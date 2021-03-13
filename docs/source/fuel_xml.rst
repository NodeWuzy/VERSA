燃料棒数据输入文件 fuel.xml
============================

一个典型的燃料棒数据输入文件如下所示：

.. code-block:: xml

    <?xml version="1.0" encoding="utf-8"?>
    <FuelPin>

        <protaltype>
            <fuelpin class="type1" inner_dia="0.0" material="fuel_1" mesh="4" outer_dia="9.5" type="heater"/>
        </protaltype>
    
        <layout>
            <f class = "type1" id ="1" > <connection> <lr> 1   2   7   8  </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="2" > <connection> <lr> 2   3   8   9  </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="3" > <connection> <lr> 3   4   9   10 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="4" > <connection> <lr> 4   5   10  11 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="5" > <connection> <lr> 5   6   11  12 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="6" > <connection> <lr> 7   8   13  14 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="7" > <connection> <lr> 8   9   14  15 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="8" > <connection> <lr> 9   10  15  16 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="9" > <connection> <lr> 10  11  16  17 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="10"> <connection> <lr> 11  12  17  18 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="11"> <connection> <lr> 13  14  19  20 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="12"> <connection> <lr> 14  15  20  21 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="13"> <connection> <lr> 15  16  21  22 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="14"> <connection> <lr> 16  17  22  23 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="15"> <connection> <lr> 17  18  23  24 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="16"> <connection> <lr> 19  20  25  26 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="17"> <connection> <lr> 20  21  26  27 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="18"> <connection> <lr> 21  22  27  28 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="19"> <connection> <lr> 22  23  28  29 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="20"> <connection> <lr> 23  24  29  30 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="21"> <connection> <lr> 25  26  31  32 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="22"> <connection> <lr> 26  27  32  33 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="23"> <connection> <lr> 27  28  33  34 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="24"> <connection> <lr> 28  29  34  35 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>
            <f class = "type1" id ="25"> <connection> <lr> 29  30  35  36 </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>      
        </layout>
        
    </FuelPin> 

燃料棒类型的输入
-------------------------------
在其中的 ``<protaltype>`` 中输入燃料棒的类型数据。

在VERSA程序中，提供三类燃料元件的模型：

- ``板状燃料元件``       ： 通过 ``type="norm_slab"`` 指定。
    
    .. code-block:: xml
    
        <fuelpin   type="normal slab"           perimeter ="4.274577"     class="type1" >
             <fuel  material = "fuel_1"          half_thick = "0.3"        mesh = "3"   />
             <clad  material = "clad_1"          thick = "0.38"            mesh = "3"   />
         </fuelpin>


  - ``perimeter``         : 板状燃料元件的热周长。
  - ``<fuel>:material``   : 燃料的材料类型。材料的物性在材料输入文件中指定。
  - ``<fuel>:half_thick`` : 燃料的半厚度，即厚度除以2。
  - ``<fuel>:mesh``       : 燃料划分的网格数。
  - ``<clad>:material``   : 包壳的材料。材料的物性在材料输入文件中指定。
  - ``<clad>:thick``      : 包壳的厚度。
  - ``<clad>:mesh``       ： 包壳划分的网格数。 

- ``加热器模型``         ： 通过 ``type="heater"`` 指定，通常用于指定电加热器或者控制棒导向管。
    
    .. code-block:: xml

        <fuelpin class="type1" inner_dia="0.0" material="fuel_1" mesh="4" outer_dia="9.5" type="heater"/>

  - ``inner_dia``         : 中心孔的直径。
  - ``material``          : 材料类型。材料的物性在材料输入文件中指定。
  - ``mesh``              : 划分的网格数。
  - ``outer_dia``         : 外径。

- ``普通的柱状燃料元件``  ：通过 ``type="normal cylinder"`` 指定。
  
    .. code-block:: xml

        <fuelpin class="fuel_pin" type="normal cylinder">
            <fuel material="fuel_1" mesh="5" thick="4.095"/>
            <gap con="5678.2" thick="0.085"/>
            <clad material="clad_1" thick="0.57"/>
        </fuelpin>

  - ``<fuel>:inner_radius`` : 燃料的中心孔半径，单位mm。
  - ``<fuel>:material``     : 燃料的材料类型。材料的物性在材料输入文件中指定。
  - ``<fuel>:thick``        : 燃料的厚度，燃料芯块的外半径减去中心孔的半径，单位mm。
  - ``<fuel>:mesh``         : 燃料划分的网格数。
  - ``<clad>:material``     : 包壳的材料。材料的物性在材料输入文件中指定。
  - ``<clad>:thick``        : 包壳的厚度，单位mm。
  - ``<gap>:con``           ：间隙的等效传热系数。
  - ``<gap>:thick``         : 间隙的宽度，单位mm。


燃料棒的布置信息输入
-------------------------------

燃料棒的布置信息在 ``<layout>`` 标签中输入。

.. code-block:: xml

    <f class = "type1" id ="1" > <connection> <lr> 1   2   7   8  </lr>  <ph> 0.25 0.25 0.25 0.25 </ph>  </connection> </f>

- ``class`` : 输入燃料棒的class类型。
- ``id``    : 输入燃料棒的编号
- ``<lr>``  : 标签内部输入与该燃料棒相邻的子通道编号。
- ``<ph>``  : 标签内部输入与该燃料棒相邻的每个子通道连接面的面积占比。
