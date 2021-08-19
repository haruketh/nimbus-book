# 10. ビーコンノードを同期する

既に立ち上がっているネットワークに参加する場合は、デポジットを行う前にビーコンノードが完全に同期されていることを確認する必要があります。

これは、しばらくの間稼働しているネットワークに参加する場合には特に重要です。

## Mainnet

eth1 メインネットチェーンのデポジットの監視を開始するには、`nimbus-eth2` リポジトリで、以下を実行します。

```text
 ./run-mainnet-beacon-node.sh
```

## Web3プロバイダ URL

次のようなプロンプトが表示されるはずです。

```text
To monitor the Eth1 validator deposit contract, you'll need to pair
the Nimbus beacon node with a Web3 provider capable of serving Eth1
event logs. This could be a locally running Eth1 client such as Geth
or a cloud service such as Infura. For more information please see
our setup guide:

https://status-im.github.io/nimbus-eth2/eth1.html

Please enter a Web3 provider URL:
```

ローカルの geth インスタンスを実行している場合、geth はループバックインターフェース \(127.0.0.0.1\) からの接続を受け付けます。つまり、デフォルトの Web3 プロバイダの URL は次のようになるはずです。

```text
ws://127.0.0.1:8546
```

{% hint style="info" %}
Infura エンドポイントを使用している場合は、代わりにそれを入力します。
{% endhint %}

Web3プロバイダ URLを入力すると、以下のような出力が表示されるはずです。

```text
INF 2020-12-01 11:25:33.487+01:00 Launching beacon node
...
INF 2020-12-01 11:25:34.556+01:00 Loading block dag from database            topics="beacnde" tid=19985314 file=nimbus_beacon_node.nim:198 path=build/data/shared_pyrmont_0/db
INF 2020-12-01 11:25:35.921+01:00 Block dag initialized
INF 2020-12-01 11:25:37.073+01:00 Generating new networking key
...
NOT 2020-12-01 11:25:59.512+00:00 Eth1 sync progress                         topics="eth1" tid=21914 file=eth1_monitor.nim:705 blockNumber=3836397 depositsProcessed=106147
NOT 2020-12-01 11:26:02.574+00:00 Eth1 sync progress                         topics="eth1" tid=21914 file=eth1_monitor.nim:705 blockNumber=3841412 depositsProcessed=106391
...
INF 2020-12-01 11:26:31.000+00:00 Slot start                                 topics="beacnde" tid=21815 file=nimbus_beacon_node.nim:505 lastSlot=96566 scheduledSlot=96567 beaconTime=1w6d9h53m24s944us774ns peers=7 head=b54486c4:96563 headEpoch=3017 finalized=2f5d12e4:96479 finalizedEpoch=3014
INF 2020-12-01 11:26:36.285+00:00 Slot end                                   topics="beacnde" tid=21815 file=nimbus_beacon_node.nim:593 slot=96567 nextSlot=96568 head=b54486c4:96563 headEpoch=3017 finalizedHead=2f5d12e4:96479 finalizedEpoch=3014
...
```

## コマンドラインオプション

利用可能なコマンドラインオプションの一覧を説明付きで見るには、`build`ディレクトリに移動して以下のように実行してください。

```text
./nimbus_beacon_node --help
```

