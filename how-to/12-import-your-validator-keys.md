# 12. バリデータキーをインポートする

署名鍵をNimbusにインポートするには、鍵を生成したときに作成したディレクトリである `validator_keys` ディレクトリを `nimbus-eth2` フォルダにコピーしてください。それから実行してください。

**Mainnet**

```text
build/nimbus_beacon_node deposits import --data-dir=build/data/shared_mainnet_0
```

{% hint style="info" %}
validator\_keys ディレクトリへの別のパスを以下のように指定することもできます。

`build/nimbus_beacon_node deposits import --data-dir=build/data/shared_mainnet_0 "YOUR VALIDATOR KEYS DIRECTORY"`

"YOUR VALIDATOR KEYS DIRECTORY" をコマンドラインアプリを使って鍵を生成したときに作成された validator\_keys ディレクトリのフルパス名に置き換えます。
{% endhint %}

{% hint style="info" %}
Tip: validator\_keys ディレクトリで pwd を実行すると、フルパス名をコンソールに表示します \(Windows の場合は cd を実行してください\)
{% endhint %}

キーストアを暗号化するために、パスワードを作成して入力するように求められます。

これは普通のことであり問題ありません。バリデータクライアントはあなたの[鍵](https://blog.ethereum.org/2020/05/21/keys/)をインポートするために、 署名用のキーストアとそれを暗号化するパスワードの両方を必要とします （あなたに代わって署名するためにはキーストアを復号化する必要があるからです）。

### 鍵を格納する

鍵を Nimbus にインポートすると、バリデータの署名鍵は`build/data/shared_mainnet_0/` フォルダの`secrets` と`validators` の下に保存されます。**これらのフォルダは安全な場所にバックアップしてください**。

`secrets` フォルダには、あなたのバリデータキーにアクセスできる共通の秘密が格納されます。

`validators` フォルダには署名用キーストア（暗号化されたキー）が格納されます。キーストアはバリデータがキーを交換するための手段として使われます。キーとキーストアの詳細は[こちら](https://blog.ethereum.org/2020/05/21/keys/)を参照してください。

{% hint style="info" %}
Nimbus クライアントは、あなたの署名鍵のみをインポートします -- いずれの場合も、デポジット・ローンチパッドを使用した場合は、これが唯一の鍵となります。（この鍵の引き出し方法があるおかげで、引き出したいときはいつでもニーモニックからwithdrawキーを生成できます）
{% endhint %}

### エクスポートする

ToDo



