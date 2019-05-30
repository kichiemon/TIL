# MERLin Archetecture

## MERLinアーキテクチャとは？

Event-Driven Archetecture

![MERLin](./MerlinLogo.png)

https://github.com/gringoireDM/MERLin/wiki


> It emphasises the concept of modularity, promoting an easy to implement communication channel to deliver events from producers to listeners.


モジュール性やチャンネルを介したイベントのやり取りを容易に実装できることをコンセプトとしている。


## Why?

MERLinは、レゴブロックのようにモジュールを組み合わせて、イベント駆動アーキテクチャを構築する。

型安全も失わない。

https://github.com/gringoireDM/MERLin/wiki#why


> MERLinは、タイプセーフティを犠牲にすることなく、イベント駆動型アーキテクチャの典型的な疎結合を利用して、Legoレンガのようにこれらのモジュールを組み合わせることを可能にするものです。

## Module

一つの機能を提供する関数と考えるのが良さそう。

独立性があって、依存性関係も非常に限定的。

他のモジュールのことを知っていてはならないし、実装の詳細を公開してもいけない。

どんなモジュールも特定のEvnet型のProducerであり、それを結びつける役割を担う


## Event

Eventはドメインで発生したイベントを通知する。

同じドメイン内では、ユニークな名前をもつ。

ドメインに何が起きて、どんな変更があったかを説明する


## Router

Routingを担う。

EventからRoutingが発生した時に、RouterがUIをロジックに基づいて構築する


## Listener

EventのProducerから発火されるイベントを購読する。

MERLinでは、EventListenerと呼んでいる。

EventListenerは、Moduleで発生したイベントに反応する。

イベント購読は特定のEvent型に対して行う。

中にはroutingを発生させるEventがあるが、このListenerのことをMERLinでは、RouttingEventListenerと呼んでいる

この特別なRoutingEventListenerは、新しいモジュールにRoutingすることができる。






