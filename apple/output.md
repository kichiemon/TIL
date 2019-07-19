# Appleワークショップメモ

- レシートデータ原本を保存しておく方が良さそう？

## WWDC 2019 セッション動画
- Server to Server Notificationを活用する 302
    - https://developer.apple.com/videos/play/wwdc2019/302/
- サブスクリプションオファーのベストプラクティス 305
    - https://developer.apple.com/videos/play/wwdc2019/305/
- Universal link
    外部チャネルからappにユーザーを呼び戻す
    - https://developer.apple.com/videos/play/wwdc2019/717/

## 前半まとめ
- サブスクリプションオファーを使って自発的解約を防止
- Appの
- SKStorefrontを実装てユーザに適切なコンテンツを表示する
- server to servero notification
- billing grace period
- ユーザーにエラーが起きていることを通知

## appstoreで設定できるオファーの種類
- 無料トライアル
- 前払い
- 都度払い 500円、500円、500円、1000円、1000円、、、、


## 猶予期間
課金ができない状態になっていて、サブスクの更新に失敗することがある。  
この意図しない解約を防ぐため、一定期間、AppleはBillingRetryという機能で、更新を何度も試そうとする。BillingRetryの期間が長いほど、復帰率が高い。  
一方、ユーザーからは、BillingRetryに成功するまで、サービスを続けることができず、また、BillingRetryを行なっている間、サービス提供側は収益が上がらない。  
app store connectから、猶予期間を設定することで、その猶予期間の間、ユーザーはサービスを使い続けることができ、サービス提供側も課金期間として換算される。  

- レシートに `grace_period_expires_date` があるので、ここに設定期間が入っている。この期間だけServer側で延長する

## Notificationの種類
- initial_buy
    - appstoreからこちらのserverに通知が来る
    - urlを登録するだけ
    - apple側は、3回リトライしてくれる
- interactive renewal
    - 同じものを買った時に通知が来る
- did_change_renewal_pref
    - ユーザーがダウングレードした時
- cancel
    - カスタマーサポートにて返金された時
    - キャンセルを検知しないと、残りの期間タダでサービスを提供してしまう
- did_change_renewal_status // ⭐️New⭐️
    - 自動更新のON/OFF変更を通知
- did_fail_to_renew// ⭐️New⭐️
    - 自動更新に失敗した時
- did_recover// ⭐️New⭐️
    - billing retryに成功した時
- price_increase_consent // ⭐️New⭐️
    - ユーザーが値上げの了承フローに入る時
