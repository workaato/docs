 # アプリ接続
::: details クイックビデオガイドを見る

<Video src="https://www.youtube.com/embed/m3lajUatO7w" />

レシピの作成を開始する際には、最初にWorkatoとアプリの間に接続を確立する必要があります。

各接続は、ユーザーアカウントなどのアプリのインスタンスに関連付けられ、レシピ間で再利用することができます。

このガイドでは、以下の内容を説明します：

- [接続の基本](#connection-basics)
- [接続の作成](#creating-connections)
- [レシピでの接続の使用方法](#using-connections-in-recipes)
- [接続エラーの処理方法](#connection-errors)

---

## 接続の基本

- [誰が接続を作成できるのか？](#who-can-create-connections)
- [Workatoは接続にどのようにアクセスするのか？](#how-does-workato-access-my-connections)
- [Workatoは接続でどのデータにアクセスできるのか？](#what-data-can-workato-access-in-my-connections)
- [どのようなベストプラクティスを守るべきか？](#what-best-practices-should-i-follow)

### 誰が接続を作成できるのか？

接続を作成するには、[**接続の作成**特権](/ja/user-accounts-and-teams/role-based-access/collaborator-roles-and-permissions.md#recipe-development-privileges)が必要です。

手順については、[接続の作成](#creating-connections)セクションを参照してください。

### Workatoは接続にどのようにアクセスするのか？

Workatoは通常、アプリの認証/認可APIを使用して接続を確立します。以下のいずれかの方法を使用します：

- OAuth 2.0
- OAuth 1.0（およびそのバリエーション）
- ベーシック認証（ユーザー名とパスワード）
- APIキーまたはシークレット

この手順の一環として、Workatoにアプリのデータへのアクセス許可を提供します。Workatoに付与される権限は通常、[アプリの認証を行うユーザー](#what-data-can-workato-access-in-my-connections)の権限と対応しています。

Workatoに接続する方法の詳細については、アプリの[コネクタドキュメント](/ja/connectors.md)を参照してください。

### Workatoは接続でどのデータにアクセスできるのか？

Workatoは、接続を認証するユーザーがアクセスできるデータにのみアクセスできます。

例えば：Salesforceでアカウントの表示権限しか持っていない場合、WorkatoでSalesforce接続を作成しても、Workatoはアカウントの表示しかできません。

### どのようなベストプラクティスを守るべきか？

接続を作成する際には、次のことをお勧めします：

- [Workatoのための専用ユーザーの作成](#creating-a-dedicated-user-for-workato)
- [開発用のサンドボックス認証情報の使用](#using-sandbox-credentials-for-development)

#### Workatoのための専用ユーザーの作成

Workatoのために専用のアプリユーザーを作成することで、レシピが人間のユーザーアカウントに依存しないようにします。誰かが会社を去っても、レシピは引き続き実行されます。

さらに、専用のWorkatoユーザーを作成することで、Workatoがアプリ内で持つ権限を調整することができ、セキュリティリスクを低減できます。

アプリには、ユーザーの役割と権限を定義する際に異なる細かさがあります。Workatoに接続する方法の詳細については、アプリの[コネクタドキュメント](/ja/connectors.md)を参照してください。 #### 開発にはサンドボックスの資格情報を使用する

レシピを開発およびテストする際には、接続にサンドボックス（または非本番）の資格情報を使用することをお勧めします。開発中にテストデータを使用することで、ライブデータが誤って変更されることを防ぐことができます。

詳細については、[レシピでの接続の使用](#using-connections-in-recipes)セクションを参照してください。

---

## 接続の作成

Workatoでアプリを接続する方法は2つあります。

- [レシピエディタで](#in-the-recipe-editor)
- [接続ウィザードで](#in-the-connection-wizard)

### レシピエディタで

レシピエディタで接続を追加するには:

<Stepper>
<Step>

レシピエディタで、サイドメニューからアプリをクリックします。

</Step>
<Step>

使用したいトリガーまたはアクションをクリックします。

</Step>
<Step>

アプリの[セットアップガイド](/ja/connectors.md)に従って、プロンプトに従います。

</Step>
</Stepper>

![新しいレシピを介した接続](@img/recipes/app-connections/via-new-recipe.gif)

### 接続ウィザードで

Workatoのいくつかの場所から接続ウィザードにアクセスできます:

- **リソース > 接続 > 接続の作成**
- **リソース > レシピ > 接続の作成**
- **任意のプロジェクト > 接続の作成**

![新しい接続を介した接続](@img/recipes/app-connections/via-new-connection.gif)

---

## レシピでの接続の使用

::: warning 重要!
トリガーやアクションをレシピで設定する前に、アプリへの有効な接続を確立する必要があります。
:::

- [複数のアプリインスタンス、1つのレシピ](#multiple-app-instances-one-recipe)
- [ランタイムユーザー接続](#runtime-user-connections)

### 複数のアプリインスタンス、1つのレシピ

通常、アプリのインスタンスは1つまたは2つあります - 本番用の1つと、テスト用のもう1つかもしれません。このようなシナリオでは、複数のレシピで使用するために1つの接続が必要になるでしょう。

アプリの複数のインスタンスがある場合、Workatoで複数の接続を作成する必要があります。各接続は、アプリの各インスタンスに対して認証を行う必要があります。

ほとんどのコネクタは、レシピごとにアプリごとに1つの接続しか許可しません。2つの別々のアプリインスタンスで作業する必要がある場合は、[セカンダリコネクタ](/ja/features/secondary-connectors.md)を使用することができます。

**注意**: セカンダリコネクタは、すべてのWorkatoコネクタでサポートされているわけではありません。

### ランタイムユーザー接続

:::tip CALLABLE & WORKBOT RECIPESで利用可能
**ランタイムユーザー接続**機能は、CallableまたはWorkbotレシピでのみ利用可能です。
:::

デフォルトでは、レシピは接続の認証に使用された資格情報に基づいてアクションを実行します。ただし、**ランタイムユーザー接続**機能を使用することで、レシピが実行される際に接続を切り替えることができます。

例えば: Salesforceに機会を作成するレシピがあるとします。Salesforceの接続は現在、営業マネージャーの資格情報を使用しています。他の営業担当者が機会を作成しているにもかかわらず、すべての機会は営業マネージャーによって作成されたものとして表示されます。

詳細については、[ランタイムユーザー接続のドキュメント](/ja/features/ ## 接続エラー

時折、アプリの接続が無効になることがあります。以下は最も一般的な理由です：

- **変更された資格情報。** アプリ内で資格情報が変更され、Workatoで変更されていない場合、接続が無効になる可能性があります。
- **不十分な権限。** この場合、接続を承認するユーザーには必要なデータにアクセスしたり、特定のアクションを実行するための権限がありません。

無効な接続エラーが発生した場合は、以下をおすすめします：

- **接続を承認するユーザーの権限を確認します。** 接続を承認するユーザーが十分な権限を持っていることを確認してください。
- **接続の資格情報が正しいことを確認します。** パスワード、APIキーなどが正しく入力されているかを再度確認してください。
- **接続を再承認します。** ユーザーの権限と資格情報を確認した後、接続を再度行ってみてください。

![アプリ接続エラーのデザイン時エラー](~@img/recipes/troubleshooting/connection-error.png)
*アプリ接続エラーのデザイン時エラー*

---