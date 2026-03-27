---
title: "微分几何基础：仿射空间、曲线与Frenet标架"
date: 2026-03-27
subject: 其他
subtopic: 微分几何
tags: [微分几何, 仿射空间, Frenet标架, 空间曲线, 曲率, 挠率]
consolidated: true
---

# 微分几何基础：仿射空间、曲线与Frenet标架

# 仿射空间与曲线几何学

## 1. 仿射空间基础

### 1.1 仿射空间定义
设 $\mathcal{A}^{n}$ 为非空集合。若有映射：
$$
\mathcal{A}^{n} \times \mathcal{A}^{n} \mapsto \mathbb{R}^{n}, \quad (A, B) \mapsto \overrightarrow{AB}
$$
满足：
1. $\forall v \in \mathbb{R}^{n}, A \in \mathcal{A}^{n}$，存在 $B \in \mathcal{A}^{n}$ 使得 $\overrightarrow{AB} = v$。
2. $\overrightarrow{AB} + \overrightarrow{BC} = \overrightarrow{AC}$（对任意 $A, B, C \in \mathcal{A}^{n}$）。

则称 $\mathcal{A}^{n}$ 为 $n$ 维**仿射空间**。

### 1.2 直线与平面
设 $\mathcal{A}^{3}$ 为三维仿射空间。
*   **直线**：$\mathcal{A}^{3}$ 的非空子集 $l$，若存在点 $A \in l$ 和非零向量 $v \in \mathbb{R}^{3}$，使得
    $$
    l = \{ B \in \mathcal{A}^{3} \mid \overrightarrow{AB} = k v, \, k \in \mathbb{R} \},
    $$
    则称 $l$ 为过点 $A$ 以 $v$ 为方向的直线。
*   **平面**：$\mathcal{A}^{3}$ 的非空子集 $\pi$，若存在点 $A \in \pi$ 和两个线性无关的向量 $v, w \in \mathbb{R}^{3}$，使得
    $$
    \pi = \{ B \in \mathcal{A}^{3} \mid \overrightarrow{AB} = k v + p w, \, (k, p) \in \mathbb{R}^{2} \},
    $$
    则称 $\pi$ 为过点 $A$ 并由 $v, w$ 张成的平面。

### 1.3 仿射坐标系与坐标变换
在 $\mathcal{A}^{n}$ 上选定一点 $O$（称为原点），并在 $\mathbb{R}^{n}$ 上选定一组基 $\{e_i\}$，则称 $\mathcal{A} = \{O, e_i\}$ 为 $\mathcal{A}^{n}$ 上的一个**仿射坐标系**。存在双射 $\varphi_{\mathcal{A}}$：
$$
\varphi_{\mathcal{A}}: \mathcal{A}^{n} \rightarrow \mathbb{R}^{n}, \quad A \longmapsto (x^{1}, \dots, x^{n}),
$$
其中 $\overrightarrow{OA} = \sum_{i=1}^{n} x^{i} e_i$。$(x^{1}, \dots, x^{n})$ 称为点 $A$ 在坐标系 $\mathcal{A}$ 下的坐标。

考虑两个仿射坐标系 $\mathcal{A} = \{O, e_i\}$ 和 $\mathcal{A}' = \{O', f_i\}$。它们之间的关系由下式给出：
$$
\overrightarrow{OO'} = \sum_{i=1}^{n} a^{i} e_i, \quad e_i = \sum_{j=1}^{n} T_i^{\, j} f_j.
$$

**坐标变换公式**：设点 $A$ 在坐标系 $\mathcal{A}$ 下的坐标为 $(x^{1}, \dots, x^{n})$，在坐标系 $\mathcal{A}'$ 下的坐标为 $(y^{1}, \dots, y^{n})$，则：
$$
y^{i} = \sum_{j=1}^{n} T_j^{\, i} (x^{j} - a^{j}), \quad \text{或} \quad \begin{pmatrix} y^{1} \\ y^{2} \\ \vdots \\ y^{n} \end{pmatrix} = \begin{pmatrix}
T_1^{\, 1} & T_2^{\, 1} & \dots & T_n^{\, 1} \\
T_1^{\, 2} & T_2^{\, 2} & \dots & T_n^{\, 2} \\
\vdots & \vdots & & \vdots \\
T_1^{\, n} & T_2^{\, n} & \dots & T_n^{\, n}
\end{pmatrix} \begin{pmatrix} x^{1} - a^{1} \\ x^{2} - a^{2} \\ \vdots \\ x^{n} - a^{n} \end{pmatrix}.
$$
当变换矩阵的行列式 $\det(T_i^{\, j}) > 0$ 时，称两个坐标系**同向**；反之称为**反向**。

### 1.4 拓扑与函数
设 $\mathcal{A} = \{O, e_i\}$ 是 $\mathcal{A}^{n}$ 的一个仿射坐标系。$\mathcal{A}^{n}$ 的子集 $U$ 称为**开集**，如果它在坐标映射 $\varphi_{\mathcal{A}}$ 下的像 $\varphi_{\mathcal{A}}(U)$ 是 $\mathbb{R}^{n}$ 中的开集。

**引理 3.1**：一个子集 $B \subset \mathcal{A}^{n}$ 在某个仿射坐标系下是开集，当且仅当它在任意仿射坐标系下都是开集。

设 $U$ 是 $\mathcal{A}^{n}$ 的一个开区域（连通开集），$f: U \to \mathbb{R}$ 是一个函数。给定一个仿射坐标系 $\mathcal{A} = \{O, e_i\}$，我们可以通过 $f$ 定义一个 $\mathbb{R}^{n}$ 上的 $n$ 元函数 $f_{\mathcal{A}}$：
$$
f_{\mathcal{A}} = f \circ \varphi_{\mathcal{A}}^{-1}: \varphi_{\mathcal{A}}(U) \subset \mathbb{R}^{n} \to \mathbb{R}.
$$
称 $f_{\mathcal{A}}$ 为从坐标系 $\mathcal{A}$ 中**读取** $f$ 得到的函数。

**引理 3.2**：设 $U$ 为 $\mathcal{A}^{n}$ 中开区域，$f$ 为 $U$ 上函数，则以下三点等价：
1.  $f$ 是连续的（按 $\mathcal{A}^{n}$ 上由仿射坐标系诱导的拓扑）。
2.  在某个仿射坐标系 $\mathcal{A}$ 中读取 $f$ 得到的 $n$ 元函数 $f_{\mathcal{A}}$ 连续。
3.  在任意仿射坐标系中读取 $f$ 得到的 $n$ 元函数均连续。

## 2. 空间曲线与 Frenet 标架

### 2.1 曲线参数化与弧长参数
设 $r:[a, b]\to \mathbb{R}^3$ 是一条可微 $C^2$ 曲线 $C$ 的参数化。若 $|\dot{r}(t)| \neq 0$，则称 $r$ 为**正则参数化**。

**弧长参数化**是一种特殊的正则参数化，满足 $|\dot{r}(s)| = 1$。此时，参数 $s$ 表示从某点起沿曲线的弧长。

### 2.2 Frenet 标架
设 $r(s)$ 是曲线 $C$ 的**弧长参数化**。在点 $r(s)$ 处，可以定义一组正交基，称为 **Frenet 标架**：
- **切向量** $\boldsymbol{\alpha}(s) = \dot{r}(s)$，方向沿曲线切线方向，模长为1。
- **主法向量** $\boldsymbol{\beta}(s) = \frac{\ddot{r}(s)}{|\ddot{r}(s)|}$，方向指向曲线弯曲的方向（曲率中心）。
- **副法向量** $\boldsymbol{\gamma}(s) = \boldsymbol{\alpha}(s) \times \boldsymbol{\beta}(s)$，垂直于由切向量和主法向量张成的平面。

==考试重点：Frenet 标架下的切向量、法向量、副法向量的定义及其几何意义==

### 2.3 曲率与再参数化
**曲率** $k(s)$ 衡量曲线在某点处偏离直线的程度，定义为 $k(s) = |\ddot{r}(s)|$（在弧长参数下）。

**再参数化下的曲率表达式（定理2.1）**：
设 $r$ 为弧长参数化，$q$ 为正则再参数化（即 $q(t) = r(s(t))$），则曲率 $k(s)$ 的表达式为：
$$
k(s) = \frac{\left| \ddot{q}^{\perp}(t) \right|_2}{\left| \dot{q}(t) \right|_2^2}
$$
其中 $\ddot{q}^{\perp}(t)$ 是 $\ddot{q}(t)$ 在垂直于 $\dot{q}(t)$ 方向上的分量。

**推导关键**：
- 参数变换关系：$\dot{q}(t) = \dot{r}(s(t)) \frac{ds}{dt}$
- 由于 $|\dot{r}(s)| = 1$，有 $\dfrac{ds}{dt}=|\dot{q}(t)|_2$。
- 在弧长参数下，$\dot{r}(s) \perp \ddot{r}(s)$，因此 $\dot{r}(s)\parallel\dot{q}(t)$。
- 可推出 $\ddot{q}^{\perp}(t) = \left(\frac{ds}{dt}\right)^2 \ddot{r}(s)$。
- 代入即得上述公式。

==考试重点：再参数化后如何计算曲率==

### 2.4 三种特定平面及其法向量
在曲线某点处，由 Frenet 标架可以定义三个相互垂直的平面：
- **法平面**：以 $\boldsymbol{\alpha}(s)$（切向量）为法向量的平面。
- **从切平面**：以 $\boldsymbol{\beta}(s)$（主法向量）为法向量的平面。
- **密切平面**：以 $\boldsymbol{\gamma}(s)$（副法向量）为法向量的平面。

==考试重点：三种平面的法向量分别是谁==

### 2.5 挠率
**挠率** $\tau(s)$ 衡量曲线在某点处偏离平面曲线的程度（即曲线的扭转程度）。其定义与副法向量 $\boldsymbol{\gamma}(s)$ 的变化率有关：$\dot{\boldsymbol{\gamma}}(s) = -\tau(s) \boldsymbol{\beta}(s)$。

## 3. 关联与总结

- **几何量**：曲率、挠率、Frenet标架都是**几何量**，即仅依赖于曲线本身的几何形状，而不依赖于参数化或坐标系的选择。这与仿射空间中定义的几何对象（直线、平面）的坐标无关性思想一致。
- **拓扑联系**：曲线理论中研究的连续、可微等性质，其基础是仿射空间上由坐标系诱导的拓扑结构（见引理3.2）。
- **应用**：Frenet标架是研究空间曲线局部性质（如弯曲、扭转）的核心工具，在计算机图形学、机器人路径规划、物理学（如质点运动学）中有广泛应用。

==考试容易考 Frenet 标架、曲率表达式、三平面法向量==

## 4. 易混淆点
- **法平面 vs 从切平面 vs 密切平面**：关键在于记住各自的法向量是Frenet标架中的哪一个。
- **弧长参数化 vs 一般参数化下的曲率计算**：在一般参数 $t$ 下计算曲率，必须使用定理2.1的公式 $k = \frac{|\ddot{q}^{\perp}|}{|\dot{q}|^2}$，或先转化为弧长参数。直接计算 $|\ddot{q}|$ 通常不是曲率。
- **仿射空间与向量空间**：仿射空间是点的集合，没有固定的原点；向量空间是向量的集合，有零向量。两者通过平移建立联系。

## 5. 关联知识
- [[2026-03-09-拓扑学基础概念]]
- [[微分几何-曲面论]]
- [[向量代数与张量分析]]
