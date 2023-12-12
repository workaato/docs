 ---
title: オンプレミス接続
date: 2023-01-25 12:00:00
tags:
    - オンプレミスエージェント
    - オンプレミス接続
    - オンプレミスコネクティビティ
topicType: general
---

# オンプレミス接続
<br>
<Video src="https://www.youtube.com/embed/iAb2xXk9R8I" />

エンタープライズは、セキュリティとプライバシーの管理を強化するために、制限されたネットワーク内にアプリケーションとデータベースを展開しています。ファイアウォールは、これらのプライベート環境とパブリックインターネットのデータフローを監視および制御します。そのため、これらのプライベートIT環境にホストされたアプリケーションとデータは、通常、Workatoのようなクラウドサービスからアクセスできません。

Workatoのオンプレミスエージェントを使用すると、プライベートIT環境内からWorkatoクラウドに安全な接続を作成できます。これにより、セキュリティの制御を維持しながら、ハイブリッドクラウドやマルチクラウドアーキテクチャを完全に統合できます。

> オンプレミスアクセスは、特定のユーザーのみが有効です。詳細については、カスタマーサクセスマネージャーにお問い合わせください。

## 概要
以下は、Workatoのオンプレミスエージェントがファイアウォールの背後にあるデータベースとアプリケーションとどのように連携するかを示した概念モデルです。

![オンプレミスモデル](~@img/on-prem/on_prem_conceptual_model.png)
*オンプレミスエージェントとコネクタの概念モデル*

オンプレミスエージェントは、[オンプレミスグループ](/on-prem/groups.md)と呼ばれる論理グループにもインストールでき、**高可用性**と**負荷分散**の機能を実現できます。

![オンプレミスグループモデル](~@img/on-prem/on_prem_group_conceptual_model.png)
*オンプレミスエージェントのグループの概念モデル*

## 動作原理
Workatoのオンプレミス接続には、次の2つの主要なコンポーネントがあります：
- トンネリング
- データベース、ファイルシステム、およびアプリケーションへのアクセス

オンプレミスエージェントは、通常はファイアウォールの背後にあるユーザーのサーバー内で実行され、TLS WebSocketトンネルを確立してWorkatoに接続します。

オンプレミスエージェントはファイアウォールの背後にあるシステムと同じネットワーク内にあるため、安全にアクセスし、Workatoに安全に通信するためのエージェントとして機能します。

## サポートされているオペレーティングシステム
オンプレミスエージェントは、次のシステムで実行されます：

- Linux（64ビット）
- Windows 7、10、11（64ビット）
- Mac OS X
- Windows Server 2008以降（OPA [v2.8.0](/on-prem/agents/versions.md#v2-8)より前）
- Windows Server 2012 R2以降（OPA [v2.8.0](/on-prem/agents/versions.md#v2-8)以降）

最小ハードウェア要件は：

- 8 GBのRAM
- 250 MBのディスクスペース
- 800 Mhz 64ビットCPU（Intel/AMD）

各オペレーティングシステムでOPAをセットアップする方法については、[オンプレミスセットアップガイド](/on-prem/agents/setup.md)をご覧ください。

## OPAはマルチクラウドやパブリッククラウドで使用できますか？
はい、WorkatoのOPAはどのIT環境でも使用できます。OPAを[Amazon Web Service](https://aws.amazon.com/)、[Azure cloud](https://azure.microsoft.com/en-us/)、または[Google Cloud Platform](https://cloud.google.com/)のようなパブリッククラウド上で実行することもできます。また、OPAをプライベートマシン上で実行することもできます。

OPAは、互換性のあるオペレーティングシステムがあれば、仮想マシンまたは物理マシン上で実行できます。[サポートされているオペレーティングシステム](#supported-operating-systems)について詳しくは、ご覧ください。

## オンプレミスの権限
Workatoの[ロールベースのアクセス制御](/privileges.md#on-premise)を使用して、オンプレミスの機能へのアクセスを設定できます。

## このセクションの内容
* [オンプレミスグループ](/on-prem/groups.md)
  * [グループの作成](/on-prem/groups/create-group.md)
  * [エージェントのグループへの追加](/on-prem/groups/add-agent.md)
  * [グループのステータス](/on-prem/groups/group-status.md)
  * [共通の設定](/on-prem/groups/common-config.md)
* [オンプレミスエージェント](/on-prem/agents.md)
  * [エージェントのセットアップ](/on-prem/agents/setup.md)
  * [エージェントの実行](/on-prem/agents/run.md)
  * [エージェントのアップグレード](/on-prem/agents/upgrade.md)
  * [プロファイル](/on-prem/agents/connection/profile.md)
  * [オンプレミス接続](/on-prem/agents/connection.md)
  * [パスワードの暗号化](/on-prem/agents/password-encryption.md)
  * [プロキシサーバー](/on-prem/agents/proxy.md)
  * [ログ](/on-prem/agents/logging.md)
  * [拡張機能](/on-prem/agents/extension.md)