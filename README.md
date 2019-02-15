## [English version](https://github.com/elestyle/elepayAndroidDemoKotlin/blob/master/README.en.md)

# elepay android デモアプリケーション

elepay Android SDK の Kotlin でご利用のデモアプリケーションです。

## 必要な環境

* Android API 21
* Android Studio 3.2.1 +
* Kotlin 1.3 +
* Gradle 4.6 +

> IDEとビルドツールのバージョンは常に更新するので、最新バージョンをご利用するのはおすすめです。

* elepay APIキー (*テストキー*と*本番キー*)
> 事前に elepay より申請する必要があります。

## 利用方法

git clone または zip をダウンロードし、解凍したプロジェクトを Android Studio でオープンします。
elepay 管理システムから申請した*APIキー*を PaymentActivity.kt のキーマークのところに書き換えてください。
> ファイルパス：app/src/main/java/jp/elestyle/androidapp/elepaydemoapp/ui/PaymentActivity.kt

``` kotlin
    private val testModePublicKey = PaymentManager.INVALID_KEY
    private val liveModePublicKey = PaymentManager.INVALID_KEY
    // The following keys are used to generate charge data.
    // You may consider create your charge data from your server for payment management.
    // So these keys may not live here.
    private val testModeSecretKey = PaymentManager.INVALID_KEY
    private val liveModeSecretKey = PaymentManager.INVALID_KEY
```

> 書き換えしないと elepay の API をアクセスできませんので、必ずアプリを起動する前に変えてください。

ビルドしたアプリを、デバイスまたは Android Emulater で起動させます。

アプリには二つのデモ商品があります。```Pay``` ボタンを押したら、支払い方法の画面が表示されます。
デモのために、一つの商品に全ての支払い方法を使えることではありません。
以下のルールをご参照ください。

* 単価1円のデモ商品は Alipay または UnionPay で払えます。
* 単価100円のデモ商品は クレジットカード または PayPal で払えます。
