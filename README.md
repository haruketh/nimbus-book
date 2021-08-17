---
description: >-
  ※ 本サイトは Nimbus チームによる "The Nimbus Beacon Chain Book"
  の内容を、Status日本コミュニティが日本語化したものです。オフィシャル版はこちらを参照ください。
  https://nimbus.guide
---

# 1. Nimbus Book について

Nimbusは、低リソースなデバイスに可能な限り最高のユーザエクスペリエンスを提供することに焦点を当てたEthereum 2.0クライアントです。

本書では、Nimbus を使って Eth2 チェーンを監視し、本格的なバリデータになる方法を説明しています。

{% hint style="info" %}
実際のところ、私たちはeth2のバリデーションライフサイクルのごく初期段階にあります。バリデーションはまだ誰もがするというものではなく、リスクと責任の両方を伴います。お金を稼ぐのは簡単な方法ではありません。ソフトウェアをアップデートしたり、ハードフォークを研究したり、堅牢なセットアップをしたり......と、努力が必要です。そのため、あなたが本当にプロトコルの安全性を確保することに興味を持っている場合にだけ、ステークしてください。
{% endhint %}

### 役立つリソース

* [nimbus-eth2 repository](https://status-im.github.io/nimbus-eth2/github.com/status-im/nimbus-eth2)
* [eth2 specification](https://github.com/ethereum/eth2.0-specs/tree/v1.0.0#phase-0)
* [Ben Edgington's annotated spec](https://benjaminion.xyz/eth2-annotated-spec/phase0/beacon-chain/)
* [Vitalik's annotated spec](https://github.com/ethereum/annotated-spec/blob/master/phase0/beacon-chain.md)
* [Danny Ryan's annotated spec](https://notes.ethereum.org/@djrtwo/Bkn3zpwxB)

### なぜ eth2 か？

Eth2は分散化に妥協することなく、Ethereumのスケーラビリティ、セキュリティ、プログラミング性を向上させるための複数年にわたる計画です。

現在のEthereumチェーンとは対照的に、Eth2 ではネットワークの安全性を確保するためにPoS（proof-of-stake）を使用しています。そして、あなたが知っているようなEthereumは、今後しばらくの間、独自の独立したプルーフ・オブ・ワーク・チェーンとして存在し続けるでしょうが、PoSへの移行は今から始まります。

従来のPoWでは、ブロック提案者はマイナーと呼ばれていましたが、PoSではバリデータと呼ばれています。要するに、採掘者は実際のハードウェア（特別に製造されたマイニングマシンなど）に頼り、バリデータはソフトウェア（Nimbusなど）と良好なネットワーク接続に頼っています。

### なぜ Nimbus なのか？

一言で言うと、Nimbus はリソース制限のあるデバイス向けのEthereumクライアントを目指しています。

Ethereum の最大の展開は組み込みシステム上になると考えているため、Nimbusはリソース制限のあるハードウェアを搭載した古いスマートフォンを含むIoTや個人用モバイルデバイスでも十分に動作するように設計されています。

Nimbus はフルノードとアーカイブノードをサポートしますが、主な実装はライトクライアントとして、Proof of Stake とシャーディングに重点を置いています。

私たちのコードはすべてオープンソースです。[GitHub](https://github.com/status-im/nimbus) で私たちの活動を追跡することをお勧めします。また、[Nimbusブログ](https://our.status.im/tag/nimbus/)でも進捗状況を確認することができます。

### 参加しましょう

何かサポートが必要なときは [Status](https://join.status.im/nimbus-general) と [Discord](https://discord.gg/9dWwPnG) に参加してください。

### 免責事項

このドキュメントでは、Nimbus が理想的な状態にあることを前提としています。このプロジェクトはまだ活発な開発中です。問題に遭遇した場合は [Github にイシュー](https://github.com/status-im/nimbus-eth2/issues)を提出してください。

