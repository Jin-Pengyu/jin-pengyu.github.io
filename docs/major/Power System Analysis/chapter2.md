## 电力线路和电抗器的等值电路和参数
### 电力线路的结构
==Q：电力线路有哪两种形式？各有什么特点？==

- 分为架空线和电缆两类
- 架空线运行条件恶劣，要求高机械强度和抗化学腐蚀能力
- 电缆造价高，检修费工，但不占地，可靠性高

==Q：架空线路如何进行标号，具体意义是什么？==

- 铝L，钢G，铜T，铝合金HL
- 绞合的多股导线强度更大，标记为J
- 铝的机械性能差，但导电好；钢的机械性能好，但导电差，所以绞合在一起；LGJ：钢芯铝线（铝钢绞），LGJ**J**：加强型钢芯铝线，LGJ**Q**：轻型钢芯铝线
- LGJ-400/50：铝线额定截面积400平方毫米，钢线额定截面积50平方毫米。但实际中，导线实际截面积会偏**小**
- LGJ-400：载流截面积为400平方毫米

### 电力线路的电磁现象及参数
==Q：线路具有哪些电磁现象？可以用哪些参数表征？==

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/20230228111219.png)

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/20230228111246.png)

==Q：架空线路的参数如何计算？==

**电阻**：线路通过电流时产生的有功损失效应，通过电阻率计算电阻$r=\frac{\rho}{S}$

- 几个特殊点：
    - 集肤效应和邻近效应
    - 多股绞线导体长度增加2~3%
    - 制造时实际截面积略小
    - 温度修正，给定的是20&deg;
- 总之会让实际电阻一般比计算的偏大

**电感（电抗）**：反映载流导体产生的磁场效应

- 几个公式需要记住
    - 单股导线
        - 电抗：$x=0.1445lg\frac{D_m}{r'}$（非铁磁材料）
        - 几何均距：$D_m=\sqrt[3]{D_{AB}D_{BC}D_{CA}}$
        - 几何平均半径：$r'=re^{\frac{1}{4}}=0.779r$
    - 多股导线的电抗比单股要**大**，因为几何平均半径会变小；铁磁材料的导线电抗会变**小**，比如钢芯铝线，因为几何平均半径会变大，约为$0.95r$

==Q；什么是分裂导线？有什么特点？==

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/C95TA%7B%5BY%60C@6E%5DP%7DU5M$%7BF_tmb.jpg)

- 几个公式需要记住
    - 分裂导线的电抗：$x=0.1445lg\frac{D_m}{r_{eq}}+\frac{0.0157}{n}$
    - 分裂导线等值半径：$r_{eq}=\sqrt[n]{rd_m^{n-1}}$
    - 对于不分裂的110kV/220kV架空线，单位长度的等效电抗约为0.4欧姆/千米
    - 2、3、4**分裂的导线**，单位长度的等效电抗约为0.33、0.30和0.28欧姆/千米

【注】：

- 220kV及以上的系统，为了减小电晕损耗和线路电抗，会采用分裂导线
- 另外一种增加截面积的方式是采用扩径导线。人为增加导线直径，但不增加载流部分，即通过中间支撑层撑出间隔
- 实际上，由于几何均距和几何半径都在对数中，所以其实变化不大

**电导**：反映泄漏电流和空气游离所引起的有功功率损耗。通常忽略泄漏电流。（绝缘良好）

- 不是电阻的倒数
- 电晕现象：导线表面电场强度超过空气击穿强度，使导体附近空气游离而产生的局部放电现象
- 在电力系统的计算中，通常忽略电晕损耗（因为常采用分裂导线、扩径导线以减少电晕）

**电容（电纳）**：反映带电导体的电场效应

- 需要记住
    - 单位长度的电纳：$b=\frac{7.58}{lg\frac{D_m}{r}}×10^{-6}$
    - 分裂导线算电纳，导线半径用等效半径$r_{eq}=\sqrt[n]{rd_m^{n-1}}$
    - 分裂导线使得导线等效半径增加，分裂导线的电容会变大

==Q：什么是导线的循环换位？有什么用？==

- 当三相导线排列不一致的时候，各相导线的磁链、电感会不同，引起三相参数的不对称
- 简单来说，循环换位就是为了减少三相参数的不平衡
- 中性点直接接地系统中长度超过100公里的架空线路都应该换位


<center>

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/20230228131420.png)

</center>

==Q：电缆线路的参数较架空线路有什么特点？==

- 电缆线路的阻抗和导纳很难用解析法计算，这是因为导电截面复杂。一般都是厂家实测参数。
- 电缆的电阻略大于架空线路，电抗要小很多。**电抗小的原因是**三相导体距离远小于架空线。
- 电缆线路的电纳远大于相同截面的架空线，原因除了三相导体距离以外，电缆往往离地面也比较近。

### 线路的等值电路
==Q：线路的单位长度等值电路及参数能直接用嘛？==

不能，实际中线路很长，是分布式的，想要集中等值参数要通过积分实现

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/20230228140247.png)

==Q：如何进行输电线路的集中参数等值？==
<center>

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/20230228140352.png)

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/20230228141118.png)

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/20230228141202.png)

</center>

- 架空短线路100km以下，电压不高时，可以略去导纳支路。
- 中等长度架空线路100~300km，多用$\pi$型等值电路。
- 长线路，需要考虑分布参数特性。可以用修正系数的方法对参数进行修正。（修正公式不需要掌握）

### 电抗器的模型及参数
- 电力系统的电抗器主要用于限制短路电流，其电阻很小，电感很大。
- 等值电路一般只用电抗表示。
- 电抗器的额定参数包括：额定电压、额定电流和电抗百分比（没有额定容量）
- $X_R\%=\frac{X_R}{X_N}×100$
- $X_N=\frac{U_{RN}}{I_{RN}}$



## 变压器的等值电路和参数
### 概述
==Q：电机学中变压器的等值电路有几种演变？适用范围？==

- T型、$\Gamma$型（近似等值）、简化等值
- T型等值电路最准确；$\Gamma$型将励磁支路前移能够简化计算；简化等值不适合空载的分析

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/1L%6021P@9K3PQ~7%5BYQ%60%5DI~9.jpg)

==Q：T型等值电路是否实用？==

1. 是从变压器原理出发得到的，等值电路及参数的机理很明确
2. 原边和副边的电抗参数需要分离，实际中很难做到。我们只能做空载和短路实验，获得4个实验数据
3. 准确但不实用

==Q：$\Gamma$型等值电路的简化依据？==

励磁电抗对于主磁路，其值远大于漏抗

### 电力系统中的变压器模型
==Q：电力系统分析中采用的变压器模型是怎样？==

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/9QA2F01XI2Q6~~Z4_%25GIK.jpg)

==Q：电力系统和电机学中对变压器变比的规定有何不同？==

- 系统：空载线电压（看作黑盒子二端口，关心外部参数）
- 电机：相电动势（看$E=-N\frac{d\phi}{dt}$，关心电磁机理）
- 系统从实用角度出发；电机从机理出发

==Q：变压器中的参数及意义都是什么？==

1. 电阻：将二次绕组电阻折算到一次侧，与一次绕组合并
2. 电抗：将二次绕组漏抗折算到一次侧，与一次绕组合并
3. 电导：对应铁心损耗
4. 电纳：对应励磁功率
5. 变比：空载线电压之比

==Q：为什么励磁支路这么处理？==

有助于实验数据和变压器参数的一一对应

### 变压器的实验与参数
==Q：如何测得变压器的参数？==

- 变压器的短路实验
    - 进行短路实验时，将一侧绕组短接（通常时**低压侧**），在另一侧绕组施加电压，使短路绕组的电流达到额定值，测得变压器的**短路总损耗**和**短路电压** 

【注】：变压器短路实验之所以在高压侧加电压，是因为高压侧电流小，实验测量简单方便。高压侧此时也不用加很大的电压。（一般最多加到20%的额定电压）

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/6T%7D%5D3XCG_Z9Y8%5B_AOHV_2W.jpg)

1. 短路实验确定电阻 
    - 外加电压小，忽略铁心损耗
    - 短路损耗=额定电流时的原副边电阻损耗
    - $\Delta P_s=3I_N^2R_T$
    - 故$R_T=\frac{\Delta P_s}{3I_N^2}=\frac{\Delta P_s(\sqrt{3}V_N)^2}{3S_N^2}=\frac{\Delta P_sV_N^2}{S_N^2}$，
    - 计算的时候要带着单位去计算，短路损耗时kW，容量是kVA，电压是kV，此时的结果，单位为$k\Omega$，转化为欧姆$\Omega$应乘$10^3$
2. 短路实验确定电抗
    - 电阻的电压降远小于电抗压降
    - 短路电压=额定电流时电抗上的压降
    - 故$X_T=\frac{V_s\%}{100}×\frac{V_N^2}{S_N}$
    - $V_s\%$只是一种表示方式，比如短路电压是15%，则$V_s\%$=15
    - 容量是kVA，电压是kV，此时的结果，单位为$k\Omega$，转化为欧姆$\Omega$应乘$10^3$

- 变压器的空载实验
    - 进行空载实验时，将一侧绕组（通常是**高压侧**）空载，在另一侧绕组施加额定电压，测得变压器的**空载损耗**和**空载电流**

【注】：变压器空载实验之所以是高压侧空载，是因为电压要加到额定值，高压侧获取难度大，因此加到低压侧

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/X1BQOL%5BG%606~I_XB%7D7NLPLFS.jpg)

1. 空载实验确定电导
    - 空载电流小，忽略空载铜损
    - 空载损耗=额定电压时的铁心损耗
    - $\Delta P_{Fe}=\Delta P_0$
    - 故$G_T=\frac{\Delta P_0}{V_N^2}$
    - 电导是励磁电阻，励磁电阻对应铁耗
    - 空载损耗是kW，电压是kV，此时的结果，单位为$mS$，转化为西门子S，应乘$10^{-3}$
2. 空载实验确定电纳
    - 空载电流的有功分量很小
    - 空载电流=额定电压时的无功电流
    - 故$B_T=\frac{I_0\%}{100}×\frac{S_N}{V_N^2}$
    - 电纳对应励磁电抗
    - 容量是kVA，电压是kV，此时的结果，单位为$mS$，转化为西门子S应乘$10^{-3}$

==Q：变压器变比和匝数比的关系怎样？==

- 变比=高压侧额定电压/低压侧额定电压，是两侧**空载线电压**的比值
- 对于Y,y和D,d接法的变压器：$k_T=V_{1N}/V_{2N}=w_1/w_2$
- 对于Y,d接法的变压器：$k_T=V_{1N}/V_{2N}=\sqrt{3}w_1/w_2$
- 根据电力系统运行调节的要求，变压器不一定工作在主抽头上。因此，变压器运行中的实际变比，应是工作时两侧绕组实际抽头的空载线电压之比

## 三绕组变压器和自耦变压器的等值电路和参数
### 三绕组变压器的特点
==Q：较双绕组变压器而言，三绕组变压器有哪些特点？==

- 三绕组变压器每个绕组的容量不一定相等，常见的有100/100/100，100/100/50，100/50/100三种
- 忽略励磁电流，三侧电流之和为零，不具有双绕组变压器的变比关系

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/@2%5D5SCYEW%7B@W%5DKYG6OT4A.png)

【注】

- 三绕组变压器的高压绕组都在外层，这是出于绝缘考虑。
- 三绕组变压器可以将三个不同电压等级的电网相互连接起来。
- 不要混淆了三绕组变压器和三相变压器

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/I_KB9LZL1W1%7DXWNY6ZVA4E.jpg)

### 三绕组变压器的参数
==Q：三绕组变压器的参数如何确定呢？==

- 三绕组变压器的电导和电纳通过一次空载实验可以求得。即低压侧加额定电压，另外两侧开路，得到空载损耗和空载电流，然后按照双绕组变压器的公式就可以求得电导和电纳
- 对于**三个绕组容量相同**的变压器，短路实验，我们是要两两绕组做3次的，这时候就一侧加额定电流，另外一侧短路、一侧开路。得到两两绕组短路实验时的短路损耗和短路电压百分比
  
![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/@P8C~8%25BHMWT18@EKLSNEZC.png)

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/EJNKOOJ3IH0%7B85WB%5D%5DA%5D@NE.png)

- 对于**三个绕组的额定容量不相等**的变压器，在做短路实验时将受到较小容量绕组额定电流的限制。此时必须对原始的实验数据做折算

【注】：忽略励磁绕组，三侧电流之和为零，不具有双绕组变压器的变比关系。这是理解的关键，容量小的那侧达到额定值，容量大的那侧还没达到。

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/@9K2W8KD%25W%60%601%5D%60D@V%5BK8PA.jpg)

故短路损耗折算后，再计算电阻值

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/N@8DXQ6S@B8$%5DJX4948C6JT.png)

故短路电压无需折算，仍按原来步骤求电抗即可

==Q：如果仅仅已知最大短路损耗，该如何求？==

- 最大短路损耗是指两个100%容量绕组流过额定电流的损耗总和
- 变压器的设计原则：按电流密度相等选择各绕组导线截面积
- $R_{T (100\%)}=\frac{\Delta P_{smax}V_N^2}{2S_N^2}×10^3$
- $R_{T (50\%)}=2R_{T (100\%)}$
- $R_{T (66.7\%)}=\frac{100}{66.7}R_{T (100\%)}$

### 自耦变压器的参数和数学模型
==Q：自耦变压器和普通变压器有何不同？==

- 自耦变压器同常规变压器的原理是一样的，但会有一部分绕组是共用的
- 自耦变压器的短路实验和普通变压器相同，等值电路也相同
- 但需要注意，自耦变压器的短路实验数据中的短路电压百分比没有折算，所以这个时候需要按容量的比值进行相应的折算（短路损耗仍然按照容量比值的平方）。

<center>
![ ](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/E7I3GG0F3HSH1HVR~1$C1.jpg){width="300"}
</center>

【注】自耦变压器的优缺点

- 优点：成本低、便于运输安装、铜损和铁损少
- 缺点：短路电流增大，两侧绕组有电联系（不像普通的三绕组变压器只有磁联系），因此均需装设避雷器

### 例题
![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/%E6%BC%94%E8%8D%89-37.jpg)

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/Z@8K_Y%7B%25A%25F0I@5Y%5BJIPZB7.jpg)

## 变压器的简化等值电路
==Q：对于稳态分析，变压器的等值电路能做怎样的简化？==

- 变压器的电导和电纳是描述空载损耗的参数，空载损耗仅同电压有关
- 电力系统中的变压器，其机端电压大多在额定值附近
- 于是，在稳态分析中可以认为励磁功率近似恒定不变
- S即为额定电压下的励磁功率，相当于把励磁电抗当作运算负荷

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/6624BD2N8HO52_T1VMV%7B6.png)

【注】；这个变压器模型依然存在问题，由于变比的存在，等值电路里依然存在理想变压器，有**磁耦合**，计算困难（特别是对于实际的复杂电力系统）

## 变压器的$\pi$型等值电路
==Q：如何消除变压器模型中的理想变压器，把等值电路变成一个纯电路？==

- 等值的本质是对外等效，即二端口特性的等效
- 列出原始方程，对其进行变换，得到等效方程

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/1%5DM%607LWYV%5B~ZB%5B4~2%5DE2L.png)

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/3RZ5M$@%7B%5B9XTF4AD35J34TK.png)

==Q：变压器的型等值电路具有哪些特点？==

- **去掉了磁耦合，适合计算机计算**：由此求出两侧的电气量即是两侧电压等级下的数值，无须再归算。对于复杂电力系统最为合适。
- 三阻抗是**数学等值**，没有任何物理含义。
- 三阻抗均与**变比K**有关。
- 两并联阻抗**符号相反**，负号出现在电压等级**高侧**（因为按照K:1，K>1，故$Z_1=\frac{Z_T}{1-K}<0$）
- **三阻抗的和为零**，构成谐振三角形

==Q：三绕组变压器的$\pi$型等值电路是怎样？==

- 采用2组双绕组变压器的$\pi$型等值电路
- $K_{12}=\frac{U_{t1}}{U_{t2}}$  $K_{13}=\frac{U_{t1}}{U_{t3}}$

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/20230227145251.png)



## 电力系统负荷的基本概念及模型
### 负荷的概念
==Q：什么是电力系统的负荷？供电负荷？发电负荷？==

- 电力用户的用电设备所消耗的电功率总和称为负荷，也称为**综合用电负荷**，是一种把不同地区和不同性质用户加起来的综合。
- **供电负荷**是综合用电负荷+电网功率损耗，即电厂供给电网的功率
- **发电负荷**是供电负荷+厂用电功率

【注】notes：

1. 负荷指电功率，包括有功和无功。
2. 负荷的性质由其用电设备决定，包括感应电机、同步电机、电热、整流装置等。不同行业的负荷情况不同。

### 负荷曲线及用途
==Q：什么是负荷曲线？==

- 负荷曲线是描述系统负荷随时间变化规律的曲线。按负荷种类可分为有功和无功负荷曲线；按时间尺度可分为日负荷曲线和年负荷曲线

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/GMCY9%7B_K7C%7D4@PCB%5D%253M09X.jpg)

==Q：日负荷曲线有什么用？有哪些指标？取决于什么？==
 
- 日负荷曲线是安排日发电计划和确定系统运行方式的依据
- 日最大负荷称为**峰荷**，最小值称为**谷荷**，总消耗量的小时平均值称为**日平均负荷**
- $P_{av}=\frac{W_d}{24}=\frac{1}{24}\int_0^{24}Pdt$
- 负荷曲线的变化规律取决于负荷的性质、企业的生产及作息、地理位置、气候、生活习惯等
- 负荷率：平均负荷与峰荷之比
- 最小负荷系数：谷荷和峰荷的比值

==Q：为什么系统的最大负荷总是小于各用户的最大负荷之和？最小负荷总是大于最小负荷之和？==

- 因为电力系统各用户的日最大负荷和日最小负荷不会在同一时间出现

==Q：年负荷曲线有什么用？有哪些指标？==

- **年最大负荷曲线**是描述一年内每月（或每日）最大有功功率负荷的变化情况。主要用来安排发电机设备的检修计划，也为制定电厂的扩建、新建计划提供依据。
- **年持续负荷曲线**是按一年中系统负荷的数值大小及持续小时数，顺序排列而成的曲线，常用来安排发电计划和进行可靠性估算。

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/GCPYQIF490DQQX%25H_LMN~R6.jpg)

【注】：重点概念

- 最大负荷（年）利用小时数：假设负荷等于最大值，消耗掉全年耗电量的时间称为最大负荷年利用小时数。
    - $T_{max}=\frac{W_y}{P_{max}}=\frac{1}{P_{max}}\int_0^{8760}Pdt$

### 负荷的特性及模型
==Q：什么是综合负荷？==

- 综合负荷顾名思义是指一定数量的各类用电设备和相关变配电设备的组合。综合负荷是一种广义的概念，可能代表一个企业，可能代表一个地区（从母线向外看的全部）。
- 综合符合特性是指综合负荷的有功和无功功率随运行参数（主要是电压和频率）变化的特性。
- **动态负荷特性**反映电压和频率变化时负荷功率随时间变化的规律
- **静态负荷特性**反映稳态下负荷功率随电压和频率的关系。（$f_1\rightarrow p_1,f_2\rightarrow p_2$对应关系）

==Q：你是否清楚动态和静态负荷特性的本质区别？==

1. 负荷的静态特性是一种负荷大小与电压和频率的稳态对应关系
2. 负荷的动态特性表示的是当电压或频率变化时的负荷的瞬态特性，往往需要微分方程去描述

==Q：如何描述负荷的静态特性？==

- 电压静态特性：频率维持额定值不变，负荷功率与电压的关系
- 频率静态特性：电压维持额定值不变，负荷功率与频率的关系

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/9ZWLW9%5DG61NAOQW7Q%5DQSQUV.jpg)
  
- 随着电压的升高，负荷的有功和无功都会增大
- 随着频率的升高，负荷的有功会增大，但无功会降低
- 思考原因！！！！！！！！先空着

==Q：如何理解负荷建模的难度？（扩展）==

1. 电力系统的负荷种类繁多，实际综合负荷由许许多多各不相同的用电设备集合而成。（复杂性）
2. 负荷组成以及负荷大小都是随着时间随机变化的。（随机性）
3. 很多负荷具有不确定性，负荷随电压及频率变化而变化。（不确定性）
4. 工程实际中对负荷的组成缺乏准确数据。（不准确性）

【注】：因此实际中常采用大数据、人工智能等方法挖掘历史数据、预测未来变化。

==Q：对于不同问题的分析，负荷模型如何选取？==

- 潮流计算分析：恒功率
- 调频调压分析：线性化的静态特性
- 短路电流计算：恒阻抗支路、或者含电压源的阻抗支路（异步电动机）
- 稳定性分析：恒阻抗、或者恒阻抗和异步电动机的组合（根据问题性质的不同而不同）

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/F9%25QUF@%5BP%25Z%7BS@7XWZ%25PCFW.jpg)


## 同步发电机的稳态模型及运行特性
### 发电机的稳态模型
==Q：隐极发电机的稳态模型是怎样？==

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/20230228085523.png)

- 电抗后电势模型
- $\varphi$：外功率因数角，与负载有关
- $\theta$：功角，反映发电机向外的电磁功率
- $\psi$：内功率因数角，决定电枢反映性质，判断去磁交磁增磁

==Q：凸极发电机稳态模型是怎样？==

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/20230228094001.png)

==Q：电机学中学到的凸极发电机稳态模型能直接用吗？==

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/20230228094145.png)

- 不能直接用，关心的是机端电压和机端电流的关系，要考虑用一个图来表示，因此引入虚拟内电势
- 通过构造虚拟内电势的方法，将dq轴等值电路合二为一
- 因此实现隐极和凸极电机等值电路形式的统一：电抗后电势

 ![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/20230228094609.png)

### 发电机的运行特性
==Q：发电机的功角特性是什么样？==

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/Y%7BGPNRFU_%60B0~%7BBZJOI~6T.jpg)

【注】必须理解和记住的

- 隐极和凸级发电机的相量图
- 隐极发电机的功率表达式，凸极发电机的有功功率（电磁功率）表达式
- 隐极和凸机发电机的功角特性曲线（有功）
- 凸机发电机电磁功率最大值对应的功角，小于90&deg;

==Q：发电机的运行受到哪些约束的限制？==（这里指隐极机。凸极机过于复杂不考虑）

1. 定子绕组温升约束
    - 定子温升、定子电流、视在功率是一回事
2. 励磁绕组温升约束
    - 励磁绕组温升取决于励磁电流，即内电势
3. 原动机出力约束
    - 即有功功率约束
4. 其他
    - 进相时，静态稳定性、端部温升等（了解即可）

【注】图中变量都是标幺值，相量都乘$\frac{U_N}{x_d}$

![](https://image-bed-1316693164.cos.ap-shanghai.myqcloud.com/NF@TU~$6DD15%5B%5B47R%5D5T7T.jpg)

