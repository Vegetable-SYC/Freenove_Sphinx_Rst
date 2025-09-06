##############################################################################
8. 实验性的记录(避免遗忘)
##############################################################################

8.1 并发编译
***************************

**优点:**

    编译速度显著上升，但不确定是否有什么问题

**缺点:**

1、资源消耗增加:

    会占用更多 CPU 和内存资源（使用 -j auto 时会利用所有可用核心）

    可能影响同时运行的其他应用程序性能

    但不会"损害"电脑 - 现代 CPU 有温度保护机制，自动降频

2、缓存一致性问题(罕见):

    极少数情况下可能因并行写入导致缓存不一致

    可通过 make clean 强制全量重建解决


在conf.py最前面添加以下代码:

.. code-block:: python

    num_cpus = os.cpu_count() or 1
    if num_cpus > 1:
        num_jobs = num_cpus - 1  # 保留一个核心给系统
    else:
        num_jobs = 1
    
本地编译指令修改为:

.. code-block:: console

    sphinx-autobuild --port 1009 -j auto --ignore "*/freenove_Kit/*" source build/html

其中j代表的是CPU的个数, auto代表自动选择, ignore代表需要忽略的文件, 如果不忽略freenove_Kit可能会导致一直反复构建

8.2 自动更新下载代码
***************************

在原来的工程中一直使用的是

.. code-block:: python

    os.system("rm -r freenove_Kit")
    os.system("git clone --depth 1 https://github.com/Freenove/Freenove_Complete_Starter_Kit_for_Raspberry_Pi freenove_Kit")

这个方法可以正常使用，但是存在很多的弊端

* 在本地编译时，并不是每一次构建都需要重新拉取代码，这造成了很多的麻烦，而且每次下载都非常慢，需要配置代理或者github下载到本地再配置，非常不方便

* 在RTD的环境中，通过观察日志我们可以发现，每次都会从github拉取再进行构建，也就意味着每次构建都是干净的环境，因此rm指令根本无效

因此改进的思路就是：

* 判断当前有没有freenove_Kit文件夹，如果有就说明当前在本地编译，此时只需判断是否需要更新

* 如果没有freenove_Kit文件夹那么说明此时为第一次本地编译或者此时为RTD环境，重新在github拉取

* 这样保证了使用时的代码会是最新的，也减少了编译的时间

配置代码如下：

.. code-block:: python

    repo_url = "https://github.com/Freenove/Freenove_Complete_Starter_Kit_for_Raspberry_Pi"
    repo_dir = "freenove_Kit"

    if os.path.isdir(repo_dir):
        print(f"Directory '{repo_dir}' found. Pulling latest changes...")
        try:
            subprocess.run(["git", "-C", repo_dir, "pull"], check=True)
        except subprocess.CalledProcessError as e:
            print(f"Error pulling repository: {e}")
    else:
        print(f"Directory '{repo_dir}' not found. Cloning repository...")
        try:
            subprocess.run(["git", "clone", "--depth", "1", repo_url, repo_dir], check=True)
        except subprocess.CalledProcessError as e:
            print(f"Error cloning repository: {e}")

.. note::

    由于每一个项目的下载地址都不一样。因此只有部分代码进行了修改（之前的其实也可以正常使用）

但第一次编译的时候仍然会存在clone速度超级慢的情况，因此配置代理是必要的

使用自己IP的代理

.. code-block:: console

    git config --global http.proxy 192.168.1.24:7890
    git config --global https.proxy 192.168.1.24:7890

取消代理

.. code-block:: console

    git config --global --unset http.proxy
    git config --global --unset https.proxy

使用这个方法还存在一个弊端

如果使用自动构建的指令，那么只要检测到改动就会重新进行构建，但是即使git pull的时候没有检测到文件的改动，依然会触发重新构建

因此在构建指令中需要忽略掉freenove_Kit文件夹

.. code-block:: console

    sphinx-autobuild --port 1009 -j auto --ignore "*/freenove_Kit/*" source build/html

8.3 杀死那个进程
***************************

在本地构建时我们经常需要退出编译状态，输入Ctrl+c组合键即可退出，但是万一不小心点了Ctrl+z的组合键那就会暂停这个进程

那么这个端口此时就不可用了，此时你可以选择更换一个端口重新进行构建，也可以杀死这个进程重新在这个端口构建

首先查找这个端口有哪些进程在用

.. code-block:: console

    lsof -i :1009

此时会输出进程的PID，只需要使用kill指令即可杀死进程，例如PID是43550的话

.. code-block:: console

    kill -9 43550

8.4 使用release管理jsDelivr
****************************

之前在项目中我们使用的是不指定版本的方法

.. code-block:: console

    https://cdn.jsdelivr.net/gh/Freenove/freenove-docs/docs/source/_static/css/custom.css

我们可以使用purge来强制刷新这个文件，刷新限制是每1h一次，当后续用户数量提升后，万一有错误的更新，造成的损失是巨大的

而且最致命的是，使用这个指令的时候jsdelivr服务器同步这些文件需要的时间是不确定的，可能长可能短，因此假如不指定版本，可能会出现版本回溯这种灵异事件！

因此需要创建版本号，并指定加载最新的版本

.. code-block:: console

    https://cdn.jsdelivr.net/gh/Freenove/freenove-docs@latest/docs/source/_static/css/custom.css

8.5 Developer: Reload Window
****************************************

当本地编译时出现没有正确加载插件的时候，可以使用这个指令重新加载窗口，此时插件就会正确打开

ctrl+shift+p, 输入**Developer: Reload Window**即可