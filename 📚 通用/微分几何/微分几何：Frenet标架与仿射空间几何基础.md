---
title: "微分几何：Frenet标架与仿射空间几何基础"
date: 2026-03-31
subject: 其他
subtopic: 微分几何
tags: [微分几何, Frenet标架, 曲率, 仿射空间, 坐标系]
consolidated: true
---

# 微分几何：Frenet标架与仿射空间几何基础

# 微分几何：Frenet标架与仿射空间几何基础

## 一、 空间曲线的局部性质：Frenet标架

### 1.1 核心概念

**Frenet标架**是描述空间曲线上某点局部性质的正交基，是曲线微分几何的重要工具。它由三个相互正交的单位向量构成：

- **切向量 (Tangent Vector)**：记为 $\boldsymbol{\alpha}(s)$，方向与曲线在该点的瞬时运动方向一致。
- **主法向量 (Normal Vector)**：记为 $\boldsymbol{\beta}(s)$，方向指向曲线在该点的弯曲方向（曲率中心方向）。
- **副法向量 (Binormal Vector)**：记为 $\boldsymbol{\gamma}(s)$，由 $\boldsymbol{\gamma}(s) = \boldsymbol{\alpha}(s) \times \boldsymbol{\beta}(s)$ 定义，垂直于由切向量和主法向量张成的平面。

==考试重点：Frenet 标架下的切向量、法向量、副法向量的定义及其几何意义==

### 1.2 弧长参数化与Frenet标架

设 $r: [a, b] \to \mathbb{R}^3$ 是一条可微 $C^2$ 曲线 $C$ 的**弧长参数化**，即 $|\dot{r}(s)| = 1$。则 $r(s)$ 处的 Frenet 标架由以下方式定义：
- $\boldsymbol{\alpha}(s) = \dot{r}(s)$
- $\boldsymbol{\beta}(s) = \frac{\ddot{r}(s)}{|\ddot{r}(s)|}$ （当 $\ddot{r}(s) \neq 0$）
- $\boldsymbol{\gamma}(s) = \boldsymbol{\alpha}(s) \times \boldsymbol{\beta}(s)$

### 1.3 再参数化下的曲率表达式（定理2.1）

在实际计算中，曲线常以非弧长参数 $t$ 给出。设 $r(s)$ 为弧长参数化，$q(t) = r(s(t))$ 为正则再参数化，其中 $s(t)$ 为参数变换函数。

**曲率 $k(s)$** 的表达式为：
$$
k(s) = \frac{\left| \ddot{q}^{\perp}(t) \right|_2}{\left| \dot{q}(t) \right|_2^2}
$$
其中 $\ddot{q}^{\perp}(t)$ 是 $\ddot{q}(t)$ 在垂直于 $\dot{q}(t)$ 方向上的分量。

**推导关键步骤**：
1. 导数关系：
   $$
   \dot{q}(t) = \dot{r}(s(t)) \frac{ds}{dt}, \quad \frac{ds}{dt}=|\dot{q}(t)|_2
   $$
   $$
   \ddot{q}(t) = \ddot{r}(s(t)) \left(\frac{ds}{dt}\right)^2 + \dot{r}(s) \frac{d^2 s}{dt^2}
   $$
2. 由于 $\dot{r}(s) \perp \ddot{r}(s)$ 且 $\dot{r}(s)\parallel\dot{q}(t)$，可得：
   $$
   \ddot{q}^{\perp}(t) = \left(\frac{ds}{dt}\right)^2 \ddot{r}(s)
   $$
3. 代入并利用 $|\dot{r}(s)|=1$，最终得到：
   $$
   \frac{\left|\ddot{q}^{\perp}(t)\right|}{|\dot{q}(t)|_2^2} = \left|\ddot{r}(s)\right|_2 = k(s)
   $$

==考试重点：再参数化后如何计算曲率==

### 1.4 三种特定平面及其法向量

在曲线某点处，由 Frenet 标架可以定义三个相互垂直的平面：

- **法平面 (Normal Plane)**：以 $\boldsymbol{\alpha}(s)$（切向量）为法向量。
- **从切平面 (Rectifying Plane)**：以 $\boldsymbol{\beta}(s)$（主法向量）为法向量。
- **密切平面 (Osculating Plane)**：以 $\boldsymbol{\gamma}(s)$（副法向量）为法向量。

==考试重点：三种平面的法向量分别是谁==

### 1.5 挠率

**挠率 (Torsion)** 是描述空间曲线偏离密切平面程度的量，记为 $\tau(s)$。它衡量了曲线的“扭曲”程度。

==考试容易考 Frenet 标架、曲率表达式、三平面法向量==

## 二、 仿射空间中的几何学基础

### 2.1 仿射空间的定义

设 $\mathcal{A}^{n}$ 为非空集合。若有映射：
$$
\mathcal{A}^{n} \times \mathcal{A}^{n} \mapsto \mathbb{R}^{n}, \quad (A, B) \mapsto \overrightarrow{AB}
$$
满足：
1. $\forall v \in \mathbb{R}^{n}, A \in \mathcal{A}^{n}$，存在 $B \in \mathcal{A}^{n}$ 使得 $\overrightarrow{AB} = v$。
2. $\overrightarrow{AB} + \overrightarrow{BC} = \overrightarrow{AC}$（对任意 $A, B, C \in \mathcal{A}^{n}$）。

则称 $\mathcal{A}^{n}$ 为 $n$ 维仿射空间。

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

#### 仿射坐标系
在 $\mathcal{A}^{n}$ 上选定一点 $O$（称为**原点**），并在 $\mathbb{R}^{n}$ 上选定一组基 $\{e_i\}$，则称 $\mathcal{A} = \{O, e_i\}$ 为 $\mathcal{A}^{n}$ 上的一个仿射坐标系。存在双射 $\varphi_{\mathcal{A}}$：
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
(e_1, e_2, \dots, e_n) = (f_1, f_2, \dots, f_n) \begin{pmatrix}
T_1^{\, 1} & T_2^{\, 1} & \dots & T_n^{\, 1} \\
T_1^{\, 2} & T_2^{\, 2} & \dots & T_n^{\, 2} \\
\vdots & \vdots & & \vdots \\
T_1^{\, n} & T_2^{\, n} & \dots & T_n^{\, n}
\end{pmatrix}.
$$

**命题**：设点 $A$ 在坐标系 $\mathcal{A}$ 下的坐标为 $(x^{1}, \dots, x^{n})$，在坐标系 $\mathcal{A}'$ 下的坐标为 $(y^{1}, \dots, y^{n})$，则它们之间的关系为：
$$
y^{i} = \sum_{j=1}^{n} T_j^{\, i} (x^{j} - a^{j}), \quad \text{或} \quad \begin{pmatrix} y^{1} \\ y^{2} \\ \vdots \\ y^{n} \end{pmatrix} = \begin{pmatrix}
T_1^{\, 1} & T_2^{\, 1} & \dots & T_n^{\, 1} \\
T_1^{\, 2} & T_2^{\, 2} & \dots & T_n^{\, 2} \\
\vdots & \vdots & & \vdots \\
T_1^{\, n} & T_2^{\, n} & \dots & T_n^{\, n}
\end{pmatrix} \begin{pmatrix} x^{1} - a^{1} \\ x^{2} - a^{2} \\ \vdots \\ x^{n} - a^{n} \end{pmatrix}.
$$
当变换矩阵的行列式 $\det(T_i^{\, j}) > 0$ 时，称两个坐标系**同向**；反之称为**反向**。

### 2.4 拓扑与实标量场（函数）

#### 拓扑
设 $\mathcal{A} = \{O, e_i\}$ 是 $\mathcal{A}^{n}$ 的一个仿射坐标系。$\mathcal{A}^{n}$ 的子集 $U$ 称为**开集**，如果它在坐标映射 $\varphi_{\mathcal{A}}$ 下的像 $\varphi_{\mathcal{A}}(U)$ 是 $\mathbb{R}^{n}$ 中的开集。

**引理 3.1**：一个子集 $B \subset \mathcal{A}^{n}$ 在某个仿射坐标系下是开集，当且仅当它在任意仿射坐标系下都是开集。

**证明概要**：坐标变换映射 $\varphi_{\mathcal{A}'} \circ \varphi_{\mathcal{A}}^{-1}: \mathbb{R}^{n} \to \mathbb{R}^{n}$ 是一个仿射变换（由可逆矩阵 $T$ 和平移向量决定），因而是 $\mathbb{R}^{n}$ 到自身的同胚映射。同胚映射保持开集性质。

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

## 三、 关联与总结

- **几何量**：仅依赖于几何对象本身，而不依赖于坐标系选取的量。曲率 $k(s)$ 和挠率 $\tau(s)$ 是空间曲线的内在几何量。
- **易混淆点**：注意区分**法平面**、**从切平面**、**密切平面**的法向量。密切平面有时也被称为“法切平面”，但标准术语是密切平面。
- **从曲线到空间**：Frenet标架研究的是嵌入在空间（如 $\mathbb{R}^3$，可视为仿射空间）中的曲线的局部微分性质，而仿射空间几何提供了研究这些曲线所存在的“舞台”的基本语言和框架（如坐标系、变换、拓扑）。
- **相关笔记**：[[拓扑学基础概念]]
