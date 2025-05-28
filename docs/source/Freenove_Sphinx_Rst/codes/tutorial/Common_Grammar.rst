.. _Grammar:

##############################################################################
4. Common Syntax
##############################################################################

4.1 Basic Syntax
***************************************

4.1.1 Document Title
=======================================

Placed at the top of each rst file::

    ##############################################################################
    Chapter
    ##############################################################################

4.1.2 Headings
=======================================

::

    Level 1 Heading
    ******************************

    Level 2 Heading
    ==============================

    Level 3 Heading
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

    Level 4 Heading
    ------------------------------

    Level 5 Heading
    ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

    Level 6 Heading
    """"""""""""""""""""""""""""""

4.1.3 Emphasis
=======================================

**Bold**

*Italic*

:: 
    
    **Bold**

    *Italic*

4.1.4 Font Sizes
=======================================

:xx-large:`XX-Large`

:x-large:`X-Large`

:larger:`Larger`

:large:`Large`

:small:`Small`

:smaller:`Smaller`

:x-small:`X-Small`

:xx-small:`XX-Small`

::

    :xx-large:`XX-Large`

    :x-large:`X-Large`

    :larger:`Larger`

    :large:`Large`

    :small:`Small`

    :smaller:`Smaller`

    :x-small:`X-Small`

    :xx-small:`XX-Small`

4.1.5 Font Colors
=======================================

:red:`Red`

:yellow:`Yellow`

:orange:`Orange`

:blue:`Blue`

:green:`Green`

::

    :red:`Red`

    :yellow:`Yellow`

    :orange:`Orange`

    :blue:`Blue`

    :green:`Green`

4.1.6 Line Breaks
==================

| Line break
| Line break

::

    | Line break
    | Line break

Or use double line breaks:

Line break

Line break

::

    Line break

    Line break

4.1.7 Text Alignment
====================================

Use .. centered:: directive to center text

.. centered:: Centered Text

::

    .. centered:: Centered Text

4.1.8 Admonitions
====================================

.. list-table::

    * - `.. note::`
      - Notes

    * - `.. hint::`
      - Hints or suggestions

    * - `.. tip::`
      - Practical tips or shortcuts

    * - `.. warning::`
      - Warnings

    * - `.. danger::`
      - Dangerous content

    * - `.. important::`
      - Key information

    * - `.. attention::`
      - Important content

    * - `.. error::`
      - Error descriptions

    * - `.. caution::`
      - Cautions

    * - `.. admonition::`
      - Custom content

Examples:

.. note::       Notes

.. hint::       Hints or suggestions

.. tip::        Practical tips or shortcuts

.. warning::    Warnings

.. danger::     Dangerous content

.. important::  Key information

.. attention::  Important content        

.. error::      Error descriptions                

.. caution::    Cautions

.. admonition:: Custom Message

    Custom content

4.1.9 Equations
======================================

.. math:: 
    
    s = v/t

::

    .. math:: 
        
        s = v/t

.. math::

   \boldsymbol{\frac{(V_1 - V_o)}{R_1}} \boldsymbol{+} \boldsymbol{\frac{(V_2 - V_o)}{R_2}} \boldsymbol{+} \boldsymbol{\frac{(V_3 - V_o)}{R_3}} \boldsymbol{=} \boldsymbol{0}

::

    .. math::

        \boldsymbol{\frac{(V_1 - V_o)}{R_1}} \boldsymbol{+} \boldsymbol{\frac{(V_2 - V_o)}{R_2}} \boldsymbol{+} \boldsymbol{\frac{(V_3 - V_o)}{R_3}} \boldsymbol{=} \boldsymbol{0}

4.1.10 Lists
=======================================

Ordered Lists
---------------------------------------

1. h
#. e
#. a
#. d
#. s
#. o
#. m
#. e

::

    1. h
    #. e
    #. a
    #. d
    #. s
    #. o
    #. m
    #. e

Unordered Lists
---------------------------------------

- h
- e
- a
- d
- s
- o
- m
- e

::

    - h
    - e
    - a
    - d
    - s
    - o
    - m
    - e

4.1.11 Tables
=======================================

List Tables (Recommended)
---------------------------------------

.. list-table:: Example
    :widths: 1 1 1
    :header-rows: 1

    * - Cell 1
      - Cell 2
      - Cell 3
    
    * - Row 2 Cell 1
      - Row 2 Cell 2
      - Row 2 Cell 3
    
    * - Row 3 Cell 1
      - Row 3 Cell 2
      - Row 3 Cell 3
    
        Line break in cell
    
    * - Row 4 Cell 1
      - Row 4 Cell 2
      - Row 4 Cell 3

::

    .. list-table:: Example
        :widths: 1 1 1  
        :header-rows: 1

        * - Cell 1
          - Cell 2
          - Cell 3
        
        * - Row 2 Cell 1
          - Row 2 Cell 2
          - Row 2 Cell 3
        
        * - Row 3 Cell 1
          - Row 3 Cell 2
          - Row 3 Cell 3
        
            Line break in cell
        
        * - Row 4 Cell 1
          - Row 4 Cell 2
          - Row 4 Cell 3
     
Simple Tables
--------------------------------------------------------------------------------

=======  ========  =======
Row 1    1         2
=======  ========  =======
Row 2    1         2
Row 3    1         2
Row 4    1         2
Row 5    1         2
=======  ========  =======

:: 

    =======  ========  =======
    Row 1    1         2
    =======  ========  =======
    Row 2    1         2
    Row 3    1         2
    Row 4    1         2
    Row 5    1         2
    =======  ========  =======

CSV Tables
--------------------------------------------------------------------------------

.. csv-table:: Example
    :header: "Col1", "Col2", "Col3"
    :widths: 15, 10, 30

    "Row 1", 1, 2
    "Row 2", 1, 2
    "Row 3", 1, 2

::

    .. csv-table:: Example
        :header: "Col1", "Col2", "Col3"
        :widths: 15, 10, 30

        "Row 1", 1, 2
        "Row 2", 1, 2
        "Row 3", 1, 2

Grid Tables
-----------------------------------------------------------------------------------------

+-------+-----+-----+
| one   | 1   | 2   |
+-------+-----+-----+
| two   | 1   | 2   |
+-------+-----+-----+
| three | 1   | 2   |
+-------+-----+-----+
| four  | 1   | 2   |
+-------+-----+-----+
| five  | 1   | 2   |
+-------+-----+-----+

::

    +-------+-----+-----+
    | one   | 1   | 2   |
    +-------+-----+-----+
    | two   | 1   | 2   |
    +-------+-----+-----+
    | three | 1   | 2   |
    +-------+-----+-----+
    | four  | 1   | 2   |
    +-------+-----+-----+
    | five  | 1   | 2   |
    +-------+-----+-----+

Grid tables are flexible and can be designed as needed, for example:

+-------+-----+-----+
| one   | two |three|
+-------+-----+-----+
| two   |           |
+-------+           |
| three |           |
+-------+           |
| four  |           |
+-------+           |
| five  |           |
+-------+-----------+

::

    +-------+-----+-----+
    | one   | two |three|
    +-------+-----+-----+
    | two   |           |
    +-------+           |
    | three |           |
    +-------+           |
    | four  |           |
    +-------+           |
    | five  |           |
    +-------+-----------+

- Install the Table Formatter plugin in VSCode for easy table formatting. After installation, use Ctrl-Shift-P to call Table: Format Current or Table: Format All. See :ref:`Table Formatter <freenove_sphinx_rst/codes/tutorial/tools:table formatter>`

- Alternatively, use my script tool to generate custom table layouts. See :ref:`Sphinx Table Generator <freenove_sphinx_rst/codes/tutorial/tools:freenove sphinx table generator>`

Table Styling
-----------------------------------------------

Official attributes can be used to control table styling

Commonly used attributes for position and width:

Position
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Use the align attribute (common in Markdown syntax)

.. table::
   :align: left

   +-------+-----+-----+
   | one   | 1   | 2   |
   +=======+=====+=====+
   | two   | 1   | 2   |
   +-------+-----+-----+
   | three | 1   | 2   |
   +-------+-----+-----+

[Additional table examples with center and right alignment...]

Width
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. table::
   :width: 100%

   +-------+-----+-----+
   | one   | 1   | 2   |
   +=======+=====+=====+
   | two   | 1   | 2   |
   +-------+-----+-----+
   | three | 1   | 2   |
   +-------+-----+-----+

.. table::
   :width: 50%

   +-------+-----+-----+
   | one   | 1   | 2   |
   +=======+=====+=====+
   | two   | 1   | 2   |
   +-------+-----+-----+
   | three | 1   | 2   |
   +-------+-----+-----+

.. table::
   :width: 20%

   +-------+-----+-----+
   | one   | 1   | 2   |
   +=======+=====+=====+
   | two   | 1   | 2   |
   +-------+-----+-----+
   | three | 1   | 2   |
   +-------+-----+-----+

::

    .. table::
        :width: 100%

        +-------+-----+-----+
        | one   | 1   | 2   |
        +=======+=====+=====+
        | two   | 1   | 2   |
        +-------+-----+-----+
        | three | 1   | 2   |
        +-------+-----+-----+

    .. table::
        :width: 50%

        +-------+-----+-----+
        | one   | 1   | 2   |
        +=======+=====+=====+
        | two   | 1   | 2   |
        +-------+-----+-----+
        | three | 1   | 2   |
        +-------+-----+-----+

    .. table::
        :width: 20%

        +-------+-----+-----+
        | one   | 1   | 2   |
        +=======+=====+=====+
        | two   | 1   | 2   |
        +-------+-----+-----+
        | three | 1   | 2   |
        +-------+-----+-----+

Special Table Styles (Important!)
-----------------------------------------------------------------------------------------

I've defined a CSS style for Word-like tables. Use the freenove-ow class (centered by default).

.. table::
   :class: freenove-ow

   +-------+-----+-----+
   | one   | 1   | 2   |
   +=======+=====+=====+
   | two   | 1   | 2   |
   +-------+-----+-----+
   | three | 1   | 2   |
   +-------+-----+-----+

::

    .. table::
       :class: freenove-ow

       +-------+-----+-----+
       | one   | 1   | 2   |
       +=======+=====+=====+
       | two   | 1   | 2   |
       +-------+-----+-----+
       | three | 1   | 2   |
       +-------+-----+-----+

4.2 Code Display and Highlighting
******************************************

4.2.1 Including Local Code Files
==============================================================

Display entire file:

.. literalinclude:: ../../../key_pad/key_pad.ino
    :linenos:
    :language: c
    :dedent:

Display code snippets:

.. literalinclude:: ../../../key_pad/key_pad.ino
    :linenos:
    :language: c
    :lines: 11-15
    :dedent:

4.2.2 Code Highlighting
===============================

Highlight lines 2 and 4:

.. literalinclude:: ../../../key_pad/key_pad.ino
    :linenos:
    :language: c
    :lines: 11-15
    :emphasize-lines: 2, 4
    :dedent:

Highlight lines 2 through 4:

.. literalinclude:: ../../../key_pad/key_pad.ino
    :linenos:
    :language: c
    :lines: 11-15
    :emphasize-lines: 2-4
    :dedent:

4.3 Displaying Images
****************************************

4.3.1 Basic Image Display
===================================

Control image size:

.. image:: ../_static/imgs/freenove.png
    :width: 10%

Control image position:

.. image:: ../_static/imgs/freenove.png
    :width: 20%
    :align: left

4.3.2 Images in Tables
===================================

Grid table example:

+-----------+------------------+-----------------+
| Esbonib   | reStructuredText | Table Formatter |
+===========+==================+=================+
| |Net00|   | |Net01|          | |Net02|         |
+-----------+------------------+-----------------+

.. |Net00| image:: ../_static/imgs/Environment/Envi00.png
.. |Net01| image:: ../_static/imgs/Environment/Envi01.png
.. |Net02| image:: ../_static/imgs/Environment/Envi02.png

::

    +-----------+------------------+-----------------+
    | Esbonib   | reStructuredText | Table Formatter |
    +===========+==================+=================+
    | |Net00|   | |Net01|          | |Net02|         |
    +-----------+------------------+-----------------+

    .. |Net00| image:: ../_static/imgs/Environment/Envi00.png
    .. |Net01| image:: ../_static/imgs/Environment/Envi01.png
    .. |Net02| image:: ../_static/imgs/Environment/Envi02.png

List table example:

.. list-table:: 
    :header-rows: 1 

    * - Esbonib
      - reStructuredText
      - Table Formatter

    * - |List00|
      - |List01|
      - |List02| 

.. |List00| image:: ../_static/imgs/Environment/Envi00.png
.. |List01| image:: ../_static/imgs/Environment/Envi01.png
.. |List02| image:: ../_static/imgs/Environment/Envi02.png

4.4 Hyperlinks
**********************

4.4.1 External Links
============================================

`Freenove <https://github.com/Freenove>`_

4.4.2 Internal Links
============================================

Using built-in syntax:
--------------------------------------------

Create anchor::

    .. _Grammar:

Reference anchor::

    :ref:`Jump <Grammar>`

Using Sphinx extensions:
--------------------------------------------

Automatically generated labels::

    :ref:`Jump <freenove_sphinx_rst/codes/tutorial/common_grammar:4. Common Syntax>`

4.5 Video Embedding
********************************************************************************

YouTube video example (change video ID as needed):

.. raw:: html

   <iframe height="500" width="690" src="https://www.youtube.com/embed/4pTAqlxHffI" frameborder="0" allowfullscreen></iframe>

4.6 More Syntax
*******************************************************************************

For more syntax, refer to:

Sphinx documentation: https://www.sphinx-doc.org/en/master/usage/

Read the Docs documentation: https://docs.readthedocs.com/platform/stable/index.html

reStructuredText markup: https://zh-sphinx-doc.readthedocs.io/en/latest/rest.html