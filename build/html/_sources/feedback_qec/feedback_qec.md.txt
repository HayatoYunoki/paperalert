<script type="text/x-mathjax-config">MathJax.Hub.Config({tex2jax:{inlineMath:[['\$','\$'],['\\(','\\)']],processEscapes:true},CommonHTML: {matchFontHeight:false}});</script> <script type="text/javascript" async src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-MML-AM_CHTML"></script>

# 連続測定によるフィードバックを用いた量子誤り訂正

- [連続測定によるフィードバックを用いた量子誤り訂正](#連続測定によるフィードバックを用いた量子誤り訂正)
  - [Inversion of Quantum Jumps in Quantum Optical Systems under Continuous Observation](#inversion-of-quantum-jumps-in-quantum-optical-systems-under-continuous-observation)
  - [Quantum error correction for continuously detected errors](#quantum-error-correction-for-continuously-detected-errors)


## Inversion of Quantum Jumps in Quantum Optical Systems under Continuous Observation

[H. Mabuchi and P. Zoller, PRL, 1996]

量子ジャンプ(デコヒーレンス, 散逸)をフィードバック($U_i$)により打ち消すことができる条件を導出

つまり$|\psi_c\rangle\rightarrow L_i|\psi_c\rangle$に対して$|\psi_c(t+dt)\rangle=U_i L_i|\psi(t)\rangle$としたい

(正規化は無視して書いています(以降も))

コヒーレンス(情報)が不可逆的に失われるため$L_i^\dagger$を作用させるだけではダメ

(ジャンプがないときの$H_{\mathrm{eff}}$による時間発展を考慮できていない)

条件1 : $L_i=k_iU^{-1}_i (k_i\in\mathbb{C})$

条件2 : $H_S$は着目している部分空間を変えない

このときジャンプとジャンプの間のダイナミクスは

$|\psi_c(t+dt)\rangle=e^{-iH_{\mathrm{eff}}dt}|\psi(t)\rangle=e^{-1/2\sum_i |k_i|^2 dt}e^{-iH_S dt}|\psi(t)\rangle$

($H_S$による時間発展だけで書けている)

ジャンプの発生を$U_i$で打ち消すダイナミクスを考えると

$|\psi_c(t)\rangle=e^{-iH_{\mathrm{eff}}(t-t_n)}U_{j_n}L_{j_n}\cdots U_{j_1}L_{j_1}e^{-iH_{\mathrm{eff}}(t_1)}|\psi(0)\rangle=e^{-iH_S dt}|\psi(t)\rangle$

($L_i$によるデコヒーレンスをすべてキャンセルできている)

論文内では2種類の実験提案(ここでは説明を省略)

QECに使える

量子メモリのコヒーレンスを保存

Shor符号などと異なりancillaが必要ない

特定のモデルでしか使えない

## Quantum error correction for continuously detected errors

[C. Ahn, H. M. Wiseman, and G. J. Milburn, PRA, 2003]

環境との相互作用によるコヒーレンスの消失は往々にして問題になる

通常のQEC(discrete QEC): 射影測定(エラーシンドロームを取得)→ユニタリにより訂正
今回(continous QEC): 連続測定→ハミルトニアンフィードバック

今回は特定の重要なエラーを訂正する(一般のエラーへの対応と符号化の冗長性はトレードオフ)

ジャンプ測定でもホモダイン測定でも可能

マルコフフィードバックとdrivingハミルトニアン(feedbackハミルトニアンとは別)がキー

2qubit codeで自発的な光子放出によるエラーが生じる例(論文内ではより一般のエラーに対する誤り訂正についても示されているが今回はこれだけに着目)

ジャンプ演算子$L=|0\rangle\langle1 |$

driving Hamiltonianはno emmision evolutionを訂正する

1. ジャンプ測定
符号語は

$|0\rangle_L\equiv (|00\rangle +|11\rangle)/\sqrt{2}$

$|1\rangle_L\equiv (|01\rangle +|10\rangle)/\sqrt{2}$

stabilizer generatorはXX

jumpに対応するKraus演算子は$\Omega_j=\sqrt{\kappa_j dt}(X_j+iY_j)\equiv\sqrt{\kappa_j dt}a_j$

$4\kappa_j$がdecay rateに相当

フィードバックがないときのマスター方程式(Lindblad)は

$\frac{d\rho}{dt}=\sum_{j=1, 2}-i[H, \rho]+\kappa_j \mathcal{D}[X_j-iY_j]\rho$

エラー訂正が可能であることは以下の必要十分条件が成り立つことから分かる

$\langle\psi_\mu|E^\dagger E|\psi_\nu\rangle=\Lambda_E \delta_{\mu, \nu}$

ここで$E$はエラーの測定に対応する演算子, $\Lambda_E$は定数

より具体的に言うとfirst qubitに光子放出が起こったとき状態は$|0\rangle_L\rightarrow |01\rangle$, $|1\rangle_L\rightarrow |00\rangle$で, これらが直交しているということ.

correcting unitaryは

$U_1=(XI-ZX)/\sqrt{2}$

$U_2=(IX-XZ)/\sqrt{2}$

光子放出によるジャンプのエラーはこれで訂正できている.

さらにジャンプが生じないときの時間発展($H_{\mathrm{eff}}$による時間発展)におけるジャンプの影響を取り除く必要がある.

ジャンプが生じないときの時間発展を表すKraus演算子は

$\Omega_0=II(1-(\kappa_1+\kappa_2)dt)-\kappa_1 dt ZI-\kappa_2 dt IZ -iHdt$

driving Hamiltonian $H$を

$H=-(\kappa_1 YX+\kappa_2 XY)$

とするとKraus演算子は

$\Omega_0=II(1-(\kappa_1+\kappa_2)dt)-\kappa_1 dt ZI(II-XX)-\kappa_2 dt IZ(II-XX)$

$(II-XX)$は符号空間を消失させるため$\Omega_0$は符号空間を変えないことが分かる.

従ってフィードバックによるエラー訂正があるときのSSEは

$d\rho=\Omega_0\rho\Omega_0^\dagger-\rho+dt\sum_{j=1, 2}\kappa_jU_ja_j\rho a_j^\dagger U_j^\dagger$.

フィードバックハミルトニアンは$H_{fb}=\sum_{1, 2}\frac{dN_j(t)}{dt}V_j$と書ける

ここで$V_j$は$U_j=\exp(-iV_j)$を満たす. ($V_j$は$U_j$に比例する(？))

2. ホモダイン測定

aa

後で追加
