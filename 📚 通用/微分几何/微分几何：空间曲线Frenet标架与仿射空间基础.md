---
title: "微分几何：空间曲线Frenet标架与仿射空间基础"
date: 2026-04-03
subject: 其他
subtopic: 微分几何
tags: [微分几何, Frenet标架, 曲率, 仿射空间, 坐标变换]
consolidated: true
---

# 微分几何：空间曲线Frenet标架与仿射空间基础

# 微分几何：空间曲线Frenet标架与仿射空间基础

## 第一部分：空间曲线的Frenet标架

### 核心概念：Frenet标架
**Frenet标架**是描述空间曲线上某点局部性质的正交基，是曲线微分几何的重要工具。

#### 定义
设 $r:[a, b]\to \mathbb{R}^3$ 是一条可微 $C^2$ 曲线 $C$ 的==弧长参数化==。
在点 $r(s)$ 处，Frenet标架由以下三个相互正交的单位向量构成：
- **切向量** $\boldsymbol{\alpha}(s)$：沿曲线切线方向，$\boldsymbol{\alpha}(s) = \dot{r}(s)$。
- **主法向量** $\boldsymbol{\beta}(s)$：指向曲线弯曲方向，$\boldsymbol{\beta}(s) = \frac{\ddot{r}(s)}{|\ddot{r}(s)|}$（当 $\ddot{r}(s) \neq 0$）。
- **副法向量** $\boldsymbol{\gamma}(s)$：$\boldsymbol{\gamma}(s) = \boldsymbol{\alpha}(s) \times \boldsymbol{\beta}(s)$。

==考试重点：Frenet标架下的切向量、法向量、副法向量的定义及其几何意义==

### 关键公式：再参数化下的曲率

**定理（再参数化下的曲率表达式）**
设 $r$ 为弧长参数化，$q$ 为正则再参数化（即 $q(t) = r(s(t))$，且 $\dot{q}(t) \neq 0$），则曲率 $k(s)$ 的表达式为：
$$
k(s) = \frac{\left| \ddot{q}^{\perp}(t) \right|_2}{\left| \dot{q}(t) \right|_2^2}
$$
其中 $\ddot{q}^{\perp}(t)$ 是 $\ddot{q}(t)$ 垂直于 $\dot{q}(t)$ 的分量。

#### 推导要点
参数变换为 $s = s(t)$，且 $\frac{ds}{dt} = |\dot{q}(t)|_2$。
- 一阶导数关系：$\dot{q}(t) = \dot{r}(s) \frac{ds}{dt}$
- 二阶导数关系：$\ddot{q}(t) = \ddot{r}(s) \left(\frac{ds}{dt}\right)^2 + \dot{r}(s) \frac{d^2 s}{dt^2}$
由于 $\dot{r}(s) \perp \ddot{r}(s)$，可得 $\ddot{q}^{\perp}(t) = \left(\frac{ds}{dt}\right)^2 \ddot{r}(s)$。
代入定义即得上述公式。

==考试重点：再参数化后如何计算曲率==

### 与Frenet标架相关的平面
以Frenet标架中的向量为法向量，可以定义三个相互垂直的平面：
- **法平面**：以 $\boldsymbol{\alpha}(s)$（切向量）为法向量。
- **从切平面**：以 $\boldsymbol{\beta}(s)$（主法向量）为法向量。
- **密切平面**：以 $\boldsymbol{\gamma}(s)$（副法向量）为法向量。

==考试重点：三种平面的法向量分别是谁==

### 挠率
**挠率** $\tau(s)$ 衡量曲线偏离平面曲线的程度，定义为副法向量变化率在副法向量方向上的分量：
$\tau(s) = -\dot{\boldsymbol{\gamma}}(s) \cdot \boldsymbol{\beta}(s)$。
它与Frenet-Serret公式共同完整描述了空间曲线的局部几何。

## 第二部分：仿射空间中的几何学

### 核心概念：仿射空间

#### 定义
设 $\mathcal{A}^{n}$ 为非空集合。若有映射：
$$
\mathcal{A}^{n} \times \mathcal{A}^{n} \mapsto \mathbb{R}^{n}, \quad (A, B) \mapsto \overrightarrow{AB}
$$
满足：
1. $\forall v \in \mathbb{R}^{n}, A \in \mathcal{A}^{n}$，存在 $B \in \mathcal{A}^{n}$ 使得 $\overrightarrow{AB} = v$。
2. $\overrightarrow{AB} + \overrightarrow{BC} = \overrightarrow{AC}$（对任意 $A, B, C \in \mathcal{A}^{n}$）。
则称 $\mathcal{A}^{n}$ 为 $n$ 维**仿射空间**。

### 仿射空间中的几何对象

#### 直线
设 $\mathcal{A}^{3}$ 为三维仿射空间。其非空子集 $l$ 称为**直线**，若存在点 $A \in l$ 和非零向量 $v \in \mathbb{R}^{3}$，使得
$$
l = \{ B \in \mathcal{A}^{3} \mid \overrightarrow{AB} = k v, \, k \in \mathbb{R} \}.
$$
称 $l$ 为过点 $A$ 以 $v$ 为方向的直线。

#### 平面
$\mathcal{A}^{3}$ 的非空子集 $\pi$ 称为**平面**，若存在点 $A \in \pi$ 和两个线性无关的向量 $v, w \in \mathbb{R}^{3}$，使得
$$
\pi = \{ B \in \mathcal{A}^{3} \mid \overrightarrow{AB} = k v + p w, \, (k, p) \in \mathbb{R}^{2} \}.
$$
称 $\pi$ 为过点 $A$ 并由 $v, w$ 张成的平面。

### 仿射坐标系与坐标变换

#### 仿射坐标系
在 $\mathcal{A}^{n}$ 上选定一点 $O$（原点）和 $\mathbb{R}^{n}$ 上的一组基 $\{e_i\}$，则 $\mathcal{A} = \{O, e_i\}$ 构成一个**仿射坐标系**。
存在双射 $\varphi_{\mathcal{A}}$：
$$
\varphi_{\mathcal{A}}: \mathcal{A}^{n} \rightarrow \mathbb{R}^{n}, \quad A \longmapsto (x^{1}, \dots, x^{n}),
$$
其中 $\overrightarrow{OA} = \sum_{i=1}^{n} x^{i} e_i$。$(x^{1}, \dots, x^{n})$ 称为点 $A$ 在坐标系 $\mathcal{A}$ 下的坐标。

#### 仿射坐标变换
考虑两个仿射坐标系 $\mathcal{A} = \{O, e_i\}$ 和 $\mathcal{A}' = \{O', f_i\}$。它们之间的关系由下式给出：
$$
\overrightarrow{OO'} = \sum_{i=1}^{n} a^{i} e_i, \quad e_i = \sum_{j=1}^{n} T_i^{\, j} f_j.
$$
用矩阵形式表示为：
$$
(e_1, e_2, \dots, e_n) = (f_1, f_2, \dots, f_n) T,
$$
其中 $T$ 是变换矩阵，其第 $i$ 列是 $e_i$ 在基 $\{f_j\}$ 下的坐标。

**坐标变换公式**：设点 $A$ 在 $\mathcal{A}$ 下的坐标为 $(x^{1}, \dots, x^{n})$，在 $\mathcal{A}'$ 下的坐标为 $(y^{1}, \dots, y^{n})$，则：
$$
\begin{pmatrix} y^{1} \\ y^{2} \\ \vdots \\ y^{n} \end{pmatrix} = T^{\top} \begin{pmatrix} x^{1} - a^{1} \\ x^{2} - a^{2} \\ \vdots \\ x^{n} - a^{n} \end{pmatrix}.
$$
或分量形式：$y^{j} = \sum_{i=1}^{n} T_i^{\, j} (x^{i} - a^{i})$。
- 当 $\det(T) > 0$ 时，两个坐标系**同向**；反之称为**反向**。

### 仿射空间中的拓扑与函数

#### 拓扑
设 $\mathcal{A} = \{O, e_i\}$ 是 $\mathcal{A}^{n}$ 的一个仿射坐标系。$\mathcal{A}^{n}$ 的子集 $U$ 称为**开集**，如果它在坐标映射 $\varphi_{\mathcal{A}}$ 下的像 $\varphi_{\mathcal{A}}(U)$ 是 $\mathbb{R}^{n}$ 中的开集。

**引理**：一个子集 $B \subset \mathcal{A}^{n}$ 在某个仿射坐标系下是开集，当且仅当它在任意仿射坐标系下都是开集。
（证明利用坐标变换映射 $\varphi_{\mathcal{A}'} \circ \varphi_{\mathcal{A}}^{-1}$ 是 $\mathbb{R}^{n}$ 到自身的同胚，从而保持开集性质。）

#### 函数/标量场
设 $U$ 是 $\mathcal{A}^{n}$ 的一个开区域，$f: U \to \mathbb{R}$ 是一个函数。给定仿射坐标系 $\mathcal{A}$，可以定义读取函数 $f_{\mathcal{A}} = f \circ \varphi_{\mathcal{A}}^{-1}: \varphi_{\mathcal{A}}(U) \subset \mathbb{R}^{n} \to \mathbb{R}$。

**引理**：设 $U$ 为 $\mathcal{A}^{n}$ 中开区域，$f$ 为 $U$ 上函数，则以下等价：
1.  $f$ 是连续的（按仿射坐标系诱导的拓扑）。
2.  在某个仿射坐标系 $\mathcal{A}$ 中读取的函数 $f_{\mathcal{A}}$ 连续。
3.  在任意仿射坐标系中读取的函数均连续。

## 关联与总结
- **Frenet标架**提供了分析空间曲线局部微分性质的强有力工具，其核心是曲率和挠率。
- **仿射空间**为研究几何对象（点、直线、平面）及其坐标表示提供了更一般的框架，它不依赖于内积（度量）结构，是欧氏空间和后续[[微分流形]]概念的基础。
- 两者都属于**微分几何**的研究范畴，前者侧重于曲线的局部微分性质，后者侧重于更基础的几何空间结构。
- ==考试容易考 Frenet标架、曲率表达式、三平面法向量、仿射坐标变换公式==。
