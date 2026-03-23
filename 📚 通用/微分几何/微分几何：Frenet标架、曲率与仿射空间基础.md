---
title: "微分几何：Frenet标架、曲率与仿射空间基础"
date: 2026-03-23
subject: 其他
subtopic: 微分几何
tags: [微分几何, Frenet标架, 曲率, 仿射几何, 空间曲线]
consolidated: true
---

# 微分几何：Frenet标架、曲率与仿射空间基础

# 微分几何：Frenet标架、曲率与仿射空间基础

## 一、空间曲线的局部性质：Frenet标架

### 1.1 核心概念

**Frenet标架**是描述空间曲线上某点局部性质的正交基，是曲线微分几何的重要工具。

### 1.2 定义与构建

设 $r:[a, b]\to \mathbb{R}^3$ 是一条可微 $C^2$ 曲线 $C$ 的**弧长参数化**。在点 $r(s)$ 处，可以定义三个相互正交的单位向量，构成该点的 Frenet 标架：
- **切向量** $\boldsymbol{\alpha}(s)$：$\boldsymbol{\alpha}(s) = \dot{r}(s)$，方向为曲线在该点的瞬时运动方向。
- **主法向量** $\boldsymbol{\beta}(s)$：$\boldsymbol{\beta}(s) = \frac{\ddot{r}(s)}{|\ddot{r}(s)|_2}$，方向指向曲线弯曲的方向（曲率中心）。
- **副法向量** $\boldsymbol{\gamma}(s)$：$\boldsymbol{\gamma}(s) = \boldsymbol{\alpha}(s) \times \boldsymbol{\beta}(s)$，由切向量和主法向量叉积得到，与曲线所在的密切平面垂直。

==考试重点：Frenet 标架下的切向量、法向量、副法向量的定义及其几何意义==

### 1.3 与Frenet标架相关的平面

以Frenet标架中的向量为法向量，可以定义三个相互垂直的平面：
- **法平面**：以 $\boldsymbol{\alpha}(s)$ 为法向量，即所有与切向量垂直的向量构成的平面。
- **从切平面**：以 $\boldsymbol{\beta}(s)$ 为法向量，由切向量和副法向量张成。
- **密切平面**：以 $\boldsymbol{\gamma}(s)$ 为法向量，由切向量和主法向量张成，是曲线在该点“最贴合”的平面。

==考试重点：三种平面的法向量分别是谁==

## 二、曲率及其再参数化

### 2.1 曲率的定义

对于弧长参数化的曲线 $r(s)$，其**曲率** $k(s)$ 定义为切向量变化率的模长：
$$
k(s) = |\ddot{r}(s)|_2
$$
曲率衡量了曲线偏离直线的程度。

### 2.2 再参数化下的曲率计算（定理2.1）

在实际计算中，曲线常不以弧长为参数。设 $r$ 为弧长参数化，$q(t)$ 为任意正则再参数化（即 $\dot{q}(t) \neq 0$），且 $q(t) = r(s(t))$。

**导数关系**：
$$
\dot{q}(t) = \dot{r}(s(t)) \frac{ds}{dt}
$$
$$
\ddot{q}(t) = \ddot{r}(s(t)) \left(\frac{ds}{dt}\right)^2 + \dot{r}(s) \frac{d^2 s}{dt^2}
$$

由于 $|\dot{r}(s)| = 1$，可得 $\dfrac{ds}{dt}=|\dot{q}(t)|_2$，且 $\dot{r}(s) \perp \ddot{r}(s)$。

令 $\ddot{q}^{\perp}(t)$ 表示 $\ddot{q}(t)$ 在垂直于 $\dot{q}(t)$ 方向上的分量，可以推导出：
$$
\ddot{q}^{\perp}(t) = \left(\frac{ds}{dt}\right)^2 \ddot{r}(s)
$$

**再参数化下的曲率公式**：
$$
k(s) = \frac{\left| \ddot{q}^{\perp}(t) \right|_2}{\left| \dot{q}(t) \right|_2^2}
$$

==考试重点：再参数化后如何计算曲率==

### 2.3 挠率

**挠率** $\tau(s)$ 衡量曲线偏离密切平面的程度，即曲线的“扭曲”程度。其定义与副法向量 $\boldsymbol{\gamma}(s)$ 的变化率有关：
$$
\dot{\boldsymbol{\gamma}}(s) = -\tau(s) \boldsymbol{\beta}(s)
$$
挠率为正表示曲线朝副法向量正方向扭转。

==考试容易考 Frenet 标架、曲率表达式、三平面法向量==

## 三、仿射空间基础

### 3.1 仿射空间的定义

设 $\mathcal{A}^{n}$ 为非空集合。若存在映射：
$$
\mathcal{A}^{n} \times \mathcal{A}^{n} \mapsto \mathbb{R}^{n}, \quad (A, B) \mapsto \overrightarrow{AB}
$$
满足：
1. $\forall v \in \mathbb{R}^{n}, A \in \mathcal{A}^{n}$，存在唯一的 $B \in \mathcal{A}^{n}$ 使得 $\overrightarrow{AB} = v$。
2. $\overrightarrow{AB} + \overrightarrow{BC} = \overrightarrow{AC}$（对任意 $A, B, C \in \mathcal{A}^{n}$）。

则称 $\mathcal{A}^{n}$ 为 $n$ 维仿射空间。点与向量分离是其与向量空间的关键区别。

### 3.2 直线与平面

设 $\mathcal{A}^{3}$ 为三维仿射空间。
- **直线**：过点 $A$ 以 $v$ 为方向的直线 $l$ 定义为：
  $$
  l = \{ B \in \mathcal{A}^{3} \mid \overrightarrow{AB} = k v, \, k \in \mathbb{R} \},
  $$
  其中 $v \in \mathbb{R}^{3}$ 为非零向量。
- **平面**：过点 $A$ 并由两个线性无关的向量 $v, w \in \mathbb{R}^{3}$ 张成的平面 $\pi$ 定义为：
  $$
  \pi = \{ B \in \mathcal{A}^{3} \mid \overrightarrow{AB} = k v + p w, \, (k, p) \in \mathbb{R}^{2} \}.
  $$

### 3.3 仿射坐标系与坐标变换

**仿射坐标系**：在 $\mathcal{A}^{n}$ 上选定一点 $O$（原点）和 $\mathbb{R}^{n}$ 上的一组基 $\{e_i\}$，则 $\mathcal{A} = \{O, e_i\}$ 构成一个仿射坐标系。点 $A$ 的坐标 $(x^{1}, \dots, x^{n})$ 由 $\overrightarrow{OA} = \sum_{i=1}^{n} x^{i} e_i$ 唯一确定。

**仿射坐标变换**：考虑两个坐标系 $\mathcal{A} = \{O, e_i\}$ 和 $\mathcal{A}' = \{O', f_i\}$。它们的关系由平移 $\overrightarrow{OO'} = \sum_{i=1}^{n} a^{i} e_i$ 和基变换 $e_i = \sum_{j=1}^{n} T_i^{\, j} f_j$ 决定。

设点 $A$ 在 $\mathcal{A}$ 和 $\mathcal{A}'$ 下的坐标分别为 $(x^{1}, \dots, x^{n})$ 和 $(y^{1}, \dots, y^{n})$，则坐标变换公式为：
$$
\begin{pmatrix} y^{1} \\ y^{2} \\ \vdots \\ y^{n} \end{pmatrix} = \begin{pmatrix}
T_1^{\, 1} & T_2^{\, 1} & \dots & T_n^{\, 1} \\
T_1^{\, 2} & T_2^{\, 2} & \dots & T_n^{\, 2} \\
\vdots & \vdots & & \vdots \\
T_1^{\, n} & T_2^{\, n} & \dots & T_n^{\, n}
\end{pmatrix} \begin{pmatrix} x^{1} - a^{1} \\ x^{2} - a^{2} \\ \vdots \\ x^{n} - a^{n} \end{pmatrix}.
$$
或分量形式：$y^{j} = \sum_{i=1}^{n} T_i^{\, j} (x^{i} - a^{i})$。
当变换矩阵的行列式 $\det(T_i^{\, j}) > 0$ 时，两个坐标系**同向**；反之称为**反向**。

### 3.4 仿射空间中的拓扑与函数

**拓扑**：通过仿射坐标系 $\mathcal{A}$ 的坐标映射 $\varphi_{\mathcal{A}}$，可以将 $\mathbb{R}^{n}$ 的标准拓扑诱导到 $\mathcal{A}^{n}$ 上。子集 $U \subset \mathcal{A}^{n}$ 是**开集**当且仅当 $\varphi_{\mathcal{A}}(U)$ 是 $\mathbb{R}^{n}$ 中的开集。

**关键引理**：一个子集在某个仿射坐标系下是开集，当且仅当它在任意仿射坐标系下都是开集。这是因为坐标变换映射 $\varphi_{\mathcal{A}'} \circ \varphi_{\mathcal{A}}^{-1}$ 是 $\mathbb{R}^{n}$ 上的仿射变换（同胚），保持开集性质。

**函数/标量场**：设 $U$ 是 $\mathcal{A}^{n}$ 的开区域，$f: U \to \mathbb{R}$ 是一个函数。在坐标系 $\mathcal{A}$ 下“读取”该函数，得到 $n$ 元函数 $f_{\mathcal{A}} = f \circ \varphi_{\mathcal{A}}^{-1}: \varphi_{\mathcal{A}}(U) \subset \mathbb{R}^{n} \to \mathbb{R}$。

**连续性等价条件**：对于 $U$ 上的函数 $f$，以下等价：
1.  $f$ 在 $\mathcal{A}^{n}$ 的诱导拓扑下连续。
2.  在某个仿射坐标系 $\mathcal{A}$ 中读取的函数 $f_{\mathcal{A}}$ 连续。
3.  在任意仿射坐标系中读取的函数均连续。

## 四、关联与总结

- **几何量**：曲率、挠率、长度、角度等都是**几何量**，它们仅依赖于几何对象本身，而不依赖于坐标系的选取。这与仿射坐标变换下的不变性思想一致。
- **从曲线到空间**：Frenet标架研究的是**曲线**的局部微分几何，而仿射空间提供了描述**点、直线、平面**等几何对象的舞台。两者是微分几何中从一维到高维研究的基础。
- **局部与整体**：Frenet标架描述了曲线的**局部**内蕴性质（曲率、挠率），而仿射空间的概念为定义和研究整体几何对象提供了框架。

## 相关笔记
- [[拓扑学基础概念]]

