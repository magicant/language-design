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
- オブジェクト指向プログラミング
  - [継承](inheritance.md)
  - [メソッドのオーバーライド](overriding.md)
  - [デストラクター](destructor.md)
- スケーリング
  - [名前空間](namespace.md)
  - [分割コンパイル](separatecompilation.md) - 型の先行宣言・ヘッダーファイル
