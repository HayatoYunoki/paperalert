<script type="text/x-mathjax-config">MathJax.Hub.Config({tex2jax:{inlineMath:[['\$','\$'],['\\(','\\)']],processEscapes:true},CommonHTML: {matchFontHeight:false}});</script>
<script type="text/javascript" async src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-MML-AM_CHTML"></script>


# 高次トロッター分解

## Suzuki's fractal method
**元論文**
- 「Fractal decomposition of exponential operators with applications to many-body theories and Monte Carlo simulations, M. Suzuki, Physics Letters A, 1990」
- 「General theory of fractal path integrals with applications to many‐body theories and statistical physics, M. Suzuki, Journal of Mathematical Physics, 1991」

## 高次トロッター分解とは
$H=A+B$

通常のトロッター分解 : $\exp((A+B)t)=\exp(At)\exp(Bt)+O(t^2)$

トロッター分解の一般化

1次の分解 : $\exp((A+B)t)=\exp(At)\exp(Bt)+O(t^2)$

2次の分解 : $\exp((A+B)t)=\exp(At/2)\exp(Bt)\exp(At/2)+O(t^3)$

(両辺を$t$の2次までテーラー展開して係数を比較することで簡単に示せる.)

2次の積公式を以下で定義

$S_2(t)\equiv\exp(At/2)\exp(Bt)\exp(At/2)$

一般に$k$次の積公式$S_k(t)$が分かっているとすると

$\exp((A+B)t)=S_k(t)+O(t^{k+1})$ (ここで$S_k(t)=\Pi_{j=1}^l \exp(c_jAt)\exp(d_jBt)$)

長い時間のシミュレーションを行うとき, 短い時間に分割して繰り返す

→繰り返し回数は次数の増加に伴って減少

→高次積公式の探索($\{c_j, d_j\}$を見つけること)のモチベーション

## 提案手法

任意の高次積公式の系統的な導出手法

論文内ではより一般的な形での定式化 (Theorem 1近辺, $r$=3のとき)

**$k(=2\kappa)$次積公式** : $S_{2\kappa}(t)=S_{2\kappa-2}(s_\kappa t)S_{2\kappa-2}((1-2s_\kappa)t)S_{2\kappa-2}(s_\kappa t)$

としたとき$s_\kappa=1/(2-2^{1/(2\kappa-1)})$(←これが高次積公式探索の解)

$S_2$を用いて偶数次に対して再帰的に定義

$S_{2m}(t)=S_{2m-1}(t)$

**3次のときの簡単な証明**

(準備)

$S_2(t)=\exp((A+B)t+O(t^3))=\exp((A+B)t+R_2t^2+R_3t^3+\dots)$とする(誤差は指数の肩に載せられることを用いた).

$S_2(t)$と$S_2(-t)$は可換なので($e^Ae^B=e^{(A+B)}$を用いると)

$S_2(t)S_2(-t)=\exp((A+B)t+R_2t^2+R_3t^3\dots-(A+B)t+R_2t^2-R_3t^3\dots)=\exp(2(R_2t^2+R_4t^4))$

また$S_2(t)S_2(-t)=I$

よって$R_2=R_4=\dots=0$

(証明)

$S_4(t)=S_2(s_2t)S_2((1-2s_2)t)S_2(s_2t)=\dots=\exp((A+B)t+[2s_2^3+(1-2s_2)^3]R_3+O(t^5))$

$2s_2^3+(1-2s_2)^3=0$を解くと$s_2=1/(2-\sqrt[3]{2})$



デメリット : $s_\kappa, 1-2s_\kappa>1$→誤差大

**デメリットを改善した公式**

$k(=2\kappa)$次積公式 : $S_{2\kappa}(t)=S_{2\kappa-2}(u_\kappa t)^2S_{2\kappa-2}((1-4u_\kappa)t)S_{2\kappa-2}(u_\kappa t)^2$

としたとき$u_\kappa=1/(4-4^{1/(2\kappa-1)})$

![2](2.pdf)
![4](4.pdf)


