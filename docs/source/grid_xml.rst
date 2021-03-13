定位格架与绕丝输入文件grids.xml
============================================

.. note::
    
    本文件是可选输入文件，这意味着不对定位格架和绕丝进行建模时可以省略本文件。


定位格架信息的输入
-----------------------------------------------------

.. code-block:: xml

    <?xml version="1.0" encoding="utf-8"?>

    <!--下面输入格架或绕丝的设计输入数据-->
    <Grid  type = "grid" >
    <!-- 下面输入格架的数据 -->

    <grid>
        <protaltype>
        <grid class="mixing_vanes_spacer" >
            <cd>
            <table row_num ="36" > 
                <row>     1           1.00    </row>
                <row>     2           1.00    </row>
                <row>     3           1.00    </row>
                <row>     4           1.00    </row>
                <row>     5           1.00    </row>
                <row>     6           1.00    </row>
                <row>     7           1.00    </row>
                <row>     8           1.00    </row>
                <row>     9           1.00    </row>
                <row>     10          1.00    </row>
                <row>     11          1.00    </row>
                <row>     12          1.00    </row>
                <row>     13          1.00    </row>
                <row>     14          1.00    </row>
                <row>     15          1.00    </row>
                <row>     16          1.00    </row>
                <row>     17          1.00    </row>
                <row>     18          1.00    </row>
                <row>     19          1.00    </row>
                <row>     20          1.00    </row>
                <row>     21          1.00    </row>
                <row>     22          1.00    </row>
                <row>     23          1.00    </row>
                <row>     24          1.00    </row>
                <row>     25          1.00    </row>
                <row>     26          1.00    </row>
                <row>     27          1.00    </row>
                <row>     28          1.00    </row>
                <row>     29          1.00    </row>
                <row>     30          1.00    </row>
                <row>     31          1.00    </row>
                <row>     32          1.00    </row>
                <row>     33          1.00    </row>
                <row>     34          1.00    </row>
                <row>     35          1.00    </row>
                <row>     36          1.00    </row>
            </table>
            </cd>
            <fxflow>
            <table row_num = "60" >
                
                <!--     gap index   fxlow     -->
                
                <row>     1          0.06   </row>
                <row>     2          0.00   </row>
                <row>     3          0.06   </row>
                <row>     4          0.00   </row>
                <row>     5          0.06   </row>
                <row>     6         -0.06   </row>
                <row>     7          0.06   </row>
                <row>     8         -0.06   </row>
                <row>     9          0.06   </row>
                <row>     10        -0.06   </row>
                <row>     11         0.06   </row>
                <row>     12        -0.06   </row>
                <row>     13         0.06   </row>
                <row>     14        -0.06   </row>
                <row>     15         0.06   </row>
                <row>     16        -0.06   </row>
                <row>     17         0.06   </row>
                <row>     18        -0.06   </row>
                <row>     19         0.06   </row>
                <row>     20        -0.06   </row>
                <row>     21         0.06   </row>
                <row>     22        -0.06   </row>
                <row>     23         0.06   </row>
                <row>     24        -0.06   </row>
                <row>     25         0.06   </row>
                <row>     26        -0.06   </row>
                <row>     27         0.00   </row>
                <row>     28        -0.06   </row>
                <row>     29         0.00   </row>
                <row>     30        -0.06   </row>
                <row>     31         0.00   </row>
                <row>     32         0.06   </row>
                <row>     33         0.00   </row>
                <row>     34         0.06   </row>
                <row>     35         0.00   </row>
                <row>     36         0.06   </row>
                <row>     37        -0.06   </row>
                <row>     38         0.06   </row>
                <row>     39        -0.06   </row>
                <row>     40         0.06   </row>
                <row>     41        -0.06   </row>
                <row>     42         0.06   </row>
                <row>     43        -0.06   </row>
                <row>     44         0.06   </row>
                <row>     45        -0.06   </row>
                <row>     46         0.06   </row>
                <row>     47        -0.06   </row>
                <row>     48         0.06   </row>		
                <row>     49        -0.06   </row>
                <row>     50         0.06   </row>
                <row>     51        -0.06   </row>
                <row>     52         0.06   </row>
                <row>     53        -0.06   </row>
                <row>     54         0.06   </row>
                <row>     55        -0.06   </row>
                <row>     56         0.00   </row>
                <row>     57        -0.06   </row>
                <row>     58         0.00   </row>
                <row>     59        -0.06   </row>
                <row>     60         0.00   </row>
            </table>
            </fxflow>
        </grid>

        <grid class="simple_spacer" >
            <cd>
            <table row_num ="36" > 
                <row>     1           0.40    </row>
                <row>     2           0.40    </row>
                <row>     3           0.40    </row>
                <row>     4           0.40    </row>
                <row>     5           0.40    </row>
                <row>     6           0.40    </row>
                <row>     7           0.40    </row>
                <row>     8           0.40    </row>
                <row>     9           0.40    </row>
                <row>     10          0.40    </row>
                <row>     11          0.40    </row>
                <row>     12          0.40    </row>
                <row>     13          0.40    </row>
                <row>     14          0.40    </row>
                <row>     15          0.40    </row>
                <row>     16          0.40    </row>
                <row>     17          0.40    </row>
                <row>     18          0.40    </row>
                <row>     19          0.40    </row>
                <row>     20          0.40    </row>
                <row>     21          0.40    </row>
                <row>     22          0.40    </row>
                <row>     23          0.40    </row>
                <row>     24          0.40    </row>
                <row>     25          0.40    </row>
                <row>     26          0.40    </row>
                <row>     27          0.40    </row>
                <row>     28          0.40    </row>
                <row>     29          0.40    </row>
                <row>     30          0.40    </row>
                <row>     31          0.40    </row>
                <row>     32          0.40    </row>
                <row>     33          0.40    </row>
                <row>     34          0.40    </row>
                <row>     35          0.40    </row>
                <row>     36          0.40    </row>
            </table>
            </cd>
        </grid>

        <grid class="non_mixing_vanes_spacer" >
            <cd>
            <table row_num ="36" > 
                <row>     1           0.70    </row>
                <row>     2           0.70    </row>
                <row>     3           0.70    </row>
                <row>     4           0.70    </row>
                <row>     5           0.70    </row>
                <row>     6           0.70    </row>
                <row>     7           0.70    </row>
                <row>     8           0.70    </row>
                <row>     9           0.70    </row>
                <row>     10          0.70    </row>
                <row>     11          0.70    </row>
                <row>     12          0.70    </row>
                <row>     13          0.70    </row>
                <row>     14          0.70    </row>
                <row>     15          0.70    </row>
                <row>     16          0.70    </row>
                <row>     17          0.70    </row>
                <row>     18          0.70    </row>
                <row>     19          0.70    </row>
                <row>     20          0.70    </row>
                <row>     21          0.70    </row>
                <row>     22          0.70    </row>
                <row>     23          0.70    </row>
                <row>     24          0.70    </row>
                <row>     25          0.70    </row>
                <row>     26          0.70    </row>
                <row>     27          0.70    </row>
                <row>     28          0.70    </row>
                <row>     29          0.70    </row>
                <row>     30          0.70    </row>
                <row>     31          0.70    </row>
                <row>     32          0.70    </row>
                <row>     33          0.70    </row>
                <row>     34          0.70    </row>
                <row>     35          0.70    </row>
                <row>     36          0.70    </row>
            </table>
            </cd>
        </grid>

        </protaltype>

        <layout>
            <table row_num="15">

                <!--定位格架1  交混格架-->	
                <row> 0.12875   mixing_vanes_spacer  </row>
                <row> 0.25287   mixing_vanes_spacer  </row>
                <row> 0.37670   mixing_vanes_spacer  </row> 
                <row> 0.50082   mixing_vanes_spacer  </row> 
                <row> 0.62465   mixing_vanes_spacer  </row> 
                <row> 0.74876   mixing_vanes_spacer  </row> 
                <row> 0.88700   mixing_vanes_spacer  </row>
                
                <!--定位格架2 简单格架-->
                <row> 0.06478   simple_spacer         </row>
                <row> 0.19081   simple_spacer         </row>		
                <row> 0.31465   simple_spacer         </row>
                <row> 0.50823   simple_spacer         </row>
                <row> 0.56287   simple_spacer         </row>
                <row> 0.68671   simple_spacer         </row>
                <row> 0.81820   simple_spacer         </row>
                <row> 0.95708   simple_spacer         </row>
                
            </table>
        </layout>
    </grid>
    </Grid>

在程序中，如果需要输入定位格架的信息需要通过 ``<Grid  type = "grid" >`` 指定输入的是定位格架的信息。
定位格架的信息在节点 ``<grid>`` 的内部。

^^^^^^^^^^^^^^^^^^^^^^^^^^^
定位格架类型的指定
^^^^^^^^^^^^^^^^^^^^^^^^^^^

在输入定位格架时，首先需要输入定位格架的类型信息。定位格架的类型在节点 ``<protaltype>`` 内部指定。
如果要设置一种定位格架，那么其输入类似于下面的结构。
需要在节点 ``<protaltype>`` 内部使用一个节点 ``<grid>`` 来指定一种类型的定位格架。

.. code-block:: xml

    <grid class="mixing_vanes_spacer" >
        <cd></cd>
        <fxflow></fxflow>
    </grid>

- ``class``    : 定位格架的类型。
- ``<cd>``     : 定位格架对于每一个通道的形状阻力系数。
- ``<fxflow>`` : 定位格架在间隙上的强迫横流。 

^^^^^^^^^^^^^^^^^^^^^^^^^^^
定位格架阻力系数的输入
^^^^^^^^^^^^^^^^^^^^^^^^^^^
定位格架的阻力系数在 ``<cd>`` 中使用表格 ``<table>`` 输入。其中 ``<row>`` 中的第一列为通道编号，第二列为形状阻力系数。

^^^^^^^^^^^^^^^^^^^^^^^^^^^
定位格架强迫横流的输入
^^^^^^^^^^^^^^^^^^^^^^^^^^^
定位格架强迫横流的输入在 ``<fxflow>`` 中使用表格 ``<table>`` 输入。其中 ``<row>`` 中的第一列为间隙编号，第二列为强迫横流系数。
当强迫横流系数为正时，强迫间隙横流由间隙两端编号较小的通道流向编号较大的编号。定位格架的强迫横流输入为可选项，当  ``<fxflow>`` 缺少时，认为不计算强迫横流。

^^^^^^^^^^^^^^^^^^^^^^^^^^^^
定位格架布置信息的输入
^^^^^^^^^^^^^^^^^^^^^^^^^^^^
定位格架布置信息的输入在节点 ``<layout>`` 中使用 ``<table>`` 输入，如下所示：

.. code-block:: xml

    <layout>
        <table row_num="15">

            <!--定位格架1  交混格架-->	
            <row> 0.12875   mixing_vanes_spacer  </row>
            <row> 0.25287   mixing_vanes_spacer  </row>
            <row> 0.37670   mixing_vanes_spacer  </row> 
            <row> 0.50082   mixing_vanes_spacer  </row> 
            <row> 0.62465   mixing_vanes_spacer  </row> 
            <row> 0.74876   mixing_vanes_spacer  </row> 
            <row> 0.88700   mixing_vanes_spacer  </row>
            
            <!--定位格架2 简单格架-->
            <row> 0.06478   simple_spacer         </row>
            <row> 0.19081   simple_spacer         </row>		
            <row> 0.31465   simple_spacer         </row>
            <row> 0.50823   simple_spacer         </row>
            <row> 0.56287   simple_spacer         </row>
            <row> 0.68671   simple_spacer         </row>
            <row> 0.81820   simple_spacer         </row>
            <row> 0.95708   simple_spacer         </row>
            
    </table>
    </layout>

其中 ``<row>`` 中第一列为轴向的无量纲高度；第二列为定位格架类型，其值为 ``<grid>`` 的 ``class`` 属性。

绕丝模型的输入
----------------------------


.. warning::
    
    程序支持对绕丝进行建模，但是本功能没有经过算例验证。
    在本文件中定义的绕丝模型用于绕丝的强迫横流模型或者分布式阻力模型（现在不可用）。
    如果使用双区域模型，不需要在本文件中定义绕丝模型的输入。


一个典型的定义绕丝的输入文件如下所示：


.. code-block:: xml

    <?xml version="1.0" encoding="utf-8"?>

    <!--下面输入格架或绕丝的设计输入数据-->
    <Grid  type = "warp" >
    <!-- 下面输入数据 -->
    <warp pitch = "12.0" pin_diameter="10.0" warp_diameter="1.5" force_corss_flow="true">

        <crossangle> 
            <table row_num="6">
                <row> 1   0.0864     0.0 </row>
                <row> 2   0.252      0.0 </row>
                <row> 3   0.418      0.0 </row>
                <row> 4   0.584      0.0 </row>
                <row> 5   0.750      0.0 </row>
                <row> 6  -0.917      0.0 </row>
            </table> 
        </crossangle>

        <warp_number>
            <table row_num="1">  
                <row> 1      1 </row>
            </table>
        </warp_number>
    </warp>

    </Grid>


在定义绕丝的输入文件中，使用 ``<Grid  type = "warp" >`` 定义输入的是绕丝的数据。
在 ``warp`` 标签的内部使用如下的参数设置绕丝的几何信息：

- ``pitch``            : 绕丝的轴向螺距，单位mm。
- ``pin_diameter``     : 燃料棒的直径，单位mm。
- ``warp_diameter``    : 绕丝直径，单位mm。
- ``force_corss_flow`` : 是否计算绕丝带来的强迫横流。


绕丝的入口跨接角数据的输入
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
绕丝跨界角的输入在标签 ``<crossangle>`` 中的 ``<table>`` 中定义。
其中 ``<row>`` 里面第一列输入间隙编号，第二列输入间隙两端连接的其中一根燃料棒上的绕丝跨接角，第三列输入间隙另外一根燃料棒上的跨界角。
并且可以只对部分间隙指定跨界角。对于不会有绕丝绕过的间隙，可以省略。当绕丝的跨接交输入为0.0时，认为间隙上一端的绕丝不会穿过间隙。
当跨接交为正时，绕丝在间隙上由编号较小的通道绕向较大的通道，否则相反。
绕丝的跨接角输入在-1到1之内的数。当绕丝在入口处于间隙重合时，输入按照绕丝绕向-1或者1。


子通道在入口处的绕丝数的输入
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
子通道在入口处的绕丝数的输入在标签 ``<warp_number>`` 内部输入。
其中 ``<row>`` 中第一列为通道的编号，第二列为通道对应的入口绕丝数。
如果某通道在入口处没有绕丝，则可以省略不输入。