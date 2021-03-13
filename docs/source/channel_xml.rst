
子通道划分输入文件subchannle.xml
===========================================

一个PSTB基准体题的典型子通道划分输入文件如下所示：

.. code-block:: xml

    <?xml version="1.0" encoding="utf-8"?>
    <!--这里输入用于计算的子通道布置和尺寸模型的控制参数-->

    <SubChannel>

        <protaltype>
            <subchannel class="center"  area="76.1841" wettedperimeter="31.99617"  hotperimeter="22.38318" friction="type1"/>
            <subchannel class="center1" area="87.8799" wettedperimeter="29.84425"  hotperimeter="29.84425" friction="type1"/>
            <subchannel class="side"    area="55.9268" wettedperimeter="26.92213"  hotperimeter="14.92213" friction="type1"/>
            <subchannel class="corner"  area="34.8419" wettedperimeter="20.06106"  hotperimeter="7.461065" friction="type1"/>
        </protaltype>

        <!--定义子通道的布置-->

        <typelist>
            <table row_num="36">
                <row>   1     corner    </row>
                <row>   2     side      </row>
                <row>   3     side      </row>
                <row>   4     side      </row>
                <row>   5     side      </row>
                <row>   6     corner    </row>
                <row>   7     side      </row>
                <row>   8     center1   </row>
                <row>   9     center1   </row>
                <row>   10    center1   </row>
                <row>   11    center1   </row>
                <row>   12    side      </row>
                <row>   13    side      </row>
                <row>   14    center1   </row>
                <row>   15    center    </row>
                <row>   16    center    </row>
                <row>   17    center1   </row>
                <row>   18    side      </row>
                <row>   19    side      </row>
                <row>   20    center1   </row>
                <row>   21    center    </row>
                <row>   22    center    </row>
                <row>   23    center1   </row>
                <row>   24    side      </row>
                <row>   25    side      </row>
                <row>   26    center1   </row>
                <row>   27    center1   </row>
                <row>   28    center1   </row>
                <row>   29    center1   </row>
                <row>   30    side      </row>
                <row>   31    corner    </row>
                <row>   32    side      </row>
                <row>   33    side      </row>
                <row>   34    side      </row>
                <row>   35    side      </row>
                <row>   36    corner    </row>
            </table>
        </typelist>

        <gaps>

            <table row_num="60">

            <row>  1   1     7     2.5    12.6 </row>
            <row>  2   7     13    2.5    12.6 </row>
            <row>  3   13    19    2.5    12.6 </row>
            <row>  4   19    25    2.5    12.6 </row>
            <row>  5   25    31    2.5    12.6 </row>
            <row>  6   2     8     3.1    12.6 </row>
            <row>  7   8     14    3.1    12.6 </row>
            <row>  8   14    20    3.1    12.6 </row>
            <row>  9   20    26    3.1    12.6 </row>
            <row>  10  26    32    3.1    12.6 </row>
            <row>  11   3    9     3.1    12.6 </row>
            <row>  12   9    15    3.1    12.6 </row>
            <row>  13   15   21    3.1    12.6 </row>
            <row>  14   21   27    3.1    12.6 </row>
            <row>  15   27   33    3.1    12.6 </row>
            <row>  16   4    10    3.1    12.6 </row>
            <row>  17   10   16    3.1    12.6 </row>
            <row>  18   16   22    3.1    12.6 </row>
            <row>  19   22   28    3.1    12.6 </row>
            <row>  20   28   34    3.1    12.6 </row>
            <row>  21   5    11    3.1    12.6 </row>
            <row>  22   11   17    3.1    12.6 </row>
            <row>  23   17   23    3.1    12.6 </row>
            <row>  24   23   29    3.1    12.6 </row>
            <row>  25   29   35    3.1    12.6 </row>
            <row>  26   6    12    2.5    12.6 </row>
            <row>  27   12   18    2.5    12.6 </row>
            <row>  28   18   24    2.5    12.6 </row>
            <row>  29   24   30    2.5    12.6 </row>
            <row>  30   30   36    2.5    12.6 </row>
            <row>  31   1    2     2.5    12.6 </row>
            <row>  32   2    3     2.5    12.6 </row>
            <row>  33   3    4     2.5    12.6 </row>
            <row>  34   4    5     2.5    12.6 </row>
            <row>  35   5    6     2.5    12.6 </row>
            <row>  36   7    8     3.1    12.6 </row>
            <row>  37   8    9     3.1    12.6 </row>
            <row>  38   9    10    3.1    12.6 </row>
            <row>  39   10   11    3.1    12.6 </row>
            <row>  40   11   12    3.1    12.6 </row>
            <row>  41   13   14    3.1    12.6 </row>
            <row>  42   14   15    3.1    12.6 </row>
            <row>  43   15   16    3.1    12.6 </row>
            <row>  44   16   17    3.1    12.6 </row>
            <row>  45   17   18    3.1    12.6 </row>
            <row>  46   19   20    3.1    12.6 </row>
            <row>  47   20   21    3.1    12.6 </row>
            <row>  48   21   22    3.1    12.6 </row>
            <row>  49   22   23    3.1    12.6 </row>
            <row>  50   23   24    3.1    12.6 </row>
            <row>  51   25   26    3.1    12.6 </row>
            <row>  52   26   27    3.1    12.6 </row>
            <row>  53   27   28    3.1    12.6 </row>
            <row>  54   28   29    3.1    12.6 </row>
            <row>  55   29   30    3.1    12.6 </row>
            <row>  56   31   32    2.5    12.6 </row>
            <row>  57   32   33    2.5    12.6 </row>
            <row>  58   33   34    2.5    12.6 </row>
            <row>  59   34   35    2.5    12.6 </row>
            <row>  60   35   36    2.5    12.6 </row>

            </table>

        </gaps>

    </SubChannel>


子通道数据的输入
--------------------------------------

在 ``<protaltype>`` 标签内部，定义子通道的类型数据。例如在上面的输入中，定义了四种类型的子通道。每一个类型的子通道使用 ``class`` 属性加以区分。
其中每一个 ``<subchannel>`` 标签定义一种类型的子通道。其属性：

- ``class`` : 表示通道类型的种类。
- ``area``  : 表示子通道的流通面积，单位mm。
- ``wettedperimeter`` ： 表示子通道的湿周长。
- ``hotperimeter`` ： 表示子通道的热周长。
- ``friction``: 表示使用的摩擦关系时的 ``class`` 类型。

在 ``<typelist>`` 标签的内部，使用一个 ``table`` 表格来输入子通道的类型。其中 ``row_num`` 表示总的子通道的数目。
其内部每一个 ``<row>`` 输入一个子通道的编号与类型。


前面给出了其中一种子通道的输入方式，另外一种输入方式是分别给出每一个子通道的几何信息。如下：

.. code-block:: xml

    <SubChannel use_detail_subchannel="true">
        <typelist>
            <table row_num="324">
                <row>1   27.437854240624986  7.461282425   7.461282425 </row>
                <row>2   49.23090848124998   14.92256485   14.92256485 </row>
                <row>3   49.23090848124998   14.92256485   14.92256485 </row>
                <row>4   49.23090848124998   14.92256485   14.92256485 </row>
                <row>5   49.23090848124998   14.92256485   14.92256485 </row>
                <row>6   49.23090848124998   14.92256485   14.92256485 </row>
                <row>7   49.23090848124998   14.92256485   14.92256485 </row>
                <row>8   49.23090848124998   14.92256485   14.92256485 </row>
                <row>9   49.23090848124998   14.92256485   14.92256485 </row>
                <row>10  49.23090848124998   14.92256485   14.92256485 </row>
                <row>11  49.23090848124998   14.92256485   14.92256485 </row>
                <row>12  49.23090848124998   14.92256485   14.92256485 </row>
                <row>13  49.23090848124998   14.92256485   14.92256485 </row>
                <row>14  49.23090848124998   14.92256485   14.92256485 </row>
                <row>15  49.23090848124998   14.92256485   14.92256485 </row>
                <row>16  49.23090848124998   14.92256485   14.92256485 </row>
                <row>17  49.23090848124998   14.92256485   14.92256485 </row>
                <row>18  27.437854240624986  7.461282425   7.461282425 </row>
                <row>19  49.23090848124998   14.92256485   14.92256485 </row>
                <row>20  87.87781696249999   29.8451297    29.8451297  </row>
                <row>21  87.87781696249999   29.8451297    29.8451297  </row>
                <row>22  87.87781696249999   29.8451297    29.8451297  </row>
                <row>23  87.87781696249999   29.8451297    29.8451297  </row>
                <row>24  87.87781696249999   29.8451297    29.8451297  </row>
                <row>25  87.87781696249999   29.8451297    29.8451297  </row>
                ...
            </table>
        </typelist>
        ...
    </SubChannel>

在这一种输入方式中，通过指定 ``use_detail_subchannel="true"`` 使用详细的子通道划分方式。
因此在 ``typelist`` 的 ``table`` 中输入每一个子通道的面积，湿周长，热周长。

间隙数据的输入
---------------------------

间隙的数据在 ``gaps`` 内部的 ``table`` 中输入。
其中第一列为间隙的编号，第二列为间隙两端较小的子通道编号，
第三列为间隙两端较大的子通道编号，第四列为间隙的宽度，
第五列为间隙两端子通道中心的间距。


子通道面积变化信息的输入
---------------------------

当需要模拟堵流这类工况时，可能需要输入在轴向上变化的子通道面积，其输入为在本文件中的 ``<areachange>`` 标签内部输入。且是一个可省略的输入选项。

.. code-block:: xml

    <areachange     iteration = "10">
        <axialposion        nb =  "5" >    0.0  0.4  0.5  0.6  1.0  </axialposion>
        <subchannel>     
            <table  row_num   =  "24"  > 
                <row>   1    1.0  1.0  0.4  1.0  1.0  </row>
                <row>   2    1.0  1.0  0.4  1.0  1.0  </row>
                <row>   3    1.0  1.0  0.4  1.0  1.0  </row> 
                <row>   4    1.0  1.0  0.4  1.0  1.0  </row>
                <row>   5    1.0  1.0  0.4  1.0  1.0  </row>
                <row>   6    1.0  1.0  0.4  1.0  1.0  </row> 
                <row>   7    1.0  1.0  0.4  1.0  1.0  </row>
                <row>   8    1.0  1.0  0.4  1.0  1.0  </row>
                <row>   9    1.0  1.0  0.4  1.0  1.0  </row>
                <row>   10   1.0  1.0  0.4  1.0  1.0  </row> 
                <row>   11   1.0  1.0  0.4  1.0  1.0  </row>
                <row>   12   1.0  1.0  0.4  1.0  1.0  </row>
                <row>   13   1.0  1.0  0.4  1.0  1.0  </row> 
                <row>   14   1.0  1.0  0.4  1.0  1.0  </row>
                <row>   15   1.0  1.0  0.4  1.0  1.0  </row> 
                <row>   16   1.0  1.0  0.4  1.0  1.0  </row>
                <row>   17   1.0  1.0  0.4  1.0  1.0  </row>
                <row>   18   1.0  1.0  0.4  1.0  1.0  </row> 	  
                <row>   19   1.0  1.0  0.4  1.0  1.0  </row>
                <row>   20   1.0  1.0  0.4  1.0  1.0  </row> 
                <row>   21   1.0  1.0  0.4  1.0  1.0  </row>
                <row>   22   1.0  1.0  0.4  1.0  1.0  </row>
                <row>   23   1.0  1.0  0.4  1.0  1.0  </row> 
                <row>   24   1.0  1.0  0.4  1.0  1.0  </row> 
            </table>
        </subchannel>
    </areachange>

- ``<areachange>:iteration`` : 完全考虑子通道面积变化的外迭代次数。 
- ``<axialposion>:nb`` : 轴向位置点数，其内部输入轴向插值的无量纲位置，必须包括0.0 与1.0两个点。
- ``<subchannel>:<table>`` : 第一列为子通道的编号，可以只输入面积变换的子通道的编号。后面的几位数值输入该通道在轴向位置上的面积变换因子。