边界条件与功率信息输入文件
======================================

--------------------------------------
边界条件的输入：
--------------------------------------
边界条件的输入在文件 ``conditions.xml`` 中。一个典型的瞬态工况的边界条件输入文件如下所示：

.. code-block:: xml

    <?xml version="1.0" encoding="utf-8"?>

    <Condition>

        <systempressure  value="#pressure_time_dependent"  > 
            
            <table id = "pressure_time_dependent" row_num ="41" >

                <row> 0.0    153.0  </row>
                <row> 4.0    152.6  </row>
                <row> 8.0    152.3  </row>
                <row> 12.0   151.7  </row>
                <row> 16.0   151.1  </row>

                <row> 20.0   150.4  </row>
                <row> 24.0   149.5  </row>
                <row> 28.0   148.4  </row>
                <row> 32.0   147.5  </row>
                <row> 36.0   146.3  </row>
                
                <row> 40.0   145.2  </row>
                <row> 44.0   144.1  </row>
                <row> 48.0   142.9  </row>
                <row> 52.0   141.5  </row>
                <row> 56.0   140.6  </row>
                
                <row> 60.0   139.5  </row>
                <row> 64.0   138.2  </row>
                <row> 68.0   137.0  </row>
                <row> 72.0   135.8  </row>
                <row> 76.0   134.4  </row>
                
                <row> 80.0   132.8  </row>
                <row> 84.0   131.6  </row>
                <row> 88.0   130.4  </row>
                <row> 92.0   129.5  </row>
                <row> 96.0   128.7  </row>
                
                <row> 100    127.8  </row>
                <row> 104    126.8  </row>
                <row> 108    126.0  </row>
                <row> 112    125.2  </row>
                <row> 116    124.1  </row>

                <row> 118    123.8  </row>
                <row> 122    122.7  </row>
                <row> 126    121.6  </row>
                <row> 130    120.6  </row>
                <row> 134    119.5  </row>
                <row> 138    118.2  </row>

                <row> 142    116.9  </row>
                <row> 146    115.7  </row>
                <row> 150    114.7  </row>
                <row> 154    114.3  </row>
                <row> 158    114.2  </row>

            </table>
        
        </systempressure>
        
        <inletparameter>

            <heatparameter type="temperature"  value=" 300.4 " time_dep = "#inletparameterdep" >

                <table id = "inletparameterdep" row_num ="41" >
                    <row> 0.0    300.4  </row>
                    <row> 4.0    300.4  </row>
                    <row> 8.0    300.5  </row>
                    <row> 12.0   300.5  </row>
                    <row> 16.0   300.5  </row>

                    <row> 20.0   300.5  </row>
                    <row> 24.0   300.5  </row>
                    <row> 28.0   300.5  </row>
                    <row> 32.0   300.5  </row>
                    <row> 36.0   300.5  </row>
                    
                    <row> 40.0   300.5  </row>
                    <row> 44.0   300.5  </row>
                    <row> 48.0   300.6  </row>
                    <row> 52.0   300.5  </row>
                    <row> 56.0   300.4  </row>
                    
                    <row> 60.0   300.0  </row>
                    <row> 64.0   299.7  </row>
                    <row> 68.0   299.3  </row>
                    <row> 72.0   298.7  </row>
                    <row> 76.0   298.2  </row>
                    
                    <row> 80.0   297.6  </row>
                    <row> 84.0   297.1  </row>
                    <row> 88.0   296.6  </row>
                    <row> 92.0   296.2  </row>
                    <row> 96.0   295.8  </row>
                    
                    <row> 100    295.4  </row>
                    <row> 104    295.0  </row>
                    <row> 108    294.6  </row>
                    <row> 112    294.2  </row>
                    <row> 116    293.8  </row>

                    <row> 118    293.6  </row>
                    <row> 122    293.1  </row>
                    <row> 126    292.5  </row>
                    <row> 130    291.8  </row>
                    <row> 134    290.9  </row>
                    <row> 138    290.0  </row>

                    <row> 142    289.1  </row>
                    <row> 146    288.2  </row>
                    <row> 150    287.5  </row>
                    <row> 154    286.7  </row>
                    <row> 158    286.0  </row> 
                </table>
            </heatparameter>
            
            <massflow type="average"    value="3311.1"  time_dep = "#massflow_dep" >
                <table id = "massflow_dep" row_num = "41">
                    <row> 0.0    11.92  </row>
                    <row> 4.0    11.93  </row>
                    <row> 8.0    11.93  </row>
                    <row> 12.0   11.90  </row>
                    <row> 16.0   11.93  </row>

                    <row> 20.0   11.92  </row>
                    <row> 24.0   11.91  </row>
                    <row> 28.0   11.94  </row>
                    <row> 32.0   11.93  </row>
                    <row> 36.0   11.91  </row>
                    
                    <row> 40.0   11.90  </row>
                    <row> 44.0   11.92  </row>
                    <row> 48.0   11.94  </row>
                    <row> 52.0   11.91  </row>
                    <row> 56.0   11.91  </row>
                    
                    <row> 60.0   11.92  </row>
                    <row> 64.0   11.93  </row>
                    <row> 68.0   11.94  </row>
                    <row> 72.0   11.96  </row>
                    <row> 76.0   11.92  </row>
                    
                    <row> 80.0   11.94  </row>
                    <row> 84.0   11.78  </row>
                    <row> 88.0   11.58  </row>
                    <row> 92.0   11.39  </row>
                    <row> 96.0   11.21  </row>
                    
                    <row> 100    10.99  </row>
                    <row> 104    10.82  </row>
                    <row> 108    10.75  </row>
                    <row> 112    10.78  </row>
                    <row> 116    10.80  </row>

                    <row> 118    10.75  </row>
                    <row> 122    10.79  </row>
                    <row> 126    10.76  </row>
                    <row> 130    10.75  </row>
                    <row> 134    10.80  </row>
                    <row> 138    10.77  </row>

                    <row> 142    10.73  </row>
                    <row> 146    10.76  </row>
                    <row> 150    10.80  </row>
                    <row> 154    10.79  </row>
                    <row> 158    10.80  </row>
                </table>
            </massflow>
        </inletparameter>
    
    </Condition>

对于稳态工况下的边界条件，其输入非常简单，例如：

.. code-block:: xml

    <?xml version="1.0" encoding="utf-8"?>
    <Condition>
        <systempressure  value="150.0" > </systempressure>
        <inletparameter>
            <heatparameter type="temperature"  value="250.0"         />
            <massflow      type="average"      value="2000.0"        />
        </inletparameter>
    </Condition>


^^^^^^^^^^^^^^^^^^^^^^^
系统压力边界条件的输入
^^^^^^^^^^^^^^^^^^^^^^^

系统压力边界条件输入的单位为 ``bar`` ，其在节点 ``<systempressure>`` 内定义。

:class:`在稳态工况下` ，如果要指定系统压力为一个常数。
例如，指定系统压力为 ``150bar`` , 那么只需要按照如下的方式输入：

.. code-block:: xml

    <systempressure  value="150.0"  > </systempressure>

:class:`在瞬态工况下` ，如果要指定系统压力与时间的依赖关系时，则需要按照刚才的例子中输入一个表格：

.. code-block:: xml

    <systempressure  value="#pressure_time_dependent"  >  
        <table id = "pressure_time_dependent" row_num ="41" >
            ...
        </table>
    </systempressure>

其中节点 ``<systempressure>`` 的 ``value`` 属性中输入表格 ``<table>`` 的id值，且格式为 :class:`#id`。
就如上面的例子中所示那样。
其中在表格 ``<table>`` 中，第一列输入的是瞬态时间，而第二列输入的是系统压力。


^^^^^^^^^^^^^^^^^^^^^^^
入口边界条件的指定
^^^^^^^^^^^^^^^^^^^^^^^

入口边界条件在节点 ``<inletparameter>`` 内部输入。
其中需要输入入口温度(焓值)边界条件以及入口质量流量边界条件。

入口温度(焓值边界条件)
^^^^^^^^^^^^^^^^^^^^^^^

设置入口温度边界条件指定 ``type="temperature"``，而使用焓值边界条件使用 ``type="enthalpy"``。
当使用温度边界条件时 ``value`` 属性内输入入口的温度，单位为摄氏度。
当使用焓值边界条件时 ``value`` 属性内输入的是入口冷却剂的焓值。

:class:`在稳态工况下` ，不需要输入 ``time_dep`` 属性。例如：

.. code-block:: xml

    <heatparameter type="temperature"  value=" 300.4 " ></heatparameter>

在瞬态工况下 ，需要输入 ``time_dep`` 属性来指定入口的温度或者焓值随时间的变化，其值为时间变化表格的 ``id`` 属性。

.. code-block:: xml

    <heatparameter type="temperature"  value=" 300.4 " time_dep = "#inletparameterdep" >
        <table id = "inletparameterdep" row_num ="41" >
        ...
        </table>
    <heatparameter>

``<table>`` 表格内第一列为瞬态的时间，第二列为对应时间点上的入口工况信息。 

入口质量流量边界条件
^^^^^^^^^^^^^^^^^^^^^^^
入口质量流量边界条件在节点 ``<massflow>`` 中指定。
当输入 ``type="average"`` 时，指定使用入口平均质量流量边界条件，这时在程序开始时通过压降迭代来确定每个通道在入口处压降相等时的质量流量。
当输入 ``type="specific"`` 时，指定对于每个通道的质量流量均为该值。
在 ``value`` 属性中输入入口的质量流量密度，其单位为 :math:`kg/s`。

:class:`在稳态工况下` ，不需要输入 ``time_dep`` 属性。例如：
    
.. code-block:: xml

    <massflow type="average" value="2000.0"        />

:class:`在瞬态工况下` ，需要输入 ``time_dep`` 属性来指定入口质量流量随时间的变化。其输入方式类似于上面，这里不多赘述。
在 ``<table>`` 内，第一列为瞬态时间，第二列为质量流量的变化函数。
对于某一时间点上的质量流量，其值为 ``value`` 内输入值乘以该时刻的表格中的变化函数的值并除以初始时刻表格中的变换函数值。
    


--------------------------------------
功率分布信息的输入：
--------------------------------------

燃料棒的功率分布信息在文件 ``heatflux.xml`` 中输入。
VERSA程序中支持输入2D/1D功率分布信息以及全三维的功率分布信息。


^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
2D/1D功率分布信息输入
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

2D/1D的功率分布指的是对于每一根燃料棒指定一个径向平面上的功率分布，并假定所有的燃料棒在轴向上的功率分布函数的形状都是相同的。
这种功率输入需要给定的信息比较少，但是在一些情况下会与实际情况有较大的偏差。
下面是一个瞬态功率分布的输入文件例子：

.. code-block:: xml

    <?xml version="1.0" encoding="utf-8"?>
    <Heatflux>

        <!--定义热流密度-->
        <!--
            属性Tranvalue使用常数是定义均一热流密度，value可以使用table的id值表示每根燃料棒的平均热流密度分布值。
            属性Axialvalue定义轴向的热流密度分布，Axialvalue使用常数代表在轴向上均匀为常数的热流密度，
            属性Axialvalue为table的id时，表示轴向上每层的热流密度分布表，其中在轴向上的高度坐标采用相对值表示。
            属性timedep表示热流密度与时间的依赖关系。
        -->

        <heatflux tranvalue="#tranheatflux" axialvalue ="#axialheatflux"  average_value = "1.0584" time_dep = "#time_dependent_value">

            <table id="time_dependent_value" row_num = "51" >

                <row>0.0 1.06018</row>
                <row>0.2 1.06188</row>
                <row>0.3 1.06145</row>
                <row>0.6 1.05679</row>
                <row>0.7 1.05594</row>
                <row>1.0 1.06569</row>
                <row>1.2 1.08605</row>
                <row>1.3 1.10980</row>
                <row>1.6 1.13651</row>
                <row>1.7 1.16238</row>
                <row>2.0 1.18868</row>
                <row>2.2 1.21370</row>
                <row>2.3 1.23532</row>
                <row>2.6 1.25610</row>
                <row>2.7 1.28367</row>
                <row>3.0 1.30742</row>
                <row>3.2 1.33201</row>
                <row>3.3 1.37145</row>
                <row>3.6 1.39690</row>
                <row>3.7 1.41895</row>
                <row>4.0 1.44524</row>
                <row>4.2 1.46093</row>
                <row>4.3 1.46051</row>
                <row>4.6 1.46008</row>
                <row>4.7 1.46348</row>
                <row>5.0 1.46348</row>
                <row>5.2 1.46220</row>
                <row>5.3 1.44906</row>
                <row>5.6 1.45075</row>
                <row>5.7 1.46093</row>
                <row>6.0 1.46305</row>
                <row>6.2 1.46814</row>
                <row>6.3 1.46220</row>
                <row>6.6 1.45796</row>
                <row>6.7 1.46517</row>
                <row>7.0 1.46602</row>
                <row>7.2 1.47068</row>
                <row>7.3 1.46941</row>
                <row>7.6 1.45584</row>
                <row>7.7 1.45627</row>
                <row>8.0 1.45669</row>
                <row>8.2 1.46135</row>
                <row>8.3 1.46305</row>
                <row>8.6 1.45754</row>
                <row>8.7 1.45923</row>
                <row>9.0 1.46008</row>
                <row>9.2 1.46051</row>
                <row>9.3 1.45881</row>
                <row>9.6 1.45669</row>
                <row>9.7 1.45839</row>
                <row>10. 1.47026</row>
                
            </table>
        
            <table id="axialheatflux"   row_num="26" >
                <row>   0.000000    0.40   </row>
                <row>   0.020833    0.42   </row>
                <row>   0.062499    0.47   </row>
                <row>   0.104159    0.56   </row>
                <row>   0.145826    0.67   </row>
                <row>   0.187492    0.80   </row>
                <row>   0.229158    0.94   </row>
                <row>   0.270825    1.08   </row>
                <row>   0.312491    1.22   </row>
                <row>   0.354158    1.34   </row>
                <row>   0.395824    1.44   </row>
                <row>   0.437490    1.51   </row>
                <row>   0.479157    1.55   </row>
                <row>   0.520823    1.55   </row>
                <row>   0.562489    1.51   </row>
                <row>   0.604156    1.44   </row>
                <row>   0.645822    1.34   </row>
                <row>   0.687489    1.22   </row>
                <row>   0.729156    1.08   </row>
                <row>   0.770822    0.94   </row>
                <row>   0.812489    0.80   </row>
                <row>   0.854156    0.67   </row>
                <row>   0.895822    0.56   </row>
                <row>   0.937488	0.47   </row>
                <row>   0.041666    0.42   </row>
                <row>   1.000000    0.40   </row>
            </table>

            <table id ="tranheatflux" row_num ="25" >
                <row> 1   0.85 </row>  <row> 2   0.85 </row> <row> 3   0.85 </row> 
                <row> 4   0.85 </row>  <row> 5   0.85 </row> 
                <row> 6   0.85 </row>  <row> 7   1.00 </row> <row> 8   1.00 </row> 
                <row> 9   1.00 </row>  <row> 10  0.85 </row> 
                <row> 11  0.85 </row>  <row> 12  1.00 </row> <row> 13  0.00 </row> 
                <row> 14  1.00 </row>  <row> 15  0.85 </row> 
                <row> 16  0.85 </row>  <row> 17  1.00 </row> <row> 18  1.00 </row> 
                <row> 19  1.00 </row>  <row> 20  0.85 </row> 
                <row> 21  0.85 </row>  <row> 22  0.85 </row> <row> 23  0.85 </row> 
                <row> 24  0.85 </row>  <row> 25  0.85 </row> 
            </table>
        
        </heatflux>
    
    </Heatflux>

在上面的输入中，功率分布信息在节点 ``<heatflux>`` 中指定：

.. code-block:: xml
    
    <heatflux tranvalue="#tranheatflux" axialvalue ="#axialheatflux"  average_value = "1.0584" time_dep = "#time_dependent_value">

其中的输入信息为：

- ``tranvalue``     : 径向燃料元件功率分布信息，输入一个表格的id或者一个常数。当输入一个常数时，指定所有的燃料棒均为该值。
- ``axialvalue``    : 燃料棒在径向上的功率分布表格的id值。
- ``average_value`` : 燃料棒功率分布的平均值。
- ``time_dep``      ：燃料棒功率时间变换函数表格的id值。在稳态工况下可以不输入。

^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
3维功率分布信息的输入
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
由于三维功率输入需要输入较多的信息，因此使用一个二进制文件输入。例如：
    
.. code-block:: xml
    
    <heatflux power_3d ="true" average_value = "0.3414" power_file = "power.bin" />

当设置 ``power_3d ="true"`` 时指定使用三维的功率分布信息。其中 ``power_file`` 为二进制功率分布文件的名称，其位于算例的 ``condition`` 目录下。 ``average_value`` 为燃料棒功率分布的平均值。

而二进制文件的格式为：

.. code-block:: xml

    int(轴向功率分布节点数)
    double[](轴向分段节点无量纲位置) 
    double[](第一根燃料棒对应节点上的功率分布)
    double[](第二根燃料棒对应节点上的功率分布)
    double[](第三根燃料棒对应节点上的功率分布)
    ...
