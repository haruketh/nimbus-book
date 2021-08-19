# 6. Raspberry Piのバリデート：メインネットのアドバイス

お使いの Pi がこのタスクに対応しているかどうかは、SSDの速度やネットワーク接続性など、多くの要因に左右されます。そのため、最初にテストネットで性能を確認するのがベストです。

一番良いのは、PiをPyrmontで実行するように設定することです。**Pyrmont上での同期やアテストに問題がなければ、あなたの設定はメインネットでも十分に使えるはずです**（メインネットの方がリソースの使用量は少ないと予想されます）。

{% embed url="https://twitter.com/EthereumOnARM/status/1332772217420177408" caption="" %}

最新のPiが故障することは想定していませんが、万が一故障した場合に備えて、予備のPiとエンタープライズグレードのSSDを購入することをお勧めします。

最後に、Piが起動時に自動再起動するようにするために、[systemdサービスを設定する](https://www.raspberrypi.org/documentation/linux/usage/systemd.md)ことをお勧めします。この方法の詳細については、[こちら](https://status-im.github.io/nimbus-eth2/beacon-node-systemd.html)のページを参照してください。

