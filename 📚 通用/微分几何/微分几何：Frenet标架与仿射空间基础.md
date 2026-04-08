---
title: "微分几何：Frenet标架与仿射空间基础"
date: 2026-04-08
subject: 其他
subtopic: 微分几何
tags: [微分几何, Frenet标架, 曲率, 仿射几何, 空间曲线]
consolidated: true
---

# 微分几何：Frenet标架与仿射空间基础

# 微分几何：Frenet标架与仿射空间基础

## 第一部分：空间曲线的Frenet标架

### 1.1 Frenet标架的定义

Frenet标架是描述空间曲线上某点局部性质的正交基，是曲线微分几何的核心工具。

- 设 $r:[a, b]\to \mathbb{R}^3$ 是一条可微 $C^2$ 曲线 $C$ 的**弧长参数化**。
- 在点 $r(s)$ 处，Frenet标架由三个相互正交的单位向量构成：
  - **切向量** $\boldsymbol{\alpha}(s)$：沿曲线切线方向，$\boldsymbol{\alpha}(s) = \dot{r}(s)$。
  - **主法向量** $\boldsymbol{\beta}(s)$：指向曲线弯曲方向，$\boldsymbol{\beta}(s) = \frac{\ddot{r}(s)}{|\ddot{r}(s)|}$（当曲率不为零时）。
  - **副法向量** $\boldsymbol{\gamma}(s)$：$\boldsymbol{\gamma}(s) = \boldsymbol{\alpha}(s) \times \boldsymbol{\beta}(s)$。

==考试重点：Frenet标架下的切向量、法向量、副法向量的定义及其几何意义==

### 1.2 再参数化下的曲率表达式（定理2.1）

曲率是描述曲线弯曲程度的量。当曲线不是弧长参数化时，需要利用再参数化公式计算。

- 设 $r$ 为弧长参数化，$q$ 为正则再参数化，参数变换为 $s = s(t)$，且 $q(t) = r(s(t))$。
- 再参数化下的导数关系：
  $$
  \dot{q}(t) = \dot{r}(s(t)) \frac{ds}{dt}
  $$
  $$
  \ddot{q}(t) = \ddot{r}(s(t)) \left(\frac{ds}{dt}\right)^2 + \dot{r}(s) \frac{d^2 s}{dt^2}
  $$
- 由于弧长参数化下 $|\dot{r}(s)| = 1$，可得 $\dfrac{ds}{dt}=|\dot{q}(t)|_2$，且 $\dot{r}(s) \perp \ddot{r}(s)$。
- 由此可推出 $\dot{r}(s)\parallel\dot{q}(t)$，并且 $\ddot{q}(t)$ 的垂直于 $\dot{q}(t)$ 的分量（记为 $\ddot{q}^{\perp}(t)$）满足：
  $$
  \ddot{q}^{\perp}(t) = \left(\frac{ds}{dt}\right)^2 \ddot{r}(s)
  $$
- **曲率 $k(s)$ 的再参数化表达式**：
  $$
  k(s) = \frac{\left| \ddot{q}^{\perp}(t) \right|_2}{\left| \dot{q}(t) \right|_2^2} = \left|\ddot{r}(s)\right|_2
  $$

==考试重点：再参数化后如何计算曲率==

### 1.3 由Frenet标架定义的平面

在曲线上一点，由Frenet标架中的向量可以定义三个相互垂直的平面：

- **法平面**：以 $\boldsymbol{\alpha}(s)$（切向量）为法向量的平面。
- **从切平面**：以 $\boldsymbol{\beta}(s)$（主法向量）为法向量的平面。
- **密切平面**：以 $\boldsymbol{\gamma}(s)$（副法向量）为法向量的平面。

==考试重点：三种平面的法向量分别是谁==

### 1.4 挠率

- 挠率 $\tau(s)$ 描述曲线偏离密切平面的程度，即曲线的扭曲程度。
- 定义：$\dot{\boldsymbol{\gamma}}(s) = -\tau(s) \boldsymbol{\beta}(s)$。
- 对于弧长参数化曲线 $r(s)$，挠率计算公式为：
  $$
  \tau(s) = -\boldsymbol{\gamma}(s) \cdot \dot{\boldsymbol{\beta}}(s) = \frac{(\dot{r}(s), \ddot{r}(s), \dddot{r}(s))}{|\ddot{r}(s)|^2}
  $$
  其中 $(\cdot,\cdot,\cdot)$ 表示混合积。

==考试容易考 Frenet标架、曲率表达式、三平面法向量、挠率定义==

## 第二部分：仿射空间基础

### 2.1 仿射空间的定义

设 $\mathcal{A}^{n}$ 为非空集合。若存在映射：
$$
\mathcal{A}^{n} \times \mathcal{A}^{n} \mapsto \mathbb{R}^{n}, \quad (A, B) \mapsto \overrightarrow{AB}
$$
满足：
1. $\forall v \in \mathbb{R}^{n}, A \in \mathcal{A}^{n}$，存在唯一的 $B \in \mathcal{A}^{n}$ 使得 $\overrightarrow{AB} = v$。
2. $\overrightarrow{AB} + \overrightarrow{BC} = \overrightarrow{AC}$（对任意 $A, B, C \in \mathcal{A}^{n}$）。

则称 $\mathcal{A}^{n}$ 为 $n$ 维**仿射空间**。点 $A$ 加上向量 $v$ 唯一确定点 $B$，记为 $B = A + v$。

### 2.2 直线与平面

设 $\mathcal{A}^{3}$ 为三维仿射空间。

- **直线**：$\mathcal{A}^{3}$ 的非空子集 $l$，若存在点 $A \in l$ 和非零向量 $v \in \mathbb{R}^{3}$，使得
  $$
  l = \{ B \in \mathcal{A}^{3} \mid \overrightarrow{AB} = k v, \, k \in \mathbb{R} \},
  $$
  则称 $l$ 为过点 $A$ 以 $v$ 为方向的直线。
- **平面**：$\mathcal{A}^{3}$ 的非空子集 $\pi$，若存在点 $A \in \pi$ 和两个线性无关的向量 $v, w \in \mathbb{R}^{3}$，使得
  $$
  \pi = \{ B \in \mathcal{A}^{3} \mid \overrightarrow{AB} = k v + p w, \, (k, p) \in \mathbb{R}^{2} \},
  $$
  则称 $\pi$ 为过点 $A$ 并由 $v, w$ 张成的平面。

### 2.3 仿射坐标系与坐标变换

- **仿射坐标系**：在 $\mathcal{A}^{n}$ 上选定一点 $O$（称为**原点**），并在 $\mathbb{R}^{n}$ 上选定一组基 $\{e_i\}$，则称 $\mathcal{A} = \{O, e_i\}$ 为 $\mathcal{A}^{n}$ 上的一个仿射坐标系。
- 存在双射 $\varphi_{\mathcal{A}}$：
  $$
  \varphi_{\mathcal{A}}: \mathcal{A}^{n} \rightarrow \mathbb{R}^{n}, \quad A \longmapsto (x^{1}, \dots, x^{n}),
  $$
  其中 $\overrightarrow{OA} = \sum_{i=1}^{n} x^{i} e_i$。$(x^{1}, \dots, x^{n})$ 称为点 $A$ 在坐标系 $\mathcal{A}$ 下的坐标。

#### 仿射坐标变换公式

考虑两个仿射坐标系 $\mathcal{A} = \{O, e_i\}$ 和 $\mathcal{A}' = \{O', f_i\}$。它们之间的关系由下式给出：
$$
\overrightarrow{OO'} = \sum_{i=1}^{n} a^{i} e_i, \quad e_i = \sum_{j=1}^{n} T_i^{\, j} f_j.
$$
用矩阵形式表示为：
$$
(e_1, e_2, \dots, e_n) = (f_1, f_2, \dots, f_n) T, \quad \text{其中 } T = \begin{pmatrix}
T_1^{\, 1} & T_2^{\, 1} & \dots & T_n^{\, 1} \\
T_1^{\, 2} & T_2^{\, 2} & \dots & T_n^{\, 2} \\
\vdots & \vdots & & \vdots \\
T_1^{\, n} & T_2^{\, n} & \dots & T_n^{\, n}
\end{pmatrix}.
$$

**坐标变换命题**：设点 $A$ 在坐标系 $\mathcal{A}$ 下的坐标为 $(x^{1}, \dots, x^{n})$，在坐标系 $\mathcal{A}'$ 下的坐标为 $(y^{1}, \dots, y^{n})$，则它们之间的关系为：
$$
\begin{pmatrix} y^{1} \\ y^{2} \\ \vdots \\ y^{n} \end{pmatrix} = T^{\top} \begin{pmatrix} x^{1} - a^{1} \\ x^{2} - a^{2} \\ \vdots \\ x^{n} - a^{n} \end{pmatrix}, \quad \text{或分量形式 } y^{j} = \sum_{i=1}^{n} T_i^{\, j} (x^{i} - a^{i}).
$$
- 当变换矩阵的行列式 $\det(T_i^{\, j}) > 0$ 时，称两个坐标系**同向**；反之称为**反向**。

### 2.4 仿射空间中的拓扑与函数

#### 拓扑

设 $\mathcal{A} = \{O, e_i\}$ 是 $\mathcal{A}^{n}$ 的一个仿射坐标系。$\mathcal{A}^{n}$ 的子集 $U$ 称为**开集**，如果它在坐标映射 $\varphi_{\mathcal{A}}$ 下的像 $\varphi_{\mathcal{A}}(U)$ 是 $\mathbb{R}^{n}$ 中的开集。

**引理 3.1**：一个子集 $B \subset \mathcal{A}^{n}$ 在某个仿射坐标系下是开集，当且仅当它在任意仿射坐标系下都是开集。

**证明思路**：坐标变换映射 $\varphi_{\mathcal{A}'} \circ \varphi_{\mathcal{A}}^{-1}: \mathbb{R}^{n} \to \mathbb{R}^{n}$ 是一个仿射变换（可逆线性变换加平移），因而是 $\mathbb{R}^{n}$ 到自身的同胚映射。同胚映射保持开集性质。

#### 函数/标量场

设 $U$ 是 $\mathcal{A}^{n}$ 的一个开区域（连通开集），$f: U \to \mathbb{R}$ 是一个函数。给定一个仿射坐标系 $\mathcal{A} = \{O, e_i\}$，我们可以通过 $f$ 定义一个 $\mathbb{R}^{n}$ 上的 $n$ 元函数 $f_{\mathcal{A}}$：
$$
f_{\mathcal{A}} = f \circ \varphi_{\mathcal{A}}^{-1}: \varphi_{\mathcal{A}}(U) \subset \mathbb{R}^{n} \to \mathbb{R}.
$$
称 $f_{\mathcal{A}}$ 为从坐标系 $\mathcal{A}$ 中**读取** $f$ 得到的函数。

**引理 3.2**：设 $U$ 为 $\mathcal{A}^{n}$ 中开区域，$f$ 为 $U$ 上函数，则以下三点等价：
1.  $f$ 是连续的（按 $\mathcal{A}^{n}$ 上由仿射坐标系诱导的拓扑）。
2.  在某个仿射坐标系 $\mathcal{A}$ 中读取 $f$ 得到的 $n$ 元函数 $f_{\mathcal{A}}$ 连续。
3.  在任意仿射坐标系中读取 $f$ 得到的 $n$ 元函数均连续。

**证明思路**：利用坐标变换映射是连续的双射（同胚）这一性质。

## 第三部分：关联与总结

### 3.1 核心关联

- **Frenet标架** 是研究**曲线**局部微分几何的强有力工具，其定义依赖于曲线的参数化（特别是弧长参数化）。
- **仿射空间** 为曲线、曲面等几何对象提供了一个背景舞台。在仿射空间中，我们可以定义点、向量、直线、平面，并建立坐标系，从而将几何问题代数化。
- 在仿射空间中讨论曲线的Frenet标架时，切向量、法向量等都是在仿射空间伴随的向量空间 $\mathbb{R}^n$ 中取值的。

### 3.2 易混淆点

1.  **仿射空间 vs 向量空间**：仿射空间没有绝对的“原点”，只有点和点之间的位移向量。向量空间有唯一的零元。
2.  **弧长参数化 vs 一般参数化**：Frenet公式在弧长参数化下形式最简洁。一般参数化下的曲率、挠率计算需使用再参数化公式。
3.  **三种平面**：密切平面、法平面、从切平面（或称**法切平面**）由Frenet标架中不同的法向量定义，切勿混淆。
4.  **几何量**：如曲率、挠率、长度、角度等，是几何对象本身固有的，不依赖于坐标系的选取。这与仿射坐标变换下坐标值会改变形成对比。

### 3.3 知识图谱

- 本笔记核心：[[空间曲线的局部理论]] -> [[Frenet标架]]
- 理论基础：[[仿射空间]] -> [[仿射坐标系与坐标变换]]
- 前置知识：[[向量分析]]，[[多元微积分]]
- 后续发展：[[曲面论]]，[[黎曼几何]]

## 附录：关键公式索引

1.  Frenet标架向量：$\boldsymbol{\alpha}, \boldsymbol{\beta}, \boldsymbol{\gamma}$
2.  再参数化曲率：$k(s) = \frac{\left| \ddot{q}^{\perp}(t) \right|_2}{\left| \dot{q}(t) \right|_2^2}$
3.  挠率：$\tau(s) = \frac{(\dot{r}(s), \ddot{r}(s), \dddot{r}(s))}{|\ddot{r}(s)|^2}$
4.  仿射坐标变换：$\vec{y} = T^{\top} (\vec{x} - \vec{a})$
