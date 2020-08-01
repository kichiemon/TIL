# TextFormField



## 入力内容を制限したい！

A. inputFormattersを利用する


```
TextFormField(
  ...,
  inputFormatters: [
    FilteringTextInputFormatter.digitsOnly
  ],
  ...,
)
```


## FilteringTextInputFormatterを使おう

`inputFormatters` に `FilteringTextInputFormatter` を渡すことで、ユーザーの入力に対して制限をかけることができます。

挙動としては、ユーザーが入力したものに対して制限が適用され、許可されたもの以外はFormFieldには何も表示されなくなります。

この時、特にエラー表示などはされません。

## FilteringTextInputFormatterの種類

許可(allow)、不許可(deny)の両側面から制限ことができます。

* FilteringTextInputFormatter.allow(RegExp(正規表現))
* FilteringTextInputFormatter.deny(RegExp(正規表現))

また、標準で用意されているものが2つあります。
「数字のみ」「1行だけ（==改行を許可しない）」です。

* FilteringTextInputFormatter.digitsOnly
  * 中身の実装は `FilteringTextInputFormatter.allow(RegExp(r'[0-9]'));`
* FilteringTextInputFormatter.singleLineFormatter
  * 中身の実装は `FilteringTextInputFormatter.deny('\n');`


## 任意の処理を挟みたい場合は、TextInputFormatterを利用

TextInputFormatter.withFunctionを使うと、任意の処理を実行することも可能です。   
期待しない入力値が来たときにエラーを出して知らせたい場合などに利用するといいでしょう。

* TextInputFormatter.withFunction

e.g. 
```
TextInputFormatter.withFunction((oldValue, newValue) =>
    RegExp(r'^[A-Za-z0-9]+').hasMatch(newValue.text) ? newValue : oldValue)
```

## 補足

以下はDeprecatedになりましたので利用しないでください。

https://github.com/flutter/flutter/pull/59120


* WhitelistingTextInputFormatter
* BlackelistingTextInputFormatter

