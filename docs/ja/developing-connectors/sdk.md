---
title: 開発者プログラム
date: 2019-05-08 17:00:00 Z

redirectFrom:
  - /custom-connectors.html
---
{:style="border-1px solid #dfdfdf; border-radius: 5px;"}

![Workato](https://d15ij1k610n9bt.cloudfront.net/github-img/workato-developer-program.png)

# はじめに
ここで説明しているソフトウェア開発キット（SDK）のドキュメントには、Workato経由で接続できるであろうというご利用者の意見にしたがって、追加アプリケーションを接続するためのコネクタを作成するのに必要な手順が示されています。Workatoでコネクタを構築するということは、すべてのコネクタのユーザーが期待するユーザーエクスペリエンスを提供しながら、技術的な側面も管理するということです。

Workatoはすべての利用者がプログラミングの知識を必要とせずに、エンタープライズレベルの連携を実現するために設計されました。コネクタに関しては機能性とシンプルさを両立したところでよいように作られていますので、自社チームでの利用のためのコネクタであったり、Workatoにコネクタを登録するためのコネクタであったりと、誰でもここのドキュメントを見てサクッと連携を作成することができます。

## カスタムコネクタとは

<Video src="https://www.youtube.com/embed/bfmavANqHNI" />

A connector allows Workato to interact with a single application through a series of [triggers](/recipes/triggers.md) and [actions](/recipes/actions.md). Triggers monitor for events that occur in the application you hope to connect to and kickstart a workflow of actions that we call [recipes](/workato-concepts.md#recipes). Actions carry out specific pre-defined operations in the target application.

Connectors built on the SDK are called **custom connectors**. These connectors have a private scope by default which means that they are only visible and available to the connector owner. After the connector is built and ready, you also have the ability to share it with others on various levels.

## 始める前に...
Workato has a whole host of other features and functionalities that might help you achieve what you are hoping for such as our universal HTTP connector or custom actions if your integration needs aren't so complex. [Learn more](/developing-connectors.md).

If you've decided that a custom connector is necessary, do check in at our [developer portal](https://developer.workato.com/) to see if anyone has contributed a custom connector to the application you're looking for. Our friendly support team via chat on our main website can also help you check our internal repository of custom connectors built by our customer success team.

Reading the SDK documentation is still useful as you'll be able to install these custom connectors and continue working on them if you wish to do so.

## ドキュメントフォーマット
This section will list everything you need to know about our SDK as well as provide some guides, walkthroughs, and example connectors that our users have built. You may use the links below to skip ahead to your desired section but it is recommended that you go through this documentation the order stated so as to not miss any of the features we have that might help you down the line.

> In our documentation, we default to JSON when giving examples. It is highly recommended that you read about how other data formats can be handled if the API you plan to connect to uses a different data format.
