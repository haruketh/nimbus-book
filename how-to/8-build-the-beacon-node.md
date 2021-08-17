# 8. ビーコンノードを構築する

ビーコンノードはeth2ネットワークに接続し、ブロックチェーンを管理し、ビーコンチェーンと対話するためのAPIを提供します。

重要なことは、鍵をインポートできるようにするためにはビーコンノードを構築する必要があるということです。

_Todo: ビーコンノードとバリデータクライアントの関係を説明する_

### 前提条件

アプリケーションをビルドして実行する前に、[必要な依存関係がインストールされている](https://haruki.gitbook.io/nimbus-book-ja/how-to/7-install-dependencies)ことを確認してください_。_

### ノードの構築

#### 1. nimビーコンチェーンのリポジトリをクローンする

```text
git clone https://github.com/status-im/nimbus-eth2
cd nimbus-eth2
```

#### 2. ビーコンノードのビルドプロセスを実行する

```text
make nimbus_beacon_node
```



