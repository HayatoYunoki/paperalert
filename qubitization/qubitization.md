<script type="text/x-mathjax-config">MathJax.Hub.Config({tex2jax:{inlineMath:[['\$','\$'],['\\(','\\)']],processEscapes:true},CommonHTML: {matchFontHeight:false}});</script> <script type="text/javascript" async src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-MML-AM_CHTML"></script>

# Qubitizationを用いた量子位相推定

- [Qubitizationを用いた量子位相推定](#qubitizationを用いた量子位相推定)
  - [位相推定概要](#位相推定概要)
  - [ユニタリへのエンコード](#ユニタリへのエンコード)

参考文献

- Ryan Babbush+, PRX, 2018, Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity

- Low, Chuang, Quantum, 2016, Hamiltonian simulation by Qubitization

おおまかな流れ

1. ハミルトニアン$H$ (固有値$E_k$) を用意する
2. ユニタリにエンコード$U(H)$する
3. 量子位相推定QPEにより$U(H)$の固有値$f(E_k)$を取り出す
4. $f(E_k)$デコードすることで$E_k$を取り出す

## 位相推定概要

## ユニタリへのエンコード

ナイーブなエンコーディングを行えばQPEからハミルトニアンの固有値が直接得られる。

ここでは違う方法を考える。

固有値$e^{i \mathrm{arccos}(E_k a)}$を持つユニタリ$W$を用いる

これにはブロックエンコーディングと、それに対するqubitizationを用いればよい。

