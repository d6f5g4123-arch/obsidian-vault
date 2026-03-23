---
title: "微分几何：Frenet标架与仿射空间基础"
date: 2026-03-23
subject: 其他
subtopic: 微分几何
tags: [微分几何, 空间曲线, 仿射几何, Frenet标架, 曲率]
consolidated: true
---

# 微分几何：Frenet标架与仿射空间基础

# 微分几何：Frenet标架与仿射空间基础

## 第一部分：Frenet标架与空间曲线

### 核心概念：Frenet标架

**Frenet标架**是描述空间曲线上某点局部性质的正交基，是曲线微分几何的重要工具。

- **定义**：设 $r:[a, b]\to \mathbb{R}^3$ 是一条可微 $C^2$ 曲线 $C$ 的弧长参数化。称 $r(s)$ 处的切向量、主法向量、副法向量为该点的 Frenet 标架。
- **表示**：常以 $\boldsymbol{\alpha}(s)$、$\boldsymbol{\beta}(s)$、$\boldsymbol{\gamma}(s)$ 分别表示切向量、主法向量、副法向量。

==考试重点：Frenet 标架下的切向量、法向量、副法向量的定义及其几何意义==

### 再参数化下的曲率表达式（定理2.1）

- **设定**：设 $r$ 为弧长参数化，$q$ 为正则再参数化，参数变换为 $S: (c, d) \to (a, b),\ t \to s(t)$，且 $q(t) = r(s(t))$。
- **导数关系**：
  $$
  \dot{q}(t) = \dot{r}(s(t)) \frac{ds}{dt}
  $$
  $$
  \ddot{q}(t) = \ddot{r}(s(t)) \left(\frac{ds}{dt}\right)^2 + \dot{r}(s) \frac{d^2 s}{dt^2}
  $$
- **关键推导**：由于 $|\dot{r}(s)| = 1$，有 $\dfrac{ds}{dt}=|\dot{q}(t)|_2$，且 $\dot{r}(s) \perp \ddot{r}(s)$。可推出 $\dot{r}(s)\parallel\dot{q}(t)$，并有
  $$
  \ddot{q}^{\perp}(t) = \left(\frac{ds}{dt}\right)^2 \ddot{r}(s)
  $$
- **曲率公式**：最终得到曲率 $k(s)$ 的表达式为：
  $$
  k(s) = \frac{\left| \ddot{q}^{\perp}(t) \right|_2}{\left| \dot{q}(t) \right|_2^2} = \left|\ddot{r}(s)\right|_2
  $$

==考试重点：再参数化后如何计算曲率==

### 三种特定平面及其法向量

由 Frenet 标架向量定义的三个正交平面：

- **法平面**：以 $\boldsymbol{\alpha}(s)$（切向量）为法向量。
- **从切平面**：以 $\boldsymbol{\beta}(s)$（主法向量）为法向量。
- **法切平面**：以 $\boldsymbol{\gamma}(s)$（副法向量）为法向量。

==考试重点：三种平面的法向量分别是谁==

### 挠率

- **定义**：设 $r:(a, b)\to \mathbb{R}^3$，挠率是描述曲线偏离平面曲线程度的量，与副法向量的变化率有关。（原始笔记未列全，此处为补充说明）

==考试容易考 Frenet 标架、曲率表达式、三平面法向量==

## 第二部分：仿射空间中的几何学

### 3.1 直线、平面、坐标与坐标变换

#### 仿射空间定义

设 $\mathcal{A}^{n}$ 为非空集合。若有映射：
$$
\mathcal{A}^{n} \times \mathcal{A}^{n} \mapsto \mathbb{R}^{n}, \quad (A, B) \mapsto \overrightarrow{AB}
$$
满足：
1. $\forall v \in \mathbb{R}^{n}, A \in \mathcal{A}^{n}$，存在 $B \in \mathcal{A}^{n}$ 使得 $\overrightarrow{AB} = v$。
2. $\overrightarrow{AB} + \overrightarrow{BC} = \overrightarrow{AC}$（对任意 $A, B, C \in \mathcal{A}^{n}$）。

则称 $\mathcal{A}^{n}$ 为 $n$ 维仿射空间。

#### 直线与平面

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

#### 仿射坐标系

在 $\mathcal{A}^{n}$ 上选定一点 $O$（称为原点），并在 $\mathbb{R}^{n}$ 上选定一组基 $\{e_i\}$，则称 $\mathcal{A} = \{O, e_i\}$ 为 $\mathcal{A}^{n}$ 上的一个仿射坐标系。存在双射 $\varphi_{\mathcal{A}}$：
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

**证明**：
$$
\begin{aligned}
\overrightarrow{O'A} &= \overrightarrow{OA} - \overrightarrow{OO'} = \sum_{i=1}^{n} x^{i} e_i - \sum_{i=1}^{n} a^{i} e_i = \sum_{i=1}^{n} (x^{i} - a^{i}) e_i \\
&= \sum_{i=1}^{n} (x^{i} - a^{i}) \sum_{j=1}^{n} T_i^{\, j} f_j = \sum_{j=1}^{n} \left[ \sum_{i=1}^{n} T_i^{\, j} (x^{i} - a^{i}) \right] f_j.
\end{aligned}
$$
又因为 $\overrightarrow{O'A} = \sum_{j=1}^{n} y^{j} f_j$，比较分量即得 $y^{j} = \sum_{i=1}^{n} T_i^{\, j} (x^{i} - a^{i})$。

- **坐标系方向**：当变换矩阵的行列式 $\det(T_i^{\, j}) > 0$ 时，称两个坐标系**同向**；反之称为**反向**。

### 3.2 几何量

**几何量**是仅依赖于几何对象本身，而不依赖于坐标系选取的量。

### 3.3 拓扑与实标量场（函数）

#### 拓扑

设 $\mathcal{A} = \{O, e_i\}$ 是 $\mathcal{A}^{n}$ 的一个仿射坐标系。$\mathcal{A}^{n}$ 的子集 $U$ 称为**开集**，如果它在坐标映射 $\varphi_{\mathcal{A}}$ 下的像 $\varphi_{\mathcal{A}}(U)$ 是 $\mathbb{R}^{n}$ 中的开集。

**引理 3.1**：一个子集 $B \subset \mathcal{A}^{n}$ 在某个仿射坐标系下是开集，当且仅当它在任意仿射坐标系下都是开集。

**证明概要**：设 $B$ 在坐标系 $\mathcal{A}$ 下是开集。考虑坐标变换映射 $\varphi_{\mathcal{A}'} \circ \varphi_{\mathcal{A}}^{-1}: \mathbb{R}^{n} \to \mathbb{R}^{n}$。这是一个仿射变换（由可逆矩阵 $T$ 和平移向量决定），因而是 $\mathbb{R}^{n}$ 到自身的同胚映射。由于同胚映射保持开集性质，且 $\varphi_{\mathcal{A}'}(B) = (\varphi_{\mathcal{A}'} \circ \varphi_{\mathcal{A}}^{-1})(\varphi_{\mathcal{A}}(B))$，而 $\varphi_{\mathcal{A}}(B)$ 是开集，故 $\varphi_{\mathcal{A}'}(B)$ 也是开集。反之亦然。

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

**证明思路**：利用坐标变换映射 $\varphi_{\mathcal{A}'} \circ \varphi_{\mathcal{A}}^{-1}$ 是连续（且逆也连续）的事实，将不同坐标系下的函数连续性联系起来。

## 关联知识

- 本笔记第一部分（Frenet标架）是[[微分几何]]中研究空间曲线局部性质的核心工具。
- 本笔记第二部分（仿射空间）为研究几何对象提供了基础的坐标框架和拓扑结构，是[[线性代数]]与[[拓扑学]]在几何中的应用。
- 理解仿射空间的坐标变换有助于理解更一般的[[张量分析]]中的坐标变换规则。
