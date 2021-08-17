# 15. Nimbusをアップデートする

Nimbusの重要なアップデートがないかを注意を払ってください。これを行うベストな方法は、私たちの[Discord](https://discord.com/invite/XRxWahP)の **announcements** チャネルで情報を集めることです。

最新バージョンにアップデートするには下記を実行します。

```text
git pull && make update
```

続けてこちらを実行し、

```text
make nimbus_beacon_node
```

[ビーコンノードを再構築](https://haruki.gitbook.io/nimbus-book-ja/how-to/8-build-the-beacon-node)します。

{% hint style="info" %}
ダウンタイムを最小限に抑えるために、再起動する前にビーコンノードを更新して再構築することをお勧めします。
{% endhint %}

{% hint style="info" %}
ビーコンノードがすでに実行している場合は、上記の変更を有効にするために一旦切断して再接続する必要があります。
{% endhint %}



