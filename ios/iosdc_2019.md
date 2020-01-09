

ReplayKit
- iOS 11+ 
    - 様々な画面が配信・録画できる

iOS11以降にしましょう

iOS10+
- Extensionを配信されるアプリ、配信するアプリの双方が実装しておく

iOS11+


### Bloadcast upload extension

- bloadcast upload setup extension ができる
- bloadcast upload setup extension ui ができる


bloadcast upload setup extension uiは、配信するアプリを選択する画面
- コードでUIるくるなら、VCをいじる
- Storyboardの場合は、まずStoryboard作成
    - Inof.plist 

NSExtensionの指定を変える

配信に関わるロジックはBroadcast Upload Extensionに書く

HLSならHaisinKitがおすすめ


Broadcast Upload Extensionが使えるメモリは50MBまで。こえるとkillされる
→縮小してCMSampleBufferを縮小してからSDKに渡す


音声

画面に変化がない時
- Heartbeatを定期的に送る

画面州力されたくないときはフラグをセットする

デバッグ
- printで出てこない
    - schemeを変えよう

air play でもフラグがtrueになるので、


## Segueの話。


Segueとは？



Segueと相性のいい画面
- Static TableViewと相性がいい

prepareForSegue
- performされる直前に呼ばれる

Modalが閉じられたことを検知するには
- segueのperformイベントでdelegateを設置してい検知する


Cons
- initializerを呼べない
- performForSegueが複雑になる

initializerを呼べないについて
iOS13から新しい機能
- Seque Action //New!!
    - @IBSegueAction


performForSegueが複雑になるについて
- destinationから何かをするという処理が多かったので、 - @IBSegueActionによって、


unwindSegue
- func unwindSegue(_ segue: IUStoryboardSegue)  が@IBActionで
- xボタンからexitアイコンにdragするだけ。


Static TableView
- ひとつだけopenURLしたい。
    - CustomSegue// OpenU RLSegue
- CustomSegue使えそう

NavigationController









