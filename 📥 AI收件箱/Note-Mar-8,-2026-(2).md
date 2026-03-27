---
title: "Note Mar 8, 2026 (2)"
date: 2026-03-21
source: MinerU
subject: 其他
tags: [AI生成, MinerU, 其他]
---

# Note Mar 8, 2026 (2)

> 📥 由 AI 根据你的MinerU输入自动生成 · 2026-03-21
> 🔄 每晚23:59自动整理并归档到正式目录

```yaml
title: 拓扑学习题笔记
subject: 拓扑学
source_path: /Note Mar 8, 2026 (2).pdf
---

# 拓扑学习题

## 习题 2
设 $X = \{x, y, z\}$。$X$ 的下列子集族是不是拓扑？如果不是，请添加最少的子集，使它成为拓扑。

(1) $\{X, \emptyset, \{x\}, \{y, z\}\}$；
(2) $\{X, \emptyset, \{x, y\}, \{x, z\}\}$；
(3) $\{X, \emptyset, \{x, y\}, \{x, z\}, \{y, z\}\}$。

**解：**
(1) 是拓扑。
(2) 不是拓扑。需要添加 $\{x\}$ 和 $\{y, z\}$。
(3) 不是拓扑。需要添加 $\{x\}, \{y\}, \{z\}$。

## 习题 3
规定实数集 $\mathbb{R}$ 上的子集族 $\tau = \{(-\infty, a) \mid -\infty \leqslant a \leqslant +\infty\}$（当 $a = -\infty$ 时，$(-\infty, a)$ 表示 $\varnothing$；当 $a = +\infty$ 时，$(-\infty, a) = \mathbb{R}$）。证明 $\tau$ 是 $\mathbb{R}$ 上的一个拓扑。

**证明：**
1. 显然 $\mathbb{R} \in \tau$，$\emptyset \in \tau$。
2. 设 $\{ (-\infty, a_\alpha) \}_{\alpha \in I}$ 是 $\tau$ 中一族开集，记 $M = \sup_{\alpha \in I} a_\alpha$，则
   $$
   \bigcup_{\alpha \in I} (-\infty, a_\alpha) = (-\infty, M) \in \tau.
   $$
3. 设 $(-\infty, a_1), (-\infty, a_2) \in \tau$，记 $m = \min\{a_1, a_2\}$，则
   $$
   (-\infty, a_1) \cap (-\infty, a_2) = (-\infty, m) \in \tau.
   $$
   由数学归纳法，有限个 $\tau$ 中集合的交仍在 $\tau$ 中。

综上，$\tau$ 满足拓扑公理，是 $\mathbb{R}$ 上的一个拓扑。

## 习题 9
设 $A$ 和 $B$ 都是拓扑空间 $X$ 的子集，并且 $A$ 是开集。证明 $A \cap \overline{B} \subset \overline{A \cap B}$。

**证明：**
设 $x \in A \cap \overline{B}$，则 $x \in A$ 且 $x \in \overline{B}$。因为 $A$ 是开集，所以 $A$ 是 $x$ 的一个邻域。又因为 $x \in \overline{B}$，所以 $x$ 的任一邻域与 $B$ 相交非空，特别地，$A$ 与 $B$ 相交非空，且 $x \in A$，故 $x \in \overline{A \cap B}$。因此 $A \cap \overline{B} \subset \overline{A \cap B}$。

## 习题 5
证明：$A$ 是拓扑空间 $X$ 的稠密子集 $\Longleftrightarrow$ $X$ 的每个非空开集与 $A$ 相交非空。

**证明：**
- $(\Rightarrow)$ 设 $\overline{A} = X$。若存在非空开集 $U$ 使得 $U \cap A = \emptyset$，则 $U \subset X \setminus A$。因为 $U$ 是开集，$X \setminus U$ 是闭集且包含 $A$，故 $\overline{A} \subset X \setminus U$，这与 $\overline{A} = X$ 矛盾。
- $(\Leftarrow)$ 设 $X$ 的每个非空开集与 $A$ 相交非空。对任意 $x \in X$ 和 $x$ 的任意邻域 $U$，$U$ 包含一个开邻域 $V$，由条件 $V \cap A \neq \emptyset$，从而 $U \cap A \neq \emptyset$，故 $x \in \overline{A}$。因此 $\overline{A} = X$，即 $A$ 在 $X$ 中稠密。
```

---
## 追加内容

---
title: "Note Mar 8, 2026 (2)"
subject: "其他"
source_path: "/"
---

### 2. 设 $X = \{x, y, z\}$ . $X$ 的下列子集族是不是拓扑？如果不是，请添加最少的子集，使它成为拓扑.
(1) $\{X, \emptyset, \{x\}, \{y, z\}\}$ ;   
(2) $\{X, \emptyset, \{x, y\}, \{x, z\}\}$ ;   
(3) $\{X, \emptyset, \{x, y\}, \{x, z\}, \{y, z\}\}$ .

**解：**
(1) 是拓扑。
(2) 不是拓扑。需添加子集 $\{x\}$ 和 $\{y, z\}$，使其对有限交封闭。构成拓扑 $\{X, \emptyset, \{x\}, \{x, y\}, \{x, z\}, \{y, z\}\}$。
(3) 不是拓扑。需添加子集 $\{x\}, \{y\}, \{z\}$，使其对任意并封闭。构成拓扑 $\{X, \emptyset, \{x\}, \{y\}, \{z\}, \{x, y\}, \{x, z\}, \{y, z\}\}$，即离散拓扑。

---

### 3. 规定实数集 $\pmb{R}$ 上的子集族 $\tau = \{(-\infty, a) \mid -\infty \leqslant a \leqslant +\infty\}$ ( $a = -\infty$ , 则 $(-\infty, a)$ 表示 $\varnothing$ ; $a = +\infty$ , 则 $(-\infty, a) = \mathbb{R}$ ). 证明 $\tau$ 是 $\pmb{R}$ 上的一个拓扑.

**证明：**
① $X = \mathbb{R} \in \tau$ (取 $a = +\infty$)，$\emptyset \in \tau$ (取 $a = -\infty$)，均属于 $\tau$。
② 设一族开集 $\{(-\infty, a_\alpha)\}_{\alpha \in I}$，其中 $a_\alpha \in [-\infty, +\infty]$。则
   $$
   \bigcup_{\alpha \in I} (-\infty, a_\alpha) = (-\infty, \sup_{\alpha \in I} a_\alpha) \in \tau.
   $$
③ 设有限个开集 $\{(-\infty, a_i)\}_{i=1}^n$。则
   $$
   \bigcap_{i=1}^n (-\infty, a_i) = (-\infty, \min_{1 \le i \le n} a_i) \in \tau.
   $$
满足拓扑三公理，故 $\tau$ 是 $\mathbb{R}$ 上的一个拓扑。

---

### 9. 设 $A$ 和 $B$ 都是拓扑空间 $X$ 的子集，并且 $A$ 是开集。证明 $A \cap \overline{B} \subset \overline{A \cap B}$ 。

**证明：**
首先，有分解 $\overline{B} = (A \cap \overline{B}) \cup (A^c \cap \overline{B})$。
对右边取闭包：
$$
\overline{B} = \overline{(A \cap B) \cup (A^c \cap B)} \subset \overline{A \cap B} \cup \overline{A^c \cap B}.
$$
因为 $A$ 是开集，所以 $A^c$ 是闭集，故 $\overline{A^c \cap B} \subset A^c \cap \overline{B}$。
因此，$A^c \cap \overline{B} \supset \overline{A^c \cap B}$。
结合上述包含关系，可得 $A \cap \overline{B} \subset \overline{A \cap B}$。

---

### 5. 证明: $A$ 是拓扑空间 $X$ 的稠密子集 $\Longleftrightarrow X$ 的每个非空开集与 $A$ 相交非空.

**证明：**
$(\Rightarrow)$ 设 $\overline{A} = X$。若存在非空开集 $U$ 使得 $U \cap A = \varnothing$，则取 $x \in U$，$U$ 是 $x$ 的一个邻域且与 $A$ 不交，这与 $x \in \overline{A}$ 矛盾。
$(\Leftarrow)$ 设 $X$ 的每个非空开集都与 $A$ 相交非空。对任意 $x \in X$，$x$ 的任一邻域 $U$ 都是开集（或包含开集），故 $U \cap A \ne \varnothing$。因此 $x \in \overline{A}$，故 $\overline{A} = X$，即 $A$ 在 $X$ 中稠密。