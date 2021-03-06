输出文件格式
=================================

这里介绍的是程序的txt输出格式的内容，对于瞬态稳态，目前程序会对每一个时间步输出一个txt文件：

首先介绍程序输出文件中的变量及其含义：

- ``coolant_temperature``           : 子通道冷却剂温度，单位
- ``coolant_enthalpy``              ：子通道冷却剂比焓，单位
- ``void_fraction``                 : 子通道空泡份额
- ``quality``                       : 子通道含气率
- ``coolant_density``               : 子通道冷却剂密度
- ``coolant_pressure``              : 子通道冷却剂压力
- ``coolant_axial_mass_flux``       : 子通道冷却剂质量流量密度
- ``fuel_rod_average_coolant_temp`` : 燃料元件周围的冷却剂平均温度
- ``fuel_rod_heat_transcof``        : 燃料元件表面传热系数
- ``fuel_rod_surface_temp``         : 燃料元件表面温度
- ``fuel_rod_center_temp``          ：燃料元件中心温度
- ``average_temp``                  : 每一层控制体冷却剂的平均温度
- ``mCHFR``                         : 每一层的最小临界热流密度比
- ``pressure``                      : 每一层控制体的平均压力

输出格式
------------------------------------

对于每一个变量，程序按照通道或者燃料棒的顺序横向排列，并且每次输出十组数据。
例如下面是第一个通道到第十个通道的冷却剂温度分布。
每一行输出了十个通道的数据，每一个通道从入口到出口沿着纵向排列。
对于燃料棒数据，其输出格式类似，只不过编号变为燃料棒的编号。

.. code-block:: xml

    ##### value name: [coolant_temperature]:

    [index]:1:10
    316.163547    316.163547    316.163547    316.163547    316.163547    316.163547    316.139536    316.159475    316.139537    316.139536    
    316.766311    316.766311    316.766311    316.766311    316.766311    316.766311    316.701586    316.753914    316.701588    316.701586    
    317.367923    317.367923    317.367923    317.367923    317.367923    317.367923    317.248971    317.342290    317.248976    317.248971    
    317.967938    317.967938    317.967938    317.967938    317.967938    317.967938    317.783946    317.924024    317.783957    317.783946    
    318.565924    318.565924    318.565924    318.565924    318.565924    318.565924    318.308351    318.498886    318.308369    318.308351    
    319.161486    319.161486    319.161486    319.161486    319.161486    319.161486    318.823700    319.066880    318.823729    318.823700    
    319.754273    319.754273    319.754273    319.754273    319.754273    319.754273    319.331250    319.628158    319.331291    319.331250    
    320.343984    320.343984    320.343984    320.343984    320.343984    320.343984    319.832051    320.182969    319.832107    319.832051    
    320.930365    320.930365    320.930365    320.930365    320.930365    320.930365    320.326987    320.731613    320.327060    320.326987    
    321.513212    321.513212    321.513212    321.513212    321.513212    321.513212    320.816807    321.274420    320.816898    320.816807    
    322.092362    322.092362    322.092362    322.092362    322.092362    322.092362    321.302148    321.811728    321.302260    321.302148    
    322.667695    322.667695    322.667695    322.667695    322.667695    322.667695    321.783557    322.343871    321.783691    321.783557    
    323.239127    323.239127    323.239127    323.239127    323.239127    323.239127    322.261504    322.871176    322.261660    322.261504    
    323.806604    323.806604    323.806604    323.806604    323.806604    323.806604    322.736394    323.393951    322.736572    322.736394    
    324.370103    324.370103    324.370103    324.370103    324.370103    324.370103    323.208575    323.912488    323.208777    323.208575    
    324.930202    324.930202    324.930202    324.930202    324.930202    324.930202    323.678357    324.427066    323.678582    323.678357    
    325.486829    325.486829    325.486829    325.486829    325.486829    325.486829    324.146010    324.938530    324.146258    324.146010    
    326.039530    326.039530    326.039530    326.039530    326.039530    326.039530    324.611768    325.446894    324.612039    324.611768    
    326.588357    326.588357    326.588357    326.588357    326.588357    326.588357    325.076689    325.952004    325.076983    325.076689 