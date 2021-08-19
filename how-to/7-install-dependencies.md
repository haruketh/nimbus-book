# 7. 依存関係をインストールする

Nimbusのビーコンチェーンは、Linux、macOS、Windows、Androidで動作します。現時点では、Nimbusはソースからビルドしなければならないため、いくつかの依存関係をインストールする必要があります。

## 時刻同期

ビーコンチェーンは、お使いのコンピュータが正しい時刻（プラスマイナス0.5秒）を設定しているかどうかに依存しています。

私たちは、あなたのコンピュータで高品質のタイムサービスを実行することをお勧めします。

* GPS
* NTS \(network time security, [IETFドラフト](https://tools.ietf.org/html/draft-ietf-ntp-using-nts-for-ntp-19)\)
* [Roughtime](https://roughtime.googlesource.com/roughtime) \(google\)

最低限、サーバー上でNTPクライアントを実行する必要があります。

{% hint style="info" %}
ほとんどのオペレーティングシステム（macOSを含む）は、デフォルトで自動的にNTPと同期します。
{% endhint %}

上記の内容がラテン語のように聞こえる場合は、心配しないでください。コンピューターの日付と時刻の設定をいじっていなければ大丈夫です（自動的に設定されているはずです）。

## 外部依存性

* 開発ツール（Cコンパイラ、Make、Bash、Git）

Nimbus はNimの独自のローカルコピーをビルドするため、Nim は外部依存はありません。

### Linux

一般的な Linux ディストリビューションでは、依存関係をインストールするには、

```text
# Debian and Ubuntu
sudo apt-get install build-essential git

# Fedora
dnf install @development-tools

# Archlinux, using an AUR manager
yourAURmanager -S base-devel
```

### macOS

[Homebrew](https://brew.sh/) を使用してパッケージを管理することを前提とします。

```text
brew install cmake
```

### Windows

Windows上でNimbusをビルドするには、Mingw-w64のビルド環境を推奨します。

"[MinGW-W64 Online Installer](https://sourceforge.net/projects/mingw-w64/files/)" を使用して、お使いのアーキテクチャに合わせてMingw-w64をインストールします。

* セットアップメニューでアーキテクチャを選択してください（32ビットの場合は`i686`、64ビットの場合は`x86_64`）。
* スレッドを`win32`にする
* 32ビットでは "dwarf"、64ビットでは "seh "に例外を設定します。 
* `"My Computer"/"This PC" -> "Properties" -> "Advanced system settings" -> "Environment Variables" -> "Path" -> "Edit" -> "New" -> C:\mingw-w-w64`に変更して、システムのPATHに追加します。（32ビットのときは `C:\mingw-w64\mingw32\bin`）

[Git for Windows](https://gitforwindows.org/) をインストールし、「Git Bash」シェルを使ってnimbus-eth2をクローンしてビルドします。

### Android

* FDroidまたはGoogle Playストアから[Termux](https://termux.com/)アプリをインストールします。
* お好みのディストリビューションの指示に従って、お好みの[PRoot](https://wiki.termux.com/wiki/PRoot)をインストールします。注意：UbuntuのPRootは、Arm64アーキテクチャ（Androidデバイスのための最も一般的なアーキテクチャ）でコンパイルされたすべてのNimbusの前提条件を含むことが知られています。

あなたがUbuntu PRootを使用すると仮定します。

```text
apt install build-essential git
```

