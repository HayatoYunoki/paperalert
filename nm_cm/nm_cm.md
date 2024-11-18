# non-Markovの連続測定は可能なのか

## Genuine quantum trajectories for non-Markovian processes [Heinz-Peter Breuer, PRA, 2004]

### Introduction

- 連続測定としての物理的な解釈を持つSSEをnon-Markovに対しても構成できる
- 適切な拡張された状態空間 ($\mathcal{H}\otimes \mathbb{C}^3$) を用いることでMarkovian dynamicsにembeddgingする→大きな状態空間のMarkovian evolutionの一部分としてnon-Markovian dynamicsが現れる
- 大きな状態空間のMarkovian evolutionはLindblad型の時間依存generatorを持つMarkovianマスター方程式に従う
- $\frac{d}{dt}\rho(t)=\mathcal{L}(t)\rho(t)$のとき$\mathcal{L}(t)$は必ずしも半群ではない. $\mathcal{L}(t_0)$ ($t_0\geq 0$の定数)なら力学的半群
- map $V(t, s)$の導入
- 時間依存ジャンプ演算子に対する連続測定のストレートな一般化

### Method

$\mathbb{C}^3=\mathrm{span}\{|1\rangle, |2\rangle, |3\rangle\}$

### example

未読

## Non-Markovian Continuous Quantum Measurement of Retarded Observables [Lajos Dio´si, PRL, 2008]

[H. P. Breuer, Phys. Rev. A 70, 012106 (2004)] could only be monitored by continuous measurement on a fictitious larger Hilbert space.

non-Markovianトラジェクトリは測定可能な単一システムのトラジェクトリ

von Neumann detectorを使って色々するみたいだが, von Neumann detectorが未習なので内容をちゃんと理解できた訳では無い

TLMEを仮定している訳では無い. equilibrium correlation function $\alpha (\tau-\sigma)$を使ってダイナミクスを記述している.

[L. Dio´si, Phys. Rev. A 42, 5086 (1990).]のnon-Markovianの測定理論の定式化と, NMSSE [L. Dio´si and W. T. Strunz, Phys. Lett. A 235, 569
(1997).]が等価であることをcorrelated von Neumann detectors in the weak measurement continuous limitを使って示した. すなわち、単一の量子系におけるハイゼンベルグ変数の遅延汎関数の値の連続読み出し

これを使おうと思うとまだ色々勉強が必要になりそう

## Pure-State Quantum Trajectories for General Non-Markovian Systems Do Not Exist [Howard M. Wiseman+, PRL, 2008]

上の論文 [Lajos Dio´si, PRL, 2008] の証明には欠陥がある.

[J. Gambetta and H. M. Wiseman, Phys. Rev. A. 68, 062104 (2003).]の主張

NMSSEは連続測定に対する条件付き状態として解釈することができるが、これらの解を軌跡としてつなぎ合わせることは間違い

Sの状態が純粋であり続けるためには, bathがシステムから切り離されるのを連続的に観測し続けなければならないということである。

マルコフ場合は, 環境ははSystemと相互作用し、相互作用した後に移動するので、問題にならない. non-Markovの場合は, 環境が戻ってきてもう一度systemと相互作用する. つまり環境を観測し続けることは、disturbanceをシステムにフィードバックすることになり, 状態の平均を変える.

[Lajos Dio´si, PRL, 2008]は↑を踏まえて再導出をしたもの

本論文ではそれでも[J. Gambetta and H. M. Wiseman, Phys. Rev. A. 68, 062104 (2003).]の結論は変えないことを主張

[Lajos Dio´si, PRL, 2008]は
それぞれのapparatusはsystemと一度だけ相互作用するため, systemの将来の時間発展に影響を与えずにbathを観測するのは簡単である. しかし, conditioned systemをpureにするためには既にsystemと相互作用したことのあるapparatusを観測するだけでなく, また相互作用していないものも観測する必要がある. まだ相互作用していないものを観測するにはsystemの将来の時間発展に影響を与えるnoiseを導入する必要がある. これはoriginal non-Markovian evolutionをon averageで復元するため.

本論文ではDiosiの手法での観測が, そのように時間発展に影響を与えることをexplicitな計算により示した. そしてそれはpure conditional stateを作ることに失敗することも示した.

non-Markovian pure-state trajectories cannot be interpreted as true quantum trajectories.