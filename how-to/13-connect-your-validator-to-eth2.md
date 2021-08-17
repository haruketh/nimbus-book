# 13. バリデータをeth2に接続する

バリデータをメインネットに接続するには、`nimbus-eth2`リポジトリから実行します。

```text
./run-mainnet-beacon-node.sh
```

[Web3プロバイダのURL](https://haruki.gitbook.io/nimbus-book-ja/how-to/10-sync-the-beacon-node#web-3-purobaida-url)を再度入力するように求められます。

{% hint style="info" %}
ビーコンノードを既に実行している場合は、`Ctrl+c` でシャットダウンして、上記のコマンドを再実行する必要があります。
{% endhint %}

ビーコンノードが起動し、バリデータを eth2 ネットワークに接続します。これが正しく行われたかどうかを確認するには、以下のようにログが出力されているかチェックしてください。

```text
INF 2020-11-18 11:20:00.181+01:00 Launching beacon node 
...
NOT 2020-11-18 11:20:02.091+01:00 Local validator attached
```



