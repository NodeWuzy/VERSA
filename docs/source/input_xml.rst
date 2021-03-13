
主输入文件input.xml
================================

为了更加直观的了解主输入文件的结构吗，这里提供两个例子。
一个是用于计算PSBT基准体瞬态工况的组输入文件，另外一个是用于计算ORNL FFM2A 实验的稳态工况输入文件。

PSBT基准体瞬态工况的主输入文件
--------------------------------

.. code-block:: xml

    <?xml version="1.0" encoding="utf-8"?>
    <!--本文件是程序的主要输入文件-->
    <problem   description="PSBT transient benchmark" >

    <!--这里输入用于计算的流动传热模型控制参数, Fluid属性用于指定流体的物性表，流体的物性写在文件fluids.xml中-->
    <Flowmodel  Fluid="water">
        <!--过冷含气率模型-->
        <subcoolvoid      model  = "Zuber_Saha"     />
        <!--空泡份额-->
        <voidfraction     model  = "Chexal_Lellouche"   /> 
        <!--两相摩擦倍率-->
        <phasefriction    model  = "Armand"   />  
        <!--单相对流换热系数-->
        <singlephayseH    model  = "Dittus_Boelter" />  
        <!--湍流交混模型 -->
        <turbulancemixing      model  = "Default"  >
            <singlephasemixing   type = "type0"           a="0.06"   /> 
        <towphasemixing      same_with_single_phase    = "true"     /> 
        </turbulancemixing>
        <!--单相摩擦系数-->
        <friction  model= "Blasius"  class = "type1" />
        <criticalheatflux model = "W_3" />        
    </Flowmodel>
    
    <Component height="3658.0"  dx="0" dy="0" dz="1"  segmentnum="40" />
    
    <Excutioner type="transient" totaltime = "9.0" method = "implict"  >
        <initial  condition    = "startwithsteady"  />
        <implict   timestepnum = "50"     max_iteration_times = "500"  info      = "false"  >
        <error  cross_flow  = "0.001"  enthalpy = "1.0E-5"          mass_flux = "0.001"  />
        </implict>
    </Excutioner>

    <Output format="txt" ></Output>

    </problem>


FFM2A实验主输入文件
--------------------------------
.. code-block:: xml

    <?xml version="1.0" encoding="utf-8"?>

    <problem description="FFM2A model" >

    <Flowmodel  Fluid="sodium">
        
        <!-- 单相对流换热系数 -->
        <singlephayseH    model   = "Mikityuk"  P = "1.243"  D= "1" />    
        
        <!-- 湍流交混模型 -->
        <turbulancemixing model   = "Cheng_Tak" c = "0.5" />    
    
        <!-- 单相摩擦系数 -->
        <friction  model="Novendstern" class="type1"   P="7.26" D="5.842"  H="304.8"  Dw = "1.422"  W="7.26" channel_type ="interior"/>	
        <friction  model="Novendstern" class="type2"   P="7.26" D="5.842"  H="304.8"  Dw = "1.422"  W="7.26" channel_type ="edge"/>
        <friction  model="Novendstern" class="type3"   P="7.26" D="5.842"  H="304.8"  Dw = "1.422"  W="7.26" channel_type ="corner"/>
    </Flowmodel>
    
    <Component    height="533.4"  dx="0" dy="0" dz="1"  segmentnum="40" />
    
    <Excutioner        type="steady"   method="implict">
        <implict      max_iteration_times="100"  info="true"  heat_conduct_factor = "2.5" >
        <continuty acc  = "0.8"  />
        <divert    pacc = "1.0"  />
        <solver    cross_flow = "BICGSTAB"     enthalpy = "Jacobi" />
        <error     cross_flow = "0.001"        enthalpy = "1.0E-6"   mass_flux="0.001" />
        </implict>
    </Excutioner>
    
    <!-- 输出变量 -->
    <Output format = "txt" />
    
    </problem>


输入文件input.xml 输入介绍
--------------------------------

下面会详细介绍VERSA程序的 ``input.xml`` 输入文件的输入选项。input.xml文件是一个xml格式的输入文件，其遵循 ``可扩展标记语言`` 的规范。
接下来逐一介绍本文件的输入：

- :class:`算例描述` ：在根元素 ``problem`` 的属性 ``description`` 中输入算例的描述。
  
    .. code-block:: xml

        <problem description="FFM2A model" >

- :class:`冷却剂物性` ：在节点 ``Flowmodel`` 的属性 ``Fluid`` 中输入冷却剂物性选项。
  输入的值为在文件 ``material/fluids.xml`` 设置的冷却剂物性的 ``class`` 属性（会在后面说明）。 

    .. code-block:: xml

        <Flowmodel  Fluid="sodium">

^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
经验关系式的输入
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

:class:`经验关系式设置` ： 在节点 ``<Flowmodel>`` 的内部进行经验关系式的设置  


单相对流换热系数经验关系式
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

- ``单相对流换热系数`` ： 单相对流换热系数使用标签 ``<singlephayseH>`` 进行设置。在VERSA程序中，内置了多种单相对流换热关系式模型。
  
  - ``Dittus_Boelter`` 关系式：
  
    .. code-block:: xml
    
        <singlephayseH    model  = "Dittus_Boelter" /> 

  
  -  ``Petukhov`` 关系式：

    .. code-block:: xml
    
        <singlephayseH   model  = "Petukhov" /> 


  -  ``Mikityuk`` 关系式：用于液态金属冷却快堆 , 在节点的属性 ``P`` 中输入燃料棒间距，单位mm。在节点的属性 ``D`` 中输入燃料棒直径，单位mm。

    .. code-block:: xml
    
        <singlephayseH    model   = "Mikityuk"  P = "12.43"  D= "10.0" /> 

  -  ``Seban`` 关系式：用于液态金属冷却快堆 , 在节点的属性 ``P`` 中输入燃料棒间距，单位mm。在节点的属性 ``D`` 中输入燃料棒直径，单位mm。

    .. code-block:: xml
    
        <singlephayseH    model   = "Seban"  P = "12.43"  D= "10.0" /> 

  -  ``OECD_NEA_2007`` 关系式：用于液态金属冷却快堆 , 在节点的属性 ``P`` 中输入燃料棒间距，单位mm。在节点的属性 ``D`` 中输入燃料棒直径，单位mm。

    .. code-block:: xml
    
        <singlephayseH    model   = "OECD_NEA_2007"  P = "12.43"  D= "10.0" /> 

  -  ``Borishanskii`` 关系式：用于液态金属冷却快堆 , 在节点的属性 ``P`` 中输入燃料棒间距，单位mm。在节点的属性 ``D`` 中输入燃料棒直径，单位mm。

    .. code-block:: xml
    
        <singlephayseH    model   = "Borishanskii"  P = "12.43"  D= "10.0" /> 

  -  ``West`` 关系式：用于液态金属冷却快堆 , 在节点的属性 ``P`` 中输入燃料棒间距，单位mm。在节点的属性 ``D`` 中输入燃料棒直径，单位mm。

    .. code-block:: xml
    
        <singlephayseH    model   = "West"  P = "12.43"  D= "10.0" />         

  -  ``Sleicher`` 关系式：用于液态金属冷却快堆 , 在节点的属性 ``P`` 中输入燃料棒间距，单位mm。在节点的属性 ``D`` 中输入燃料棒直径，单位mm。

    .. code-block:: xml
    
        <singlephayseH    model   = "Sleicher"  P = "12.43"  D= "10.0" />     



湍流交混经验关系式
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

- ``湍流交混系数`` ： 湍流交混系数关系式使用标签 ``<turbulancemixing>`` 进行设置。在VERSA程序中，内置了如下类型的湍流交混模型可以选择。


  - ``Zhukov交混关系式`` ：用于液态金属冷却快堆的绕丝交混模型 , 在节点的属性 ``P`` 中输入燃料棒间距，单位mm。在节点的属性 ``D`` 中输入燃料棒直径，单位mm。
    ``H``            ：绕丝螺距；
    ``Dw``           : 绕丝直径；
    ``W``            : 组件内壁到燃料棒中心间距；
    ``pin_ring_num`` ：燃料棒的环数；
    ``direction``    : 绕丝绕向，顺时针为1，逆时针为-1；
    ``convective_factor`` : 外围间隙的单向对流交混因子。
    ``use_MIF_eq``   : 输入 ``true`` 或者 ``false`` ，是否使用轴向等压近似求解方法。

    .. code-block:: xml
    
        <turbulancemixing model= "MIF"   P="14.3" D="13.2"   H="101.6"  Dw = "0.94"   W="7.7" pin_ring_num="5" direction="-1" use_MIF_eq="false" convective_factor="2.0"/>  

    .. note::
        使用这种交混模型时，组件的几何模型输入需要使用程序中自带的脚本进行。因为程序对于边通道和角通道的编号方案使用的是该前处理工具提供的固定方案。


  - ``Cheng_Todreas`` ：用于液态金属冷却快堆的绕丝交混模型 , 在节点的属性 ``P`` 中输入燃料棒间距，单位mm。在节点的属性 ``D`` 中输入燃料棒直径，单位mm。
    ``H``            ：绕丝螺距；
    ``Dw``           : 绕丝直径；
    ``W``            : 组件内壁到燃料棒中心间距；
    ``pin_ring_num`` ：燃料棒的环数；
    ``direction``    : 绕丝绕向，顺时针为1，逆时针为-1；
    ``use_MIF_eq``   : 输入 ``true`` 或者 ``false`` ，是否使用轴向等压近似求解方法。

    .. code-block:: xml
    
        <turbulancemixing model= "Cheng_Todreas"   P="14.3" D="13.2"   H="101.6"  Dw = "0.94"   W="7.6" pin_ring_num="5" direction="-1" use_MIF_eq="false" /> 

    .. note::
        使用这种交混模型时，组件的几何模型输入需要使用程序中自带的脚本进行。因为程序对于边通道和角通道的编号方案使用的是该前处理工具提供的固定方案。

  - ``Cheng_Tak交混模型`` ：用于液态金属冷却快堆的绕丝交混模型 , 输入系数 ``c``。        
    
    .. code-block:: xml
        
        <turbulancemixing model   = "Cheng_Tak" c = "0.5" />  
        
  - ``通用的交混模型`` ： COBRA程序中使用的交混模型，使用  :class:`model = "Default"` 指定。对于单相湍流交混，有如下四种关系式：
    
    1. :math:`w^{'} = \beta l \bar{G}_{k,j} , \beta = a` :

    .. code-block:: xml

        <turbulancemixing      model  = "Default"  >
            <singlephasemixing   type = "type0"           a="0.06"   /> 
        </turbulancemixing>

    2. :math:`w^{'} = \beta l \bar{G}_{k,j} , \beta = a Re^{b}` :

    .. code-block:: xml

        <turbulancemixing      model  = "Default"  >
            <singlephasemixing   type = "type1"           a="0.06"  b = "0.0" /> 
        </turbulancemixing>   

    3. :math:`w^{'} = \beta \bar{D}_{e} \bar{G}_{k,j} , \beta = a Re^{b}` :

    .. code-block:: xml

        <turbulancemixing      model  = "Default"  >
            <singlephasemixing   type = "type2"           a="0.06"  b = "0.0" /> 
        </turbulancemixing>
    
    4.  :math:`w^{'} = \beta \bar{D}_{e} \bar{G}_{k,j} l /d , \beta = a Re^{b}` :

    .. code-block:: xml

        <turbulancemixing      model  = "Default"  >
            <singlephasemixing   type = "type3"           a="0.06"  b = "0.0" /> 
        </turbulancemixing>   
    
    ``两相湍流交混`` 可以使用如下的输入设置为与单相湍流交混系数相同的值：

    .. code-block:: xml

        <turbulancemixing     model  = "Default"  >
            <singlephasemixing  type = "type0"       a = "0.006"  /> 
            <towphasemixing     same_with_single_phase = "true" />              
        </turbulancemixing>
    
    或者 ``两相湍流交混`` 中的系数 :math:`\beta` 可以为含气率的插值函数 ： :math:`w^{'} = \beta \bar{D}_{e} \bar{G}_{k,j}, \beta = b_x(x_q)`

    .. code-block:: xml

        <turbulancemixing     model  = "Default"  >
            <singlephasemixing  type = "type0"       a = "0.006"  /> 
            <towphasemixing     same_with_single_phase = "false" >
                <xq> 0.0    1.0 <xq/>
                <bx> 0.1    0.0 <bx>
            </towphasemixing>              
        </turbulancemixing>
    
    当不输入两相湍流交混系数的设置 ``<towphasemixing>`` 时, 在汽液两相工况下使用和单相湍流交混相同的数值计算交混系数。


单相流动阻力系数
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

- ``单相流动阻力系数``： 单相流动阻力系数关系式使用标签 ``<friction>`` 指定。在VERSA程序中，内置有多种单相流动阻力系数以计算光滑棒束与带绕丝棒束的流动阻力压降。
  并且可以输入多个阻力关系式，每一个阻力关系式使用 ``class`` 属性加以区分。

  - ``Blasius关系式`` ：
  
    .. code-block:: xml

        <friction  model= "Blasius"  class = "type1" />

  - ``COBRA-IV中使用的关系式`` ：分别指定层流和湍流时的摩擦系数，``heatedwallcorrection`` 属性设置是否使用加热壁面修正。 
    ``<lamilarfriction>`` 标签设置层流摩擦系数，如果不输入该标签则认为不计算层流时的摩擦系数。
    ``<turbulancefriction>`` 标签设置湍流交混系数，``roughness`` 属性设置壁面粗糙度。

    .. code-block:: xml

        <friction  model= "Old"  class = "type1"  heatedwallcorrection = "true" >
            <lamilarfriction />
            <turbulancefriction  roughness ="7.513E-4" />  
        </friction>

  - ``RELAP5中使用的关系式`` ： 使用RELAP5中的关系式计算单相流动阻力摩擦系数，使用 ``roughness`` 属性输入表面粗糙度：
  
  .. code-block:: xml

  <friction  model= "Default"  class = "type1"  roughness ="7.513E-4" />

  - ``简化Cheng_Todreas模型`` ：用于带绕丝棒束通道，标签中属性的定义与前述的相同。
    
    .. code-block:: xml

        <friction  model="Cheng_Todreas"  class="type1"   P="14.3" D="13.2"   H="101.6"  Dw = "0.94"   W="7.7" />

  - ``Kirikkov模型`` ：用于带绕丝棒束通道，标签中属性的定义与前述的相同。
    
    .. code-block:: xml

        <friction  model="Kirikkov"  class="type1"   P="14.3" D="13.2"   H="101.6"  Dw = "0.94"   W="7.7" />
 
  - ``详细Cheng_Todreas模型`` ：用于带绕丝棒束通道，需要对内通道、边通道和角通道分别指定阻力系数。
    
    .. code-block:: xml

        <friction  model="Cheng_Todreas_Interior"  class="type1"   P="14.3" D="13.2"   H="101.6"  Dw = "0.94"   W="7.7" />
        <friction  model="Cheng_Todreas_Edge"      class="type2"   P="14.3" D="13.2"   H="101.6"  Dw = "0.94"   W="7.7" />	
        <friction  model="Cheng_Todreas_Corner"    class="type3"   P="14.3" D="13.2"   H="101.6"  Dw = "0.94"   W="7.7"  />   

  - ``Novendstern模型`` ：用于带绕丝棒束通道，标签中属性的定义与前述的相同。
 
    .. code-block:: xml

        <friction  model="Novendstern"  class="type1"   P="14.3" D="13.2"   H="101.6"  Dw = "0.94"   W="7.7" />

  - ``Rehme模型`` ：用于带绕丝棒束通道，标签中属性的定义与前述的相同。
 
    .. code-block:: xml

        <friction  model="Rehme"  class="type1"   P="14.3" D="13.2"   H="101.6"  Dw = "0.94"   W="7.7" />

  - ``Chiu_Rohsenow_Todreas模型`` ：用于带绕丝棒束通道，需要分别指定内部通道、边通道、角通道的阻力系数。

    .. code-block:: xml

        <friction  model="Chiu_Rohsenow_Todreas"  class="type1"   P="14.3" D="13.2"   H="101.6"  Dw = "0.94"   W="7.7" channel_type ="interior"/>
        <friction  model="Chiu_Rohsenow_Todreas"  class="type2"   P="14.3" D="13.2"   H="101.6"  Dw = "0.94"   W="7.7" channel_type ="edge"    />	
        <friction  model="Chiu_Rohsenow_Todreas"  class="type3"   P="14.3" D="13.2"   H="101.6"  Dw = "0.94"   W="7.7" channel_type ="corner"  />


过冷沸腾含气率模型(可选输入)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

程序通过过冷沸腾含气率模型考虑过冷沸腾时的汽液两相非热平衡。程序提供以下几种模型计算过冷沸腾含气率

- ``Levy过冷沸腾含气率模型``：
  
    .. code-block:: xml

        <subcoolvoid      model  = "Levy"     />


- ``Zuber_Saha过冷沸腾含气率模型``：
  
    .. code-block:: xml

        <subcoolvoid      model  = "Zuber_Saha"     />

- ``Bowring过冷沸腾含气率模型``：
  
    .. code-block:: xml

        <subcoolvoid      model  = "Bowring"     />

- ``Lahey Moody过冷沸腾含气率模型``：
        
    .. code-block:: xml

        <subcoolvoid      model  = "Lahey_Moody"     />


空泡份额模型(可选输入)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

- ``均相流模型``：

    .. code-block:: xml

        <voidfraction     model  = "Homogeneous"   />


- ``Armand关系式``：
  
    .. code-block:: xml

        <voidfraction     model  = "Armand"   />


- ``滑速比模型``：需要输入滑速比 ``slip_r``

    .. code-block:: xml

        <voidfraction     model  = "Slip"   slip_r ="0.1" />

- ``Chexal_Lellouche 漂移流关系式``

    .. code-block:: xml

        <voidfraction     model  = "Chexal_Lellouche"   />



两相摩擦倍率(可选输入)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^


- ``Armand模型``：

    .. code-block:: xml

        <phasefriction    model  = "Armand"   /> 

-  ``均匀流模型``：
    
    .. code-block:: xml

        <phasefriction       model  = "Homogeneous"   /> 
  


临界热流密度比计算模型（可选输入）
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

如果输入则计算临界热流密度比，否则不计算临界热流密度比。
临界热流密度比的计算可以使用以下的模型。

-  ``W_3关系式``：

    .. code-block:: xml
    
        <criticalheatflux model = "W_3" />  

-  ``BAW_2关系式``：

    .. code-block:: xml
    
        <criticalheatflux model = "BAW_2" />  

-  ``BIASI关系式``：

    .. code-block:: xml
    
        <criticalheatflux model = "BIASI" />  

-  ``CONDIE关系式``：

    .. code-block:: xml
    
        <criticalheatflux model = "CONDIE" /> 


-  ``GAMBILL关系式``：

    .. code-block:: xml
    
        <criticalheatflux model = "GAMBILL" /> 


-  ``KNOEBEL关系式``：

    .. code-block:: xml
    
        <criticalheatflux model = "KNOEBEL" /> 
   
-  ``ZEIGARNIK关系式``：

    .. code-block:: xml
    
        <criticalheatflux model = "ZEIGARNIK" /> 

-  ``BERNATH关系式``：

    .. code-block:: xml
    
        <criticalheatflux model = "BERNATH" /> 

-  ``Sudo关系式``：

    .. code-block:: xml
    
        <criticalheatflux model = "Sudo" /> 

-  ``MIRSHAK关系式``：

    .. code-block:: xml
    
        <criticalheatflux model = "MIRSHAK" /> 

-  ``GUNTHER关系式``：

    .. code-block:: xml
    
        <criticalheatflux model = "GUNTHER" /> 

-  ``LABUNTSOV关系式``：
        
    .. code-block:: xml
    
        <criticalheatflux model = "LABUNTSOV" /> 

-  ``Shim关系式``：
        
    .. code-block:: xml
    
        <criticalheatflux model = "Shim" /> 

^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
轴向高度、方向、分段数的输入
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

在主输入文件的 ``<Component>`` 标签中，输入轴向高度，方向与分段数。

.. code-block:: xml

    <Component height="3658.0"  dx="0" dy="0" dz="1"  segmentnum="40" />

- ``height`` : 高度，单位mm。
- ``dx`` 、 ``dy`` 、 ``dz`` : 棒束冷却剂轴向流动的方向向量。
- ``segmentnum`` : 轴向分段数。


^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
执行选项的输入
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

``瞬态执行``：选择 ``type = "transient"`` 。并使用 ``totaltime`` 设置总的瞬态时间长度。
``method = "implict"`` ，指定使用隐式数值算法，目前程序中只包含隐式数值求解算法。
在 ``<implict>`` 标签中使用属性 ``timestepnum``指定总的时间步数。
在 ``<initial>`` 标签中使用属性 ``condition`` 来指定初始条件， ``startwithsteady`` 指定使用稳态初始条件。
其余参数与稳态时的设置相同。

.. code-block:: xml

    <Excutioner type="transient" totaltime = "9.0" method = "implict"  >
        <initial  condition    = "startwithsteady"  />
        <implict   timestepnum = "50"     max_iteration_times = "500"  info      = "false"  >
        <error  cross_flow  = "0.001"  enthalpy = "1.0E-5"          mass_flux = "0.001"  />
        </implict>
    </Excutioner>

``稳态``：选择 ``type = "steady"``。


.. code-block:: xml

    <Excutioner        type="steady"   method="implict">
        <implict      max_iteration_times="100"  info="true"  heat_conduct_factor = "2.5"  p_solve="true">
            <continuty acc  = "0.8"  />
            <divert    pacc = "1.0"  />
            <solver    cross_flow = "BICGSTAB"     enthalpy = "Jacobi" />
            <error     cross_flow = "0.001"        enthalpy = "1.0E-6"   mass_flux="0.001" />
        </implict>
    </Excutioner>



- ``<implict>`` :
    - ``max_iteration_times`` :  最大的外迭代次数
    - ``info``                ： 是否输出外迭代残差信息
    - ``heat_conduct_factor`` :  间隙导热形状因子，默认为1。
    - ``p_solve``             ： 是否使用压降迭代形式来求解方程。
    - ``<continuty>:acc``     :  连续性方程松弛因子。
    - ``<divert>:padd``       ： 压力迭代松弛因子。
    - ``<solver>:cross_flow`` :  横流方程求解器，输入 :class:`BICGSTAB` 、:class:`BICG` 、:class:`CG` 、:class:`GMRES` 、:class:`PLU` 来选择不同的矩阵求解器。推荐使用 :class:`BICGSTAB` 。
    - ``<solver>:enthalpy``   ： 能量方程求解器， 输入 :class:`BICGSTAB` 、:class:`BICG` 、:class:`CG` 、:class:`GMRES` 、:class:`PLU`、:class:`Jacobi` 来选择不同的矩阵求解器。推荐使用 :class:`Jacobi` 。
    - ``<error>:cross_flow``  :  外迭代横流收敛判据，推荐值0.01。
    - ``<error>:enthalpy``    :  外迭代焓值判据,推荐值1.0E-6。
    - ``<error>:mass_flux``   :  外迭代质量流量收敛判据，推荐值1.0E-5。

^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
输出文件格式的指定
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: xml

    <Output format="txt" ></Output>

输出文件格式 ``format`` 可以选择 ``txt`` 或者 ``xml``

