# Morgan Fingerprint 学習用実装

[English Version](README_en.md)

Morgan Fingerprint の仕組みを理解するために、RDKit のソースコードを参考にしながら Python で学習用実装を作ってみました。

RDKit を使えば Fingerprint は簡単に生成できますが、内部で何が起きているのかを意識する機会はあまりありません。

そこで、Atom Invariant の生成から Neighborhood の拡張、Morgan Identifier の計算、BitInfoMap の構築までを追いかけながら理解できるような実装を試作しました。

実運用向けの実装ではなく、アルゴリズムの学習を目的とした個人的な実装です。

## 作った理由

Morgan Fingerprint について調べていると、

- Atom Invariant はどのように作られるのか
- Neighborhood はどのように広がっていくのか
- Morgan Identifier はどのように計算されるのか
- 冗長な局所環境はどのように除去されるのか
- BitInfoMap はどのように構築されるのか

といった部分が気になりました。

論文や RDKit のソースコードを読むだけでは理解しきれない箇所もあったため、実際に手を動かして実装してみることにしました。

## この実装で見られるもの

学習しやすさを優先し、計算途中の中間結果を確認できるようにしています。

例えば以下の情報を確認できます。

- Atom Components
- Atom Invariants
- Bond Invariants
- Morgan Identifiers
- Neighborhood Environments
- Environment Bitsets
- BitInfoMap

また、各 radius ごとの結果を保存しているため、

- radius = 0
- radius = 1
- radius = 2
- radius = 3

といった各段階で原子環境がどのように成長していくのかを観察できます。

Fingerprint が最終的に生成されるまでの流れを追いながら理解したい方の参考になれば幸いです。

## RDKit との関係

この実装は RDKit のソースコードを参考にしながら作成しました。

Morgan Fingerprint のアルゴリズムや内部処理を理解することが目的であり、RDKit の完全な移植や置き換えを目指したものではありません。

コードは Python で新たに記述しています。

## 制限事項

学習しやすさと可読性を優先しているため、以下はあまり重視していません。

- 実行速度
- メモリ効率
- 実運用性能
- RDKit との完全互換性

実際のケモインフォマティクス用途では、通常は RDKit の利用を推奨します。

## 動作環境

- Python 3.10.18
- RDKit 2025.03.5
- Pandas 2.3.1

## 参考文献

### Morgan Algorithm

Morgan, H. L. "The Generation of a Unique Machine Description for Chemical Structures" Journal of Chemical Documentation, 5, 107–113 (1965)

### RDKit

RDKit Open-Source Cheminformatics https: //github.com/rdkit/rdkit

RDKit は BSD 3-Clause License の下で公開されています。

## ライセンス

MIT License

## 謝辞

RDKit のソースコードやドキュメントから多くのことを学ばせていただきました。

RDKit 開発者およびコミュニティの皆様に感謝いたします。