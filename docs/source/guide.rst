=================================
用户指南
=================================

编译
=================================

在windows系统上编译
---------------------------------
VERSA子通道分析程序支持在windows系统与Linux系统上编译。
在Window系统上，可以使用Visual Studio打开程序文件夹中的.sln文件，然后编译运行。
也可以使用Cmake进行编译。

在linux系统上进行编译
---------------------------------

在linux上支持使用Cmake进行编译，在程序中的文件夹build下打开终端，输入：

.. code-block::

    cmake ..
    make -j 4

运行
================================

直接运行
--------------------------------
运行编译后生成的可执行程序的方式与运行其他可执行程序的方式一样。
在windows系统上，可以双击可执行程序，或者使用命令行的方式调用。
在运行VERSA的可执行程序后，程序将会要求用户输入输入文件的目录位置。

.. code-block::

    # INPUT FILE PATH:
        path_to_input_file/

在输入输入文件的目录时，不要忘记加上最后面的“/”符号。

命令行中传入输入文件路径
--------------------------------

在命令行中运行程序时，可以将输入文件的路径作为参数传入给程序,例如：

.. code-block::

    ./VERSA  path_to_input_file/

在windows上：


.. code-block::

    ./VERSA.exe  path_to_input_file/


输入文件目录介绍
================================
VERSA程序的输入文件保存在一个文件夹中，其目录结构如下：

.. code-block::

    - input.xml
  
    - component/
        - fuel.xml
        - subchannle.xml
        - grids.xml(可缺省)
  
    - condition/
        - conditions.xml
        - heatflux.xml
  
    - material/
        - fluids.xml
        - material.xml

因此，在VERSA程序中的输入文件夹中包含由一个主输入文件input.xml以及三个文件夹。

- ``input.xml``  : 程序的主输入文件，主要输入经验关系式的选择与执行选项。
- ``component/`` : 程序的几何部件的输入目录，包括子通道的划分信息以及燃料棒的信息。
- ``condition/`` : 程序的边界条件设置目录，包括入口冷却剂流量，功率分布等。
- ``material/``  : 程序中的固体物性与冷却剂物性设置目录。


输入文件说明：
================================

.. toctree::
    :maxdepth: 1

    input_xml.rst
    channel_xml.rst
    fuel_xml.rst
    grid_xml.rst
    fluids_xml.rst
    condition.rst

输出文件格式：
===============================


.. toctree::
    :maxdepth: 1

    output.rst
    





