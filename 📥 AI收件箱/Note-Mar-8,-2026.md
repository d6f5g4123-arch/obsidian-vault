---
title: "Note Mar 8, 2026"
date: 2026-03-21
source: MinerU
subject: 随机过程
tags: [AI生成, MinerU, 随机过程]
---

# Note Mar 8, 2026

> 📥 由 AI 根据你的MinerU输入自动生成 · 2026-03-21
> 🔄 每晚23:59自动整理并归档到正式目录

```yaml
title: 随机过程习题一
subject: 随机过程
source_path: /大三下/作业/随机过程/Note Mar 8, 2026.pdf
---

# 习题一

## 1.1 条件概率公式推导

**题目**：当 $P(AB) > 0$ 时，推导公式 $P_A(C|B) = P(C|AB)$。

**推导**：
$$
\begin{aligned}
P_A(C|B) &= \frac{P(A \cap (C|B))}{P(A)} \quad \text{(条件概率定义)} \\
&= \frac{P(ABC)}{P(AB)} \quad \text{(化简)} \\
&= P(C|AB) \quad \text{(条件概率定义)}
\end{aligned}
$$

## 1.2 乘法公式推导

**题目**：当 $P(A) > 0$ 时，推导乘法公式：
$$
P(B_1 B_2 \dots B_n | A) = P(B_1 | A) P(B_2 | B_1 A) \dots P(B_n | B_1 B_2 \dots B_{n-1} A).
$$

**公式**：
$$
\begin{aligned}
P(B_1 B_2) &= P(B_1) \cdot P(B_2 | B_1).
\end{aligned}
$$

**推导（归纳法）**：
1.  **基础**：当 $n=2$ 时，有 $P(B_1 B_2 | A) = P(B_1 | A) \cdot P(B_2 | B_1 A)$。
2.  **归纳假设**：设 $n=k-1$ 时公式成立，即：
    $$
    P(B_1 \dots B_{k-1} | A) = P(B_1 | A) P(B_2 | B_1 A) \dots P(B_{k-1} | B_1 B_2 \dots B_{k-2} A)
    $$
3.  **归纳步骤**：对于 $n=k$，
    $$
    \begin{aligned}
    P(B_1 \dots B_k | A) &= P(B_1 \dots B_{k-1} | A) \cdot P(B_k | B_1 \dots B_{k-1} A) \\
    &= P(B_1 | A) P(B_2 | B_1 A) \dots P(B_{k-1} | B_1 \dots B_{k-2} A) \cdot P(B_k | B_1 \dots B_{k-1} A)
    \end{aligned}
    $$
    因此，公式对任意 $n$ 成立。

## 1.5 随机和的期望与方差

**题目**：设 $X_1, X_2, \cdots$ 是来自总体 $X$ 的独立同分布随机变量， $\mu = \operatorname{E} X, \sigma^{2} = \operatorname{Var}(X) < \infty$。对于和总体 $X$ 独立的取非负整数值的随机变量 $N$，当 $\sigma_{N}^{2} = \operatorname{Var}(N) < \infty$ 时，计算：
$$
\operatorname{E} \left(X_1 + X_2 + \dots + X_N\right), \quad \operatorname{Var} \left(X_1 + X_2 + \dots + X_N\right).
$$

**解**：
记 $S_N = X_1 + \dots + X_N$。

1.  **期望**：
    $$
    \begin{aligned}
    \operatorname{E}(S_N) &= \operatorname{E}[\operatorname{E}(S_N | N)] \quad \text{(全期望公式)} \\
    &= \operatorname{E}[N \cdot \mu] \quad \text{(给定 $N$ 时，$S_N$ 的期望为 $N\mu$)} \\
    &= \mu \cdot \operatorname{E}(N)
    \end{aligned}
    $$

2.  **方差**：
    由全方差公式（Law of Total Variance）：
    $$
    \operatorname{Var}(S_N) = \operatorname{E}[\operatorname{Var}(S_N | N)] + \operatorname{Var}[\operatorname{E}(S_N | N)]
    $$
    其中：
    $$
    \begin{aligned}
    \operatorname{Var}(S_N | N = n) &= n \cdot \sigma^2 \\
    E(S_N | N) &= N \cdot \mu
    \end{aligned}
    $$
    代入得：
    $$
    \begin{aligned}
    \operatorname{Var}(S_N) &= \operatorname{E}[N \cdot \sigma^2] + \operatorname{Var}[N \cdot \mu] \\
    &= \sigma^2 \cdot \operatorname{E}(N) + \mu^2 \cdot \operatorname{Var}(N)
    \end{aligned}
    $$

## 1.6 条件期望与概率计算

**题目**：设 $X$ 是非负随机变量， $X_1, X_2, \dots, X_n$ 是来自总体 $X$ 的独立同分布样本， $k \leqslant n$。
(a) 计算 $\operatorname{E}\left(X_1 + X_2 + \dots + X_k \mid X_1 + X_2 + \dots + X_n = t\right)$；
(b) 如果 $U$ 在 $[0, t]$ 上均匀分布，且与 $X_1, X_2$ 独立，计算 $P (U < X_1 \mid X_1 + X_2 = t)$。

**解**：
(a) 记 $S_n = X_1 + \dots + X_n$。由对称性，对于任意 $i$，有 $\operatorname{E}(X_i \mid S_n = t) = \operatorname{E}(X_j \mid S_n = t)$。因此：
$$
\begin{aligned}
\operatorname{E}\left( \sum_{i=1}^n X_i \mid S_n = t \right) &= \sum_{i=1}^n \operatorname{E}(X_i \mid S_n = t) = t \\
\Rightarrow \operatorname{E}(X_i \mid S_n = t) &= \frac{t}{n}
\end{aligned}
$$
所以，
$$
\operatorname{E}\left(X_1 + \dots + X_k \mid S_n = t\right) = \sum_{i=1}^k \operatorname{E}(X_i \mid S_n = t) = k \cdot \frac{t}{n} = \frac{kt}{n}.
$$

(b) 由于 $X_1$ 和 $X_2$ 独立同分布，在条件 $X_1 + X_2 = t$ 下，$(X_1, X_2)$ 的联合分布是对称的。因此，$X_1$ 在 $[0, t]$ 上的条件分布也是对称的（例如，可能服从均匀分布或某种对称分布）。又因为 $U$ 在 $[0, t]$ 上均匀分布且与 $(X_1, X_2)$ 独立，故在给定 $X_1+X_2=t$ 的条件下，$U$ 与 $X_1$ 独立（或至少 $U$ 的分布与 $X_1$ 无关）。由对称性，事件 $\{U < X_1\}$ 和 $\{U > X_1\}$ 的条件概率应相等，且 $P(U = X_1) = 0$。因此：
$$
P (U < X_1 \mid X_1 + X_2 = t) = \frac{1}{2}.
$$

> 🔄 AI合并更新：2026-03-21