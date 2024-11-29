<script type="text/x-mathjax-config">MathJax.Hub.Config({tex2jax:{inlineMath:[['\$','\$'],['\\(','\\)']],processEscapes:true},CommonHTML: {matchFontHeight:false}});</script> <script type="text/javascript" async src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-MML-AM_CHTML"></script>

- [Lindblad formed Time Local Master Equationの導出](#lindblad-formed-time-local-master-equationの導出)
  - [The theory of open quantum systems (黄緑と黒の教科書, Breuer+)](#the-theory-of-open-quantum-systems-黄緑と黒の教科書-breuer)
    - [Nakajima-Zwanzig method](#nakajima-zwanzig-method)
    - [time-convolution technique](#time-convolution-technique)
  - [Lindblad型time local master equaitonの導出](#lindblad型time-local-master-equaitonの導出)


# Lindblad formed Time Local Master Equationの導出

$\frac{d\rho_S(t)}{dt}=-i[H_S(t), \rho_S(t)]
    +\sum_i \Gamma_i(t)[L_i(t)\rho_S(t)L_i(t)^\dagger-\frac{1}{2}\{L_i(t)^\dagger L_i(t), \rho_S(t)\}]$

の導出を目指す

## The theory of open quantum systems (黄緑と黒の教科書, Breuer+)
9章

projection operator tequnique : non-Markovも含めた開放量子系を記述する方程式を導出する手法

「環境系の部分トレースを$\rho\mapsto\mathcal{P}\rho$とする」というのがベースとなる

ハミルトニアン$H=H_0+\alpha H_I$

von-Neumann方程式から出発

### Nakajima-Zwanzig method
かなりごちゃこちゃした計算をするとNakajima-Zwanzig方程式が得られる

$\frac{\partial}{\partial t}\mathcal{P}\rho(t)=\int_{t_0}^t ds\mathcal{K}(t, s)\mathcal{P}\rho(s)+\alpha\mathcal{P}\mathcal{L}(t)\mathcal{G}(t, t_0)\mathcal{Q}\rho(t_0)$

妥当な仮定を与えて, $\alpha$で2次までの摂動展開をすると

$\frac{\partial}{\partial t}\rho_S(t)=-\alpha^2\int_{t_0}^t ds \mathrm{Tr}_E[H_I(t), [H_I(s), \rho(s)\otimes\rho_E]]$

time-localではない→扱いにくい

### time-convolution technique
かなりごちゃこちゃした計算をするとTCL方程式が得られる.

$\frac{\partial}{\partial t}\mathcal{P}\rho(t)=\mathcal{K}(t)\mathcal{P}\rho(t)+\mathcal{I}(t)\mathcal{Q}\rho(t_0)$

すでにtime-local

同様に$\alpha$の2次まで摂動展開すると

Redfield方程式 $\frac{\partial}{\partial t}\rho_S(t)=-\alpha^2\int_{t_0}^t ds \mathrm{Tr}_E[H_I(t), [H_I(s), \rho(t)\otimes\rho_E]]$

Redfield方程式も含めてtime-localなマスター方程式はまとめてtime local master equationと呼ぶらしい

導出したい

$\frac{d\rho_S(t)}{dt}=-i[H_S(t), \rho_S(t)]
    +\sum_i \Gamma_i(t)[L_i(t)\rho_S(t)L_i(t)^\dagger-\frac{1}{2}\{L_i(t)^\dagger L_i(t), \rho_S(t)\}]$

はLindblad型(Lindblad form, GKSL likeなど様々)のtime local master equationと呼ばれる.

non-markovを記述するマスター方程式をtime-localにする方法は他にもあるっぽいが, この方法がスタンダードっぽい

※10章に具体例を考えたときにLindblad型のtime local master equation形式のマスター方程式が出てくるが, これはRedfield方程式から導いたものではなく, その具体例を考えたら(摂動展開などを与えなくても)たまたまそうなっているだけ

## Lindblad型time local master equaitonの導出

**Genuine quantum trajectories for non-Markovian processes[Heinz-Peter Breuer, PRL, 2004]**

[https://journals.aps.org/pra/abstract/10.1103/PhysRevA.70.012106]

- 任意のtime local master equationはLindblad-like formとして書ける

- TCLはtime-convolutionless以外の方法でも導ける

**Canonical form of master equations and characterization of non-Markovianity [Michael J.+, PRA, 2014]**

[https://arxiv.org/abs/1009.0845]

Appendix A

- 任意のtime local master equationはLindblad-like formとして書ける
- $\dot{\rho}=\Lambda_t[\rho]=\sum_kA_k(t)\rho B_k^\dagger(t)$と書ける
[ V. Gorini, A. Kossakowski, and E. C. G. Sudarshan, J. Math.Phys. 17, 821 (1976).]
- ここからごりごり計算していくとLindblad型time local master equaitonが得られる




※「The Lindblad and Redfield forms derived from the Born–Markov master equation without secular approximation and their applications」も割ときれいに導出している