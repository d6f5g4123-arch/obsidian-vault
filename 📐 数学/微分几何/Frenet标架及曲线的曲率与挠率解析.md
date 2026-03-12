---
title: "Frenet标架及曲线的曲率与挠率解析"
date: 2026-03-12
subject: 数学
subtopic: 微分几何
tags: [Frenet标架, 曲率, 挠率, 曲线微分几何, 微分几何]
consolidated: true
---

# Frenet标架及曲线的曲率与挠率解析

## 核心概念定义

**Frenet标架**：在三维空间中，Frenet标架是描述空间曲线某一点局部几何性质的正交基，由切向量（$\boldsymbol{\alpha}$）、主法向量（$\boldsymbol{\beta}$）、副法向量（$\boldsymbol{\gamma}$）组成，是研究曲线微分几何的重要工具。

- **切向量**（Tangent vector，$\boldsymbol{\alpha}(s)$）：表示曲线在某点的瞬时方向。
- **主法向量**（Principal normal，$\boldsymbol{\beta}(s)$）：指向曲率中心，描述曲线偏转的方向。
- **副法向量**（Binormal，$\boldsymbol{\gamma}(s)$）：由切向量和主法向量通过叉乘得到，描述曲线扭转的方向。

---

## 详细说明

设空间曲线 $r:[a, b]\to \mathbb{R}^3$ 为 $C^2$ 可微，采用弧长参数化 $s$，即 $|\dot{r}(s)|=1$。

- **Frenet标架的三个向量** 在点 $r(s)$ 处依次定义为：
  - 切向量：$\boldsymbol{\alpha}(s) = \dot{r}(s)$
  - 主法向量：$\boldsymbol{\beta}(s) = \dfrac{\ddot{r}(s)}{|\ddot{r}(s)|}$
  - 副法向量：$\boldsymbol{\gamma}(s) = \boldsymbol{\alpha}(s) \times \boldsymbol{\beta}(s)$

- 三个向量两两正交且模长均为1。

---

## 关键公式

### 1. Frenet-Serret 公式

$$
\begin{cases}
\dot{\boldsymbol{\alpha}}(s) = k(s)\,\boldsymbol{\beta}(s) \\
\dot{\boldsymbol{\beta}}(s) = -k(s)\,\boldsymbol{\alpha}(s) + \tau(s)\,\boldsymbol{\gamma}(s) \\
\dot{\boldsymbol{\gamma}}(s) = -\tau(s)\,\boldsymbol{\beta}(s)
\end{cases}
$$

其中：
- $k(s)$ 为曲率，$\tau(s)$ 为挠率

### 2. 曲率的定义与再参数化表达式

- **曲率定义**：
  $$
  k(s) = |\ddot{r}(s)|
  $$
- **再参数化情形下的曲率表达式**（设 $q(t) = r(s(t))$，$t$ 非弧长参数）：
  $$
  k(s) = \frac{\left| \ddot{q}^{\perp}(t) \right|}{\left| \dot{q}(t) \right|^2}
  $$
  其中 $\ddot{q}^{\perp}(t)$ 表示 $\ddot{q}(t)$ 在 $\dot{q}(t)$ 的正交补方向的分量。

- 常用推导：
  $$
  \dot{q}(t) = \dot{r}(s(t))\frac{ds}{dt}
  $$
  $$
  \ddot{q}(t) = \ddot{r}(s(t))\left(\frac{ds}{dt}\right)^2 + \dot{r}(s)\frac{d^2s}{dt^2}
  $$
  其中 $|\dot{r}(s)| = 1$，$\dot{r}(s) \perp \ddot{r}(s)$。
  由此有：
  $$
  \ddot{q}^{\perp}(t) = \left(\frac{ds}{dt}\right)^2\ddot{r}(s)
  $$
  故再参数化后曲率仍可通过上式计算。

  ==考试重点：再参数化曲线的曲率计算==

### 3. 挠率的定义

- **挠率** $\tau(s)$ 度量曲线偏离所在平面的扭转程度，定义为：
  $$
  \tau(s) = \frac{\det(\dot{r}(s),\ddot{r}(s),\dddot{r}(s))}{|\ddot{r}(s)|^2}
  $$

---

## 三种特定平面及其法向量

- **法平面**：法向量为 $\boldsymbol{\alpha}(s)$（即切向量）
- **切平面**：法向量为 $\boldsymbol{\beta}(s)$（即主法向量）
- **法切平面**：法向量为 $\boldsymbol{\gamma}(s)$（即副法向量）

==考试重点：三种平面的法向量分别是谁==

---

## 例题/典型应用

1. **已知空间曲线 $r(t)$ 求某点的Frenet标架**：先用自然参数计算导数，再单位化得到 $\boldsymbol{\alpha}, \boldsymbol{\beta}, \boldsymbol{\gamma}$，进而算出曲率/挠率。
2. **再参数化求曲率**：利用上述再参数化曲率公式，先计算 $\dot{q}(t), \ddot{q}(t)$，再按公式取正交补分量并代入求解。

---

## 易混淆点总结

- **弧长参数化、非弧长参数化**：只有弧长为参数时 $|\dot{r}(s)|=1$，推导和公式才简洁。
- **平面法向量选取**：法平面/切平面/法切平面分别对应 Frenet 三个基向量，不可混淆。
- **挠率与曲率**：曲率描述弯曲程度，挠率描述扭转程度，二者不同。
- **正交性**：Frenet 标架三向量两两正交。

---

## 关联知识
- [[2026-03-09-拓扑学基础概念]]
- [[微分几何]]

