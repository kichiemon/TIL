# iOSDC 2day

## Auto Layoutのエラーをテストで検知する

0.1sで1%落ちるよ

anbious layout
XCAssertAutolayout

- Method Swizzling  // できない
- facebook/fishhook // できない

Cuculus




## Mobile決済アプリの作り方

キャッシュレス普及の動き

Cash-in Wallet Cach-out

どこを扱うかによって、資金決済法の適用がかわってくる

資金移動業

犯罪収益移転防止法
- 郵便
- 銀行と接続できた KYC
- 最近、eKYCも可能になった

Apple Pay
トークナイゼーション

Cach-outとしてのApple Pay
- Apple Pay App In-App provisioning

PassKit

コード決済の種類
- CPM // スマホのコードを利用者が提示
- MPM // お店がQRコードを提示

→各社独自仕様で非公開

JPQR
- QRコードのデータフォーマット、バーコードのしようをとういつ
- など

// CIQRCordGenerator

iOS13より、QRCodeGeneratorがきた


Framesorkに分けている
- FrameworkごとにSandboxを

JPQRReader



## iPhoneのカメラいもとき

カメラ

レンズで光を集める
１枚だと、収差が発生する

capturerin raw in photo

iso感度変更もできる
defaultおも

rawFormatRqwPixel

## リアクティブ

#完全に理解した

Combineに備えるために


RxSwiftを参考に自作する

Cold
Hot
Subject

masterにいれて、cherry-pickでreleaseに取り込むのいいかも






























