# Language design
プログラミング言語設計のメモ

- 実行時意味論
  - [評価戦略](evaluation.md)
  - [参照](reference.md)
  - [例外](exception.md)
  - [コピーを減らす最適化](copyelision.md)
  - [ごみ収集 (ガーベジコレクション)](gc.md)
- データ構造と型システム
  - [代数的データ型](algebraictype.md) - 直積・直和・再帰
  - [部分型付け](subtyping.md)
  - [型の再構築 (型推論)](typereconstruction.md)
  - [多相性 (多態性)](polymorphism.md)
  - [型演算子](typeoperator.md)
  - [依存型](dependenttype.md)
  - [抽象データ型](adt.md)
  - [型クラス](typeclass.md)
- オブジェクト指向プログラミング
  - [継承](inheritance.md)
  - [メソッドのオーバーライド](overriding.md)
  - [デストラクター](destructor.md)
- スケーリング
  - [関数の構成](function.md) - 名前付き引数・部分適用
  - [名前空間](namespace.md)
  - [分割コンパイル](separatecompilation.md) - 型の先行宣言・ヘッダーファイル
- モデリングと設計 - モデルと実行時意味論と型の関係
- データ変換 - 直列化・永続化・遠隔手続呼出

## リンク

- [検査例外と場合分けと多態性の話](http://magicant.txt-nifty.com/main/2013/05/post-5cc9.html) - 直和型の話もある
