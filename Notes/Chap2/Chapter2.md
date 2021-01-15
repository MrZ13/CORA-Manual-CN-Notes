# Chapter2. Set Representations and Operations


- [Chapter2. Set Representations and Operations](#chapter2-set-representations-and-operations)
  - [2.1 Set Operations](#21-set-operations)
    - [2.1.1 Basic Set Operations](#211-basic-set-operations)
      - [2.1.1.1 mtimes](#2111-mtimes)
      - [2.1.1.2 plus](#2112-plus)
      - [2.1.1.3 cartProd](#2113-cartprod)
      - [2.1.1.4 convHull](#2114-convhull)
      - [2.1.1.5 quadMap](#2115-quadmap)
      - [2.1.1.6 and](#2116-and)
      - [2.1.1.7 or](#2117-or)
    - [2.1.2 Predicates](#212-predicates)
      - [2.1.2.1 in](#2121-in)
      - [2.1.2.2 isIntersecting](#2122-isintersecting)
      - [2.1.2.3 isFullDim](#2123-isfulldim)
      - [2.1.2.4 isequal](#2124-isequal)
      - [2.1.2.5 isempty](#2125-isempty)
    - [2.1.3 Set Properties](#213-set-properties)
      - [2.1.3.1 center](#2131-center)
      - [2.1.3.2 dim](#2132-dim)
      - [2.1.3.3 norm](#2133-norm)
      - [2.1.3.4 vertices](#2134-vertices)
      - [2.1.3.5 volume](#2135-volume)
    - [2.1.4 Auxiliary Operations](#214-auxiliary-operations)
      - [2.1.4.1 cubMap](#2141-cubmap)
      - [2.1.4.2 enclose](#2142-enclose)
      - [2.1.4.3 enclosePoints](#2143-enclosepoints)
      - [2.1.4.4 generateRandom](#2144-generaterandom)
      - [2.1.4.5 randPoint](#2145-randpoint)
      - [2.1.4.6 reduce](#2146-reduce)
      - [2.1.4.7 supportFunc](#2147-supportfunc)
      - [2.1.4.8 plot](#2148-plot)
      - [2.1.4.9 project](#2149-project)
  - [2.2 Set Representations](#22-set-representations)
    - [2.2.1 Basic Set Representations](#221-basic-set-representations)
      - [2.2.1.1 Zonotopes](#2211-zonotopes)
          - [1.n维空间上的zonotope定义](#1n维空间上的zonotope定义)
          - [2.CORA中zonotope的声明方式](#2cora中zonotope的声明方式)
          - [3.代码示例](#3代码示例)
          - [4.zonotope的产生过程](#4zonotope的产生过程)
      - [2.2.1.2 Intervals（区间）](#2212-intervals区间)
          - [1.n维空间上的interval定义](#1n维空间上的interval定义)
          - [2.CORA中interval的声明方式](#2cora中interval的声明方式)
          - [示例](#示例)
      - [2.2.1.3 Ellipsoids（椭圆体）](#2213-ellipsoids椭圆体)
          - [1.nxn空间上Ellipsoids的定义](#1nxn空间上ellipsoids的定义)
          - [2.CORA中ellipsoids的声明方式](#2cora中ellipsoids的声明方式)
          - [3.示例](#3示例)
      - [2.2.1.4 MPT Polytopes（MPT多面体）](#2214-mpt-polytopesmpt多面体)
      - [2.2.1.5 Polynomial Zonotopes（多项的zonotope)](#2215-polynomial-zonotopes多项的zonotope)
      - [2.2.1.6 Capsules（胶囊）](#2216-capsules胶囊)
      - [2.2.1.7 Zonotope Bundles (zonotope束)](#2217-zonotope-bundles-zonotope束)
      - [2.2.1.8 Constrained Zonotopes](#2218-constrained-zonotopes)
      - [2.2.1.9 Probabilistic Zonotopes](#2219-probabilistic-zonotopes)
    - [2.2.2 Auxiliary Set Representations](#222-auxiliary-set-representations)
      - [2.2.2.1 Constrained Hyperplane](#2221-constrained-hyperplane)
      - [2.2.2.2 Halfspace](#2222-halfspace)
      - [2.2.2.3 Level Sets](#2223-level-sets)
    - [2.2.3 Set Representations for Range Bounding](#223-set-representations-for-range-bounding)
      - [2.2.3.1 Taylor Models](#2231-taylor-models)
      - [2.2.3.2 Affine](#2232-affine)
      - [2.2.3.3 Zoo](#2233-zoo)


## 2.1 Set Operations

### 2.1.1 Basic Set Operations

#### 2.1.1.1 mtimes



#### 2.1.1.2 plus



#### 2.1.1.3 cartProd



#### 2.1.1.4 convHull



#### 2.1.1.5 quadMap



#### 2.1.1.6 and



#### 2.1.1.7 or



### 2.1.2 Predicates

#### 2.1.2.1 in



#### 2.1.2.2 isIntersecting



#### 2.1.2.3 isFullDim



#### 2.1.2.4 isequal



#### 2.1.2.5 isempty



### 2.1.3 Set Properties

#### 2.1.3.1 center



#### 2.1.3.2 dim



#### 2.1.3.3 norm



#### 2.1.3.4 vertices



#### 2.1.3.5 volume



### 2.1.4 Auxiliary Operations

#### 2.1.4.1 cubMap



#### 2.1.4.2 enclose



#### 2.1.4.3 enclosePoints



#### 2.1.4.4 generateRandom



#### 2.1.4.5 randPoint



#### 2.1.4.6 reduce



#### 2.1.4.7 supportFunc



#### 2.1.4.8 plot



#### 2.1.4.9 project



## 2.2 Set Representations

> 可达性分析对集合表示的要求：
>
> - 足以能够精准得描述可达性集合
> - 需要能够保证运行效率和可伸缩性



CORA支持内部某些集合表示之间进行相互转化，只需要将一个集合的实例交给另一个集合的构造器即可。下图为不同集合表示方法之间进行相互转换的关系。

> o: over-approximatation(超精度转换)
>
> e: exact conversion(精准转换)

![](pics/pic2-1.jpg)



集合表示转换示例

```matlab
% 创建 zonotope 对象
zono = zonotope([1 2 1;0 1 -1]);

% 转换为其他的集合表示
% 转换为interval(o)
int = interval(zono);
% 转换为polytope(e)
poly = mptPolytope(zono);
```



### 2.2.1 Basic Set Representations

#### 2.2.1.1 Zonotopes

> zonotope是一种紧凑的(compact)，用于表示高维空间中的集合。实际上，zonotope可以被看做数个线段的闵可夫斯基加和。
>
> tips：实际上，zonotope可以看作为数个变量的可能取值，通过一个中心点+数个噪声变量的形式表示



##### 1.n维空间上的zonotope定义

![](pics/pic2-2.jpg)

> c：中心点
>
> g<sup>(i)</sup>：generator(发生器)



##### 2.CORA中zonotope的声明方式

![](pics/pic2-3.jpg)

> G = [g(1),g(2),......g(p)]



##### 3.代码示例

```matlab
% construct zonotope 
c = [1;1]; 
G = [1 1 1; 1 -1 0];
zono = zonotope(c,G);
```



##### 4.zonotope的产生过程

> 以3中的定义为例：
>
> 1. 以c点作为中心点
> 2. 向(1,1),(-1,-1)两个方向进行一次移动，得到一条线段
> 3. 线段上的所有点向(1,-1),(-1,1)两个方向进行一次移动，得到一个正方形
> 4. 正方形上的所有点向(1,0),(-1,0)两个方向进行一次移动，得到一个六边形

![](pics/pic2-4.jpg)



#### 2.2.1.2 Intervals（区间）

> interval(区间)，是一个n维空间上的连通子集，使用上下界来进行定义



##### 1.n维空间上的interval定义

![](pics/pic_interval_1.jpg)



##### 2.CORA中interval的声明方式

![](pics/pic_interval_2.jpg)

> 注意，上下界均可以不止一个，以便表示不同维度中的interval



###### 示例

```matlab
% construct interval 
% 注意，-2~4为一组，-1~3为一组
lb = [-2; -1];
ub = [4; 3];
int = interval(lb,ub);
```

![](pics/pic_interval_3.jpg)



#### 2.2.1.3 Ellipsoids（椭圆体）

> 椭圆体是一个R<sup>n</sup>维度上的几何学对象，由一个中心q和一个正的、半正定的对称矩阵定义



##### 1.nxn空间上Ellipsoids的定义

![](pics/pic-ellpi-1.jpg)

![](pics/pic-ellpi-2.jpg)

> 上述两种定义方式等价



##### 2.CORA中ellipsoids的声明方式

![](pics/pic-ellpi-3.jpg)

##### 3.示例

```matlab
% construct 
ellipsoid Q = [13 7; 7 5]; 
q = [1; 2];
E = ellipsoid(Q,q);
```

![](pics/pic-ellpi-4.jpg)



#### 2.2.1.4 MPT Polytopes（MPT多面体）

> 表示多面体的方法有两种：
>
> 1. 半空间表示法（H-repre）
> 2. 顶点表示法（V-repre)



##### 1.定义

###### 2.2.1.4.1 H-repre

> 半空间表示法通过多个半空间交集的形式表示多面体

多面体P的定义：``H(i): P = H(1) ∩ H(i) ∩ . . . ∩ H(q)``



==半空间==

> 一个半空间是使用超平面，二等分一个n维的欧几里得空间得到的

超平面的定义：``S := {x|cTx = d}, c ∈ Rn, d ∈ R``

其中

- C:超平面的法向量 
- d:超平面上任意一点与法向量的纯量积

根据超平面，可得半空间的定义：``H := {x|cTx ≤ d}``



==凸多面体(convex polytope)的定义==

一个凸的多面体P是q个半空间的有界集合，定义如下：

![](pics/pic_mpt_h1.jpg)

###### 2.2.1.4.2 V-repre

使用顶点表示的凸多面体是一个在欧几里得空间中有限点集构成的凸包，这些点即是凸多面体的顶点，以 `v(i) ∈ Rn`的形式表示

###### 使用顶点表示的凸包(convex hull)

![](pics/pic-mpt-v1.jpg)



2.2.1.4.1与2.2.1.4.2中提到的两种表示法的图示如下:

![](pics/pic-mpt-1.jpg)



##### 2.CORA中polytope的定义方式

![](pics/pic-mpt-2.jpg)

> 这两种分别对应着V-repre和H-repre



##### 3.示例

```matlab
% construct polytope (halfspace rep.) 
C = [1 0 -1 0 1; 0 1 0 -1 1]’; 
d = [3; 2; 3; 2; 1];
poly = mptPolytope(C,d);

% construct polytope (vertex rep.) 
V = [-3 -3 -1 3; -2 2 2 -2]; 
poly = mptPolytope(V’);
```

![](pics/pic-mpt-3.jpg)



#### 2.2.1.5 Polynomial Zonotopes（多项的zonotope)

> 多项式Zonotope是一种非凸的集合表示



##### 1.R<sup>n</sup>空间上多项式Zonotope的定义

![](pics/pic-pzono-1.jpg)

> - c：与zonotope一样，中心点
> - G：dependent generator   ∈ R<sup>nxh</sup>
> - Gi：independent generator ∈ R<sup>nxq</sup>
> - E：指数矩阵 ∈ N<sup>pxh</sup><sub>0</sub>



tips: 多项Zonotope的特点

- 可以表示非凸集合
- 在二次和更高的函数运算下都是封闭的

故适合用于可达性分析



##### 2.CORA中多项式Zonotope的表达方式

![](pics/pic-pzono-2.jpg)



##### 3.示例

```matlab
% construct polynomial zonotope 
c = [4;4]; 
G = [2 1 2; 0 2 2]; 
expMat = [1 0 3;0 1 1]; 
Grest = [1;0];
pZ = polyZonotope(c,G,Grest,expMat);
```

![](pics/pic-pzono-3.jpg)



#### 2.2.1.6 Capsules（胶囊）

> 胶囊被定义为线段集合和球体的闵可夫斯基和



##### 1.Capsules在R<sup>n</sup>空间上的定义

![](pics/pic-cap-1.jpg)

> - c：中心
> - g：generator
> - r：半径



##### 2.CORA中Capsules的表示

![](pics/pic-cap-2.jpg)

##### 3.示例

```matlab
% construct capsule 
c = [1;2]; 
g = [2;1]; 
r = 1;
C = capsule(c,g,r);
```

![](pics/pic-cap-3.jpg)

> tips：Capsules的计算方式与Zonotope非常类似，同样是计算闵可夫斯基和



#### 2.2.1.7 Zonotope Bundles (zonotope束)









#### 2.2.1.8 Constrained Zonotopes



#### 2.2.1.9 Probabilistic Zonotopes



### 2.2.2 Auxiliary(辅助的) Set Representations

#### 2.2.2.1 Constrained Hyperplane

#### 2.2.2.2 Halfspace

#### 2.2.2.3 Level Sets

### 2.2.3 Set Representations for Range Bounding

#### 2.2.3.1 Taylor Models

#### 2.2.3.2 Affine

#### 2.2.3.3 Zoo