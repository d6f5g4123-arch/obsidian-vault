---
title: "Frenet标架与空间曲线的微分几何分析"
date: 2026-03-11
subject: 数学
subtopic: 微分几何
tags: [微分几何, 曲线微分几何, Frenet标架, 曲率, 挠率]
consolidated: true
---

# Frenet标架与空间曲线的微分几何分析

**核心概念定义**

- **Frenet 标架**是空间曲线上某点的一个正交基底，用于精确刻画曲线在该点的局部几何性质。Frenet 标架包含切向量（**T**）、主法向量（**N**，又称主法）、副法向量（**B**，又称副法、体法或双法）。
- 该标架是研究空间曲线微分几何的基础工具，常用于定义曲率和挠率等几何量。

**Frenet 标架详细说明**

设 $r: [a, b] \to \mathbb{R}^3$ 为一条二阶可导空间曲线的**弧长参数化**（即 $|\dot{r}(s)|=1$，其中 $s$ 为弧长）。则：

- **切向量**：$\boldsymbol{T}(s) = \dot{r}(s)$
- **主法向量**：$\boldsymbol{N}(s) = \dfrac{\dot{T}(s)}{|\dot{T}(s)|}$
- **副法向量（体法向量）**：$\boldsymbol{B}(s) = \boldsymbol{T}(s) \times \boldsymbol{N}(s)$

> $\boldsymbol{T}(s), \boldsymbol{N}(s), \boldsymbol{B}(s)$ 形成该点的 Frenet 正交三标架。

==考试重点：Frenet 标架中三向量定义及其几何意义==

**关键公式**

- $\boxed{\boldsymbol{T}(s) = \displaystyle \frac{dr}{ds}}$
- $\boxed{\boldsymbol{N}(s) = \displaystyle \frac{d\boldsymbol{T}/ds}{|d\boldsymbol{T}/ds|}}$
- $\boxed{\boldsymbol{B}(s) = \boldsymbol{T}(s) \times \boldsymbol{N}(s)}$

**曲率与挠率的表达式**

- **曲率**：描述曲线弯曲程度
  $$
  k(s) = |\dot{\boldsymbol{T}}(s)| = |\ddot{r}(s)|
  $$
- **挠率**（Twist/Torsion）：描述曲线扭转程度
  $$
  \tau(s) = \frac{\det(\dot{r}(s), \ddot{r}(s), \dddot{r}(s))}{|\dot{r}(s) \times \ddot{r}(s)|^2}
  $$

==考试重点：曲率、挠率公式==

**再参数化下的曲率表达式**

若 $q(t) = r(s(t))$ 是 $r$ 的正则再参数化，则曲率在新参数 $t$ 下的表达式为：
$$
k(s) = \frac{|\ddot{q}^{\perp}(t)|}{|\dot{q}(t)|^2}
$$
其中 $\ddot{q}^{\perp}(t)$ 为二阶导数在当前切向量方向的正交分量。推导关系：

$$
\dot{q}(t) = \dot{r}(s(t)) \frac{ds}{dt}
$$
$$
\ddot{q}(t) = \ddot{r}(s(t))\left(\frac{ds}{dt}\right)^2 + \dot{r}(s)\frac{d^2 s}{dt^2}
$$
由 $|\dot{r}(s)|=1$ 可知 $\frac{ds}{dt}=|\dot{q}(t)|$，并有 $\dot{r}(s) \perp \ddot{r}(s)$。于是：

$$
\ddot{q}^{\perp}(t) = \left(\frac{ds}{dt}\right)^2 \ddot{r}(s)
$$
最终得到：
$$
\frac{|\ddot{q}^{\perp}(t)|}{|\dot{q}(t)|^2} = |\ddot{r}(s)| = k(s)
$$

==考试重点：再参数化后如何计算曲率==

**三种特定平面及法向量**

- **法平面**：法向量为切向量 $\boldsymbol{T}(s)$，即经过曲线点且垂直于切线方向的平面。
- **切平面**：法向量为主法向量 $\boldsymbol{N}(s)$，即经过曲线点且包含切向量和副法向量的平面。
- **法切平面（又称副法平面）**：法向量为副法向量 $\boldsymbol{B}(s)$。

==考试重点：三种平面的法向量及几何含义==

**例题/应用**

1. **计算空间曲线 $r(s)$ 的 Frenet 标架及曲率**：
   给定 $r(s) = (s, s^2, s^3)$，求其在 $s=0$ 处的切向量、法向量、副法向量及曲率。
   - $\dot{r}(s) = (1, 2s, 3s^2)$, $\dot{r}(0) = (1,0,0)$
   - $\ddot{r}(s) = (0,2,6s)$, $\ddot{r}(0) = (0,2,0)$
   - $\boldsymbol{T}(0) = (1,0,0)$，$\boldsymbol{N}(0) = (0,1,0)$
   - $\boldsymbol{B}(0) = (1,0,0) \times (0,1,0) = (0,0,1)$
   - 曲率 $k(0) = |\ddot{r}(0)| = 2$

2. **再参数化情形**：设 $r(s)$ 已知，$q(t) = r(s(t))$ 是另一参数下的表达式，可以通过上述公式求再参数化后的曲率。

**易混淆点**

- 弧长参数化是构建 Frenet 标架的前提，若用其他参数，则要使用再参数化的曲率公式。
- 三个“平面”名称（法平面、切平面、法切平面）与其法向量容易混淆，一定要记住：法平面法向量是切向量、切平面法向量是主法、副法向量为法切平面。
- 切向量、副法向量等常见表示有文献差异，注意统一。

**关联知识**

- [[微分几何基本概念]]
- [[三维空间向量运算]]
- [[拓扑学基础概念]]

==考试容易考 Frenet 标架、曲率表达式、三种平面的法向量==
