# Go


## Tutorial
https://go-tour-jp.appspot.com/basics/1

---
- 変数名の 後ろ に型名を書く
- 同じなら省略できる
```
func add(x, y int) int {
	return x + y
}
```
- 関数の中では、 var 宣言の代わりに、短い := で暗黙的な型宣言ができる
- 基本型
```
bool

string

int  int8  int16  int32  int64
uint uint8 uint16 uint32 uint64 uintptr

byte // uint8 の別名

rune // int32 の別名
     // Unicode のコードポイントを表す

float32 float64

complex64 complex128
```

## Go Modules

Go moduleが登場している

1.14よりデフォルトON
それ以前では、GO111MODULE=on で利用できる


```
go mod init xxxx
```
でgo.modが作成され、go buildの時にimportしているものを自動で取ってくるようになる
