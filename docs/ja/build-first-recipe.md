 # 最初のレシピを作成する
::: details このビデオガイドで最初のレシピを作成しましょう
<Video src="https://www.youtube.com/embed/H4MMLklNpPU"/>
:::

レシピは、アプリを接続する自動化ワークフローです。各レシピは、トリガーと1つ以上のアクションで構成されています。レシピをオンにすると、アクションを実行するためにトリガーイベントを待機します。

以下の手順に従って、Jiraで名前が同じ問題がクローズされた場合にSalesforceのケースをクローズするレシピを作成します。

## 開始する前に
* Jiraアカウントに接続するには、ホスト名、メールアドレス、APIトークンが必要です。<br>APIトークンの生成方法については、[AtlassianでAPIトークンを作成する](/connectors/jira.md#how-to-connect-to-jira-on-workato)を参照してください。
* Salesforceアカウントに接続するには、ユーザ名とパスワードが必要です。

1. **Assets**に移動し、**Create Recipe**をクリックします。
2. **Name**フィールドに `My first recipe` を入力します。
3. **Start building**をクリックします。 ![Setup your recipe view](~@img/first-recipe/setup-recipe-view.png)

## ステップ2: Jiraに接続する
1. Jiraアプリを検索します。
2. **Updated issue**を選択します。<br>接続ページが開きます。
3. **Connection name**フィールドに接続の名前を入力します。<br>レシピ間で接続を再利用できるため、アカウントを識別できるように記述的な名前を入力してください。例えば `Test Jira account` と入力します。
4. JiraアカウントのURLを入力します。
5. 認証にAPIトークンを使用する場合は `Yes` を選択します。
6. Jiraにログインするためのメールアドレスを入力します。
7. Atlassianから取得したAPIトークンを入力します。
4. **Connect**をクリックします。<br>
トリガーフィールドを設定できるようになります。

## ステップ3: トリガーを設定する
このレシピは、問題がクローズされるたびに実行されます。レシピを開始すると、過去7日間の一致するイベントをチェックします。
1. **When first started...**フィールドにこの式を入力します: `7.days.ago`
2. トリガー条件を設定するためにクリックします。
3. **Recipe data**ウィンドウで、**Status > Name**を検索します。
4. **Name**データピルを**Trigger data**フィールドにドラッグします。
![Search for and drag the datapill](~@img/first-recipe/datapill.gif)
5. 条件を`contains`に設定します。
6. 値を`Closed`に設定します。
![Trigger fields](~@img/first-recipe/trigger-fields.png)

## ステップ4: Salesforceに接続する
1. **Actions**の下にある+をクリックし、**Action in app**をクリックします。
2. Salesforceアプリを検索します。
3. **Search records**を選択します。<br>接続ページが開きます。
4. **Connection name**フィールドに接続の説明的な名前を入力します。
5. **Connect**をクリックします。<br>
Salesforceのログインページが新しいウィンドウで開きます。
6. ユーザ名とパスワードを入力し、**Log In**をクリックします。<br>
アクションフィールドを設定できるようになります。

## ステップ5: アクションを設定する
このレシピは、Jiraの問題と同じケース名を持つSalesforceのケースを検索します。
1. **Search for**フィールドで**Case**を選択します。
2. `150`件のレコードを制限に入力します。
3. **Summary**データピルを**Subject**フィールドにドラッグします。
![Action fields](~@img/first-recipe/action-fields.png)

## ステップ6: 条件文を設定する
このステップでは、レシピがSalesforceのケースがクローズされているかどうかをチェックし、クローズされていない場合はステータスをクローズに更新します。
1. **Actions**の下にある+をクリックし、**IF condition**をクリックします。
2. **Status**データピルを**Data field**にドラッグします。
3. **equals**条件を選択します。
4. **Value**フィールドに`Closed`を入力します。
![Conditional step](~@img/first-recipe/if-condition.png)
5. **Select an app..**をクリックします。
6. Salesforceアプリを選択します > **Update record**を選択します。<br>アクションは、ステップ4で確立した接続を自動的に選択します。
7. **Case**を選択します。
8. **Case ID**データピルを**Case ID**フィールドにドラッグします。
9. **Closed**ステータスを選択します。
![Conditional step fields](~@img/first-recipe/if-condition-fields.png)

## ステップ7: レシピを保存して開始する
1. **Save**をクリックしてから**Exit**をクリックします。
2. **Start recipe**をクリックします。
完成したレシピは、この[レシピ](https://app.workato.com/recipes/837151-closed-jira-issues-close-salesforce-cases?community=true)と一致するはずです。

## 次は何をするか
次にできるいくつかのアイデア:
- 他のユーザーが作成した使用準備ができたレシピを見つけるために[Community library](https://app.workato.com/browse/recipes)を探索してみてください。
- [recipe components](/recipes/building-recipes.md#learn-more-about-recipe-components)で他のタイプのトリガーやアクションについて詳しく学びましょう。