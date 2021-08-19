# 4. ビーコンノードだけを実行する

このページでは、バリデータをアタッチせずにビーコンノードだけを実行する方法を説明します。

バリデータをアタッチせずにビーコンノードを実行することで、ネットワーク全体の匿名性を向上させることができます。

## 1. 依存関係のインストール

Nimbusを正しく動作させるためには、いくつかのパッケージをインストールする必要があります。

### Linux

一般的な Linux ディストリビューションでは、以下の依存関係をインストールします。

```text
# Debian と Ubuntu
sudo apt-get install build-essential git

# Fedora
dnf install @development-tools

# ArchlinuxでAURマネージャを使う
yourAURmanager -S base-devel
```

### macOS

パッケージの管理に [Homebrew](https://brew.sh/) を使うことを想定しています。

```text
brew install cmake
```

## 2. Nimbus リポジトリをクローンする

以下のコマンドを実行して、[nimbus-eth2](https://github.com/status-im/nimbus-eth2) リポジトリをクローンします。

```text
git clone https://github.com/status-im/nimbus-eth2
```

## 3. ビーコンノードをビルドする

上記のディレクトリに移動して、ビーコンノードをビルドします。

```text
cd nimbus-eth2
make nimbus_beacon_node
```

_この処理には数分かかる場合があります。処理が終わるまで待ちます。_

## 4. メインネットに接続する

下記を実行してメインネットに接続します。

```text
./run-mainnet-beacon-node.sh
```

Web3 プロバイダーのURLを入力するよう促されます。

```text
To monitor the Eth1 validator deposit contract, you'll need to pair
the Nimbus beacon node with a Web3 provider capable of serving Eth1
event logs. This could be a locally running Eth1 client such as Geth
or a cloud service such as Infura. For more information please see
our setup guide:

https://status-im.github.io/nimbus-eth2/eth1.html

Please enter a Web3 provider URL:
```

Enter キーを押してスキップします（これはバリデータを実行している場合にのみ重要です）。

