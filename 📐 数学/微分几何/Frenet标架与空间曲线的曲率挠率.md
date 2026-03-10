---
title: "Frenet标架与空间曲线的曲率挠率"
date: 2026-03-10
subject: 数学
subtopic: 微分几何
tags: [Frenet标架, 曲线微分几何, 微分几何]
consolidated: true
---

# Frenet标架与空间曲线的曲率挠率

**核心概念定义**

**Frenet 标架（Frenet Frame）**指的是在空间曲线的每一点处，由切向量、主法向量、副法向量（又称双法向量或副法向量）构成的一组正交单位基。Frenet 标架能极大地揭示曲线的局部几何性质，是==曲线微分几何==的基础工具之一。

**详细说明**

设 $r:[a, b] \to \mathbb{R}^3$ 是一条 $C^2$ 可微的空间曲线，并已弧长参数化。如下定义 Frenet 标架的三个向量：

- **切向量**（Tangent Vector）：$\boldsymbol{\alpha}(s) = r'(s)$
- **主法向量**（Normal Vector）：$\boldsymbol{\beta}(s) = \dfrac{r''(s)}{|r''(s)|}$
- **副法向量（双法向量或挠向量）**：$\boldsymbol{\gamma}(s) = \boldsymbol{\alpha}(s) \times \boldsymbol{\beta}(s)$

它们相互垂直且为单位向量，满足
$$
\big(\boldsymbol{\alpha}(s),\ \boldsymbol{\beta}(s),\ \boldsymbol{\gamma}(s)\big)
$$
构成空间的有序正交基。

==考试重点：Frenet 标架下的切向量、法向量、副法向量的定义及几何意义==

**关键公式**

1. **曲率的定义与再参数化表达式**

- **曲率 k(s)：**
由弧长参数化曲线 $r(s)$，有
$$
k(s) = |r''(s)|
$$

- **再参数化表达式（定理2.1）：**
若 $q(t) = r(s(t))$ 是 $r$ 经正则参数变换 $t \to s(t)$ 得到的新参数曲线，则曲率可表示为：
$$
k(s) = \frac{\left| \ddot{q}^{\perp}(t) \right|}{\left| \dot{q}(t) \right|^2}
$$
其中：
- $\dot{q}(t) = \dot{r}(s(t)) \dfrac{ds}{dt}$
- $\ddot{q}(t) = \ddot{r}(s(t))\left(\dfrac{ds}{dt}\right)^2 + \dot{r}(s)\dfrac{d^2 s}{dt^2}$
- $\ddot{q}^{\perp}(t) = \left(\dfrac{ds}{dt}\right)^2 \ddot{r}(s)$，即 $\ddot{q}(t)$ 垂直于 $\dot{q}(t)$ 的分量。
所以
$$
\frac{\left|\ddot{q}^{\perp}(t)\right|}{|\dot{q}(t)|^2} = |\ddot{r}(s)| = k(s)
$$

==考试重点：再参数化后如何计算曲率==

2. **三种特定平面及其法向量**

- **法平面**：以切向量 $\boldsymbol{\alpha}(s)$ 为法向量
- **从切平面**（标准写法应为“主法平面”）：以主法向量 $\boldsymbol{\beta}(s)$ 为法向量
- **法切平面**：以副法向量 $\boldsymbol{\gamma}(s)$ 为法向量

==考试重点：三种平面的法向量分别是谁==

3. **挠率（Torsion）**

设空间曲线 $r(s)$，其挠率 $\tau(s)$ 是反映曲线空间弯曲性质的重要量，定义如下：
$$
\tau(s) = \frac{\det\big(r'(s), r''(s), r'''(s)\big)}{|r''(s)|^2}
$$
或者用向量投影的方式表达：
$$
\tau(s) = -\langle \gamma'(s), \beta(s) \rangle
$$
其中 $\gamma'(s)$ 是副法向量关于弧长的导数，$\langle \cdot, \cdot \rangle$ 为欧氏内积。

**例题/应用**

- 给定空间曲线的参数方程，要求：
    1. 写出其 Frenet 标架
    2. 计算曲率 $k(s)$ 与挠率 $\tau(s)$，并判断其变换下曲率计算公式
    3. 指明对应平面的法向量是谁

（练习：$r(t) = (\cos t, \sin t, t)$，求 t 处的 Frenet 标架与曲率、挠率）

**易混淆点**

- **主法向量** 与 **副法向量** 的严格定义。副法向量是 $\boldsymbol{\alpha}(s) \times \boldsymbol{\beta}(s)$，方向以保证 $(\boldsymbol{\alpha}, \boldsymbol{\beta}, \boldsymbol{\gamma})$ 构成右手系为准。
- ==注意== 再参数化曲线的曲率计算不能直接对新参数两次求导，需要用上述曲率公式。

**关联知识**

- [[2026-03-09-拓扑学基础概念]]
- [[曲线的弧长参数]]
- [[空间曲线的主法线和法平面]]


