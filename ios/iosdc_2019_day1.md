## Imageの話
sansan

### 名刺のスキャンと共有
自動検出機能の精度を向上させた!!

SampleBufferから変換する
・CIImageへ変換


iPhone6だときつかった

・CGimageを経由させて、UIImageに。

画像処理後
MetalKitのMTKView

前処理のところを改善すると効果大

画像認識処理の前処理

・CIImageを使い回す
・必要なところでUIImageに変換する

リサイズはどっちがいい？？
→ CIImageに寄せるといいのでは

CIImage(Core Imageに含まれる画像クラス)
- Metalを使った処理の恩恵を受けられる
- Immutable
    - 別スレッドから安全に参照
- 遅延実行
  - 実際に使うまで処理を実行しない
  - パフォーマンスを計測する時に注意

CIImage乗りサイズ
CIFilterを使う/使わない

Image

iOS10からリサイズがあるらしい

CIImageの変換すると、もっと早い
J


# FatViewController

サービス開発とリファクタリングのバランス、トレードオフ























