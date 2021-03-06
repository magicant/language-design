# 評価戦略

## 定義

ここでは決定的な評価戦略 (evaluation strategy) のみを考へる。すなはち、ある項 `t1` に対して簡約 `t1 → t2` が可能な時、項 `t2` は一意である。

項が簡約できないとき (当てはまる簡約が無いとき)、その項は**正規形** (canonical form) である。
ある項が有限回の簡約の繰り返しによって正規形となるときその項は**収束する** (converge)。収束しない項は**発散する** (diverge)。
項 `a` が発散するならば項 `f a` も発散するとき、関数 `f` は**正格** (strict) である。

(注) 項が正規形かどうかや収束するかどうかなどの性質は項そのものの構文的形のみならず評価戦略にも依る。

ある評価戦略の下で全ての関数が正格なとき、その評価戦略は**正格** (strict) である。

ある評価戦略の下で、簡約基の引数 `a` が値である時にしか簡約 `(λx. t1) a → t2` が認められないとき、その評価戦略は**値呼び** (call-by-value) である。
値呼びでない評価戦略は**遅延評価** (lazy evaluation) である。(遅延評価といふ語は名前呼びとか必要呼びとかの評価戦略の総称であって、それ自体が特定の評価戦略を指すのではない。)

ある型システムの下で全ての型を持つ項が収束するとき、その型システムは**正規化性** (normalization) を持つ。

## 決定的評価戦略

既存の言語は大体正格評価で、Haskell や Clean が非正格評価。
「正格か非正格かは処理系が選べる」みたいな自由度を与へると処理系がより最適化をしやすくなるかもしれないが、同じ項が評価戦略の選択によって収束したり発散したりすることになるので、混乱して使ひ物にならないと思はれる。

## 評価戦略の性質

値呼び評価戦略は正格である。

遅延評価戦略では無限リスト等の余帰納的データ構造を扱ふことができる。
値呼び戦略では不動点演算子は関数にしか適用できないので余帰納的データ構造を直接作ることはできない。(後述の型付けを参照。ただし遅延評価を模倣することで余帰納的データ構造を模倣することはできる。)

非正格評価(といふか遅延評価)は無駄な計算を減らすのには役に立たないことが多い。サンクの生成やサンクを評価済みかどうかの判定などに掛かるオーバーヘッドが大きい。またサンクが評価されるタイミングをうまく制禦しないと空間計算量が爆発する。

Haskell はデフォルトが非正格評価であるといふだけで、正格評価ができないわけではない。 `seq` 関数を使って部分的に正格性を強制することができる。
一方他の言語はデフォルトが正格評価であるといふだけで、その言語上で遅延評価を模倣する機構を作ることはできる。

## 正規化

正規化性を持つ型システムは研究対象としてはありえても決して実用的ではない。正規化性があると無限ループが書けない。すなはち、プログラムの最大稼働時間が静的に決められてしまふ。

無限ループを書けるやうにするには不動点演算子を言語プリミティブとして与へるか型付け可能にすればよい。
[再帰型](algebraictype.md#%E5%86%8D%E5%B8%B0%E5%9E%8B)があると不動点演算子は型を持てる。
