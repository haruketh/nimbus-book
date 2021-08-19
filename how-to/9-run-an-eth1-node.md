# 9. eth1ノードを実行する

eth1 チェーンからのバリデータのデポジットを処理するには、eth1 クライアントを eth2 クライアントと並行して実行する必要があります。

バリデータは、ブロックを提案する際に新しいデポジットを含めなければなりません。バリデータがこのタスクを正しく実行するためには eth1 クライアントが必要です。

このページでは Geth の使い方を説明しています \(ただし、信頼できる eth1 クライアントであれば問題ありません\)。

{% hint style="info" %}
Raspberry Pi のようなリソース制限のあるデバイスで実行している場合は、その場しのぎの解決策として、代わりに個人用の Infura エンドポイントを設定することをお勧めします。現状では、Pi で完全な Geth ノードを実行するのは少し複雑かもしれません（ライトモードでは必要なデポジットデータが得られません）。

中期的（3～6ヶ月）には、誰か（おそらく私たち）がこの問題に対処するために、プレーンなEth1ヘッダ同期ライトクライアントの上に薄いレイヤーを構築することを期待しています。具体的に何が足りないのかというと、ゴシップネットでブロードキャストされているデポジットの証明です（つまり、デポジットとそれに対応するマークルプルーフは Eth1 ヘッダに関連しています）。それが解決すれば、Infura をスワップアウトすることができるはずです。

ただし、500GB以上のSSDをお持ちで、ハードウェアがそれを処理できる場合は、独自のeth1クライアントを実行することを強くお勧めします。これにより、ネットワークが可能な限り分散された状態を維持することができます。
{% endhint %}

## 1. Gethをインストールする

MacOS をお使いの場合は、[ここに記載されている手順](https://github.com/ethereum/go-ethereum/wiki/Installation-Instructions-for-Mac)に従って geth をインストールしてください。それ以外の場合は[こちら](https://github.com/ethereum/go-ethereum/wiki/Installation-Instructions-for-Mac)を参照してください。

## 2. Gethを起動する

gethをインストールしたら、以下のコマンドでeth1ノードを起動します。

Testnet

```text
geth --goerli --ws
```

Mainnet

```text
geth --ws
```

{% hint style="info" %}
--ws フラグは、websocket RPC APIを有効にするために必要です。これにより、NimbusはWeb3 API呼び出しを使用してeth1チェーンを照会することができます。
{% endhint %}

## 3. Gethをそのまま放置する

しばらく同期させておきます。Gethはデフォルトで高速同期モードを使用しています。数時間から数日かかる場合があります。

{% hint style="info" %}
Gethがまだ完全に同期していなくても、Nimbusを実行して検証を開始しても安全です。
{% endhint %}

以下のようなログが表示されるようになれば、Gethの同期が完了したことがわかります。

```text
INFO [05-29|01:14:53] Imported new chain segment               blocks=1 txs=2   mgas=0.043  elapsed=6.573ms   mgasps=6.606   number=3785437 hash=f72595…c13f23
INFO [05-29|01:15:08] Imported new chain segment               blocks=1 txs=3   mgas=0.067  elapsed=7.639ms   mgasps=8.731   number=3785441 hash=be7e55…a8c1c7
INFO [05-29|01:15:25] Imported new chain segment               blocks=1 txs=21  mgas=1.084  elapsed=33.610ms  mgasps=32.264  number=3785442 hash=fd54be…79b047
INFO [05-29|01:15:42] Imported new chain segment               blocks=1 txs=26  mgas=0.900  elapsed=26.209ms  mgasps=34.335  number=3785443 hash=2504ff…119622
INFO [05-29|01:15:59] Imported new chain segment               blocks=1 txs=12  mgas=1.228  elapsed=22.693ms  mgasps=54.122  number=3785444 hash=951dfe…a2a083
INFO [05-29|01:16:05] Imported new chain segment               blocks=1 txs=3   mgas=0.065  elapsed=5.885ms   mgasps=11.038  number=3785445 hash=553d9e…fc4547
INFO [05-29|01:16:10] Imported new chain segment               blocks=1 txs=0   mgas=0.000  elapsed=5.447ms   mgasps=0.000   number=3785446 hash=5e3e7d…bd4afd
INFO [05-29|01:16:10] Imported new chain segment               blocks=1 txs=1   mgas=0.021  elapsed=7.382ms   mgasps=2.845   number=3785447 hash=39986c…dd2a01
INFO [05-29|01:16:14] Imported new chain segment               blocks=1 txs=11  mgas=1.135  elapsed=22.281ms  mgasps=50.943  number=3785444 hash=277bb9…623d8c
```

