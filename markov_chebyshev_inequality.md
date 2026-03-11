1. 马尔可夫不等式 (Markov's Inequality) 的证明
定理内容： 设 $Y$ 是一个非负随机变量，对于任何常数 $a > 0$：
$$P(Y \ge a) \le \frac{E[Y]}{a}$$ 
证明过程（以连续型为例）：

   1. 利用期望的定义：
   $$E[Y] = \int_{0}^{\infty} y f(y) dy$$ 
   2. 拆分积分区间： 将积分分为 $[0, a)$ 和 $[a, \infty)$ 两部分：
   $$E[Y] = \int_{0}^{a} y f(y) dy + \int_{a}^{\infty} y f(y) dy$$ 
   3. 放缩：
   * 因为 $Y$ 是非负的，所以第一个积分 $\int_{0}^{a} y f(y) dy \ge 0$。
      * 在第二个积分中，由于 $y \ge a$，所以 $\int_{a}^{\infty} y f(y) dy \ge \int_{a}^{\infty} a f(y) dy$。
   得到：
   $$E[Y] \ge 0 + \int_{a}^{\infty} a f(y) dy = a \int_{a}^{\infty} f(y) dy$$ 
   1. 整理结果：
   注意到 $\int_{a}^{\infty} f(y) dy$ 正好是 $P(Y \ge a)$。
   所以：$E[Y] \ge a P(Y \ge a)$。
   两边除以 $a$，得证：$$P(Y \ge a) \le \frac{E[Y]}{a}$$ 

------------------------------
2. 切比雪夫不等式 (Chebyshev's Inequality) 的证明
定理内容： 设 $X$ 是随机变量，均值为 $\mu$，方差为 $\sigma^2$。对于任意 $\epsilon > 0$：
$$P(|X - \mu| \ge \epsilon) \le \frac{\sigma^2}{\epsilon^2}$$ 
证明过程：

   1. 构造非负随机变量： 令 $Y = (X - \mu)^2$。显然 $Y \ge 0$。
   2. 构造常数： 令 $a = \epsilon^2$。显然 $a > 0$。
   3. 套用马尔可夫不等式：
   $$P(Y \ge a) \le \frac{E[Y]}{a}$$ 代入 $Y$ 和 $a$ 的定义：
   $$P((X - \mu)^2 \ge \epsilon^2) \le \frac{E[(X - \mu)^2]}{\epsilon^2}$$ 
   4. 识别项：
   * 左侧事件 $(X - \mu)^2 \ge \epsilon^2$ 等价于 $|X - \mu| \ge \epsilon$。
      * 右侧分子 $E[(X - \mu)^2]$ 正好是方差 $\sigma^2$（或者说 $Var(X)$）。
   得到：$$P(|X - \mu| \ge \epsilon) \le \frac{\sigma^2}{\epsilon^2}$$ 证毕。


