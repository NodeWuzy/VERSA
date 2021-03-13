冷却剂与固体物性fluids.xml与material.xml
============================================================

冷却剂物性输入文件
------------------------------------
冷却剂的输入文件通常保持如下输入即可，在主输入文件中通过引用 ``type`` 属性的值来调用该冷却剂的物性。

.. code-block:: xml

    <?xml version="1.0" encoding="utf-8"?>
    <Fluids>
        <water   type = "water" />   
        <Sodium  type = "sodium" />
        <Li      type = "lithium" />
        <LBE     type = "LBE"    /> 
    </Fluids>

- ``<water>``  ： 水物性。
- ``<Sodium>`` ： 钠物性。
- ``<LBE>``    ： 铅铋合金物性。
- ``<Li>``     :  液态金属锂物性。

固体物性输入文件
------------------------------------

材料物性的输入文件通常如下，在燃料元件中使用材料信息时，通过引用材料的 ``type`` 属性的值来调用该材料的物性。

.. code-block:: xml

    <Materials>
        <UO2      type="UO2_1"  D ="1.0" ></UO2>
        <Material type="fuel_1" k="51.5" Cp="0.4786" rho="5850" ></Material>
        <Material type="fuel_2" k="167"  Cp="1.084"  rho="2700" ></Material>
    </Materials>

- ``<UO2>``      ： 二氧化铀的物性， ``D`` 实际密度与理论密度的比值。
- ``<Material>`` ： 普通的材料，通过输入指定材料的热导率 ``k`` 、 比热容 ``Cp`` 、 密度 ``rho`` 。
