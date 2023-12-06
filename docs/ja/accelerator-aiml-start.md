 ---
title: AIMLアクセラレータの開始
date: 2022-12-12 00:00:00
topictype: task
---

# AIMLアクセラレータの開始 {: #main :} 

## レシピの開始 {: #recipes :}

<Stepper>

<Step>

**Projects > Home > AIML Accelerator**に移動します。

</Step>
<Step>

以下のフォルダ内のすべてのレシピを次の順序で開始します：

1. APIエンドポイント
2. AWS S3
3. AWS Sagemaker
4. 関数

</Step>
</Stepper>

## スキーマの読み込み {: #schema-load :}

**AIML|Data Fields**ルックアップテーブルには、SageMakerに展開されたデータモデルのスキーマが保存されます。WorkatoはデータをSagemakerに送信してデータモデルを作成し、トレーニングします。Sagemakerは、このデータを**AIML | Data Fields**ルックアップテーブルで定義されたルールに基づいて検証します。

![AIMLデータフィールド](~@img/data-fields-lookup.png)_データフィールドルックアップテーブル_

**AIML | Data Fields**ルックアップテーブルを設定する方法は2つあります。最初のオプションは、**Add Entry**をクリックして各データフィールドを手動で設定することです。2番目のオプションは、**AIML|REC-009|Load Model Schema**レシピを使用してこのプロセスを自動化することです。このレシピはまた、**AIML | Model Profile**ルックアップテーブルにエントリを追加します。

**AIML | REC-009 | Load Model Schema**レシピを使用する手順は次のとおりです：

<Stepper>
<Step>

Workatoで、**Projects > Home > AIML Accelerator > Bootstrap**に移動します。

</Step>
<Step>

**AIML | REC-009 | Load Model Schema**を選択します。

</Step>
<Step>

**Step 2**で入力フィールドを設定します。

![入力フィールドの設定](~@img/load-schema-recipe.png)_入力フィールドの設定_

<dl>
	<dt>model_Identifier</dt>
	<dd>機械学習モデルを識別するための一意でわかりやすい名前を指定します。</dd>
	<dt>headers</dt>
	<dd>スキーマの列名をスペースなしのCSV形式で指定します。</dd>
	<dt>prediction_col_name</dt>
	<dd>予測列の名前を指定します。</dd>
	<dt>datetime_format</dt>
	<dd>データに日時値が含まれる場合、Workatoが解析するための形式を指定します。Workatoがサポートする形式の一覧については、<a href="/formulas/date-formulas.html#strftime">日時の形式</a>を参照してください。</dd>
</dl>

</Step>
<Step>

**Step 3**で、データモデルが使用するサンプルCSVデータを提供します。

例：
```
id,first_name,last_name,email,ip_address
1,Lucy,Carrigan,lcarrigan@example.com,123.45.678.900
2,Jude,Feeney,jfeeney@example.com,987.65.43.210.012
3,Sadie,Simmons,ssimmons@example.com,345.67.890.100
```

</Step>
<Step>

**Test**をクリックしてレシピを1回実行します。

</Step>
<Step>

**AIML|Data Fields**ルックアップテーブルに更新された値があるかどうかを確認するために移動します。

</Step>
<Step>

入力フィールドを設定して、検証ルールを手動で指定します。

![](~@img/datafields-lookup.png)

<dl>
	<dt>Workatoデータ型</dt>
	<dd>フィールドのデータ型を指定します。Workatoがサポートするデータ型の一覧については、<a href="/recipes/data-pills-and-mapping.html#data-types">Workatoがサポートするデータ型</a>を参照してください。</dd>
	<dt>必須 (true/false)</dt>
	<dd>フィールドが必須フィールドの場合は<strong>true</strong>に設定します。フィールドが必須でない場合は<strong>false</strong>に設定するか、空白のままにします。</dd>
	<dt>一意 (true/false)</dt>
	<dd>フィールドの値がモデルのトレーニングに使用されるデータセット内で一意である必要がある場合は<strong>true</strong>に設定します。一意である必要がない場合は<strong>false</strong>に設定するか、空白のままにします。</dd>
	<dt>正規表現パターン</dt>
	<dd>Workatoはデータをこのパターンに対してチェックします。</dd>
</dl>

</Step>
</Stepper>

## モデルプロファイルの定義 {: #profile-define :}

**AIML|Model Profile**ルックアップテーブルには、ソリューションで使用される機械学習モデルのモデルプロファイルが保存されます。レシピはこれらのプロファイルを使用してデータを読み取り、機械学習プラットフォームに接続します。

モデルプロファイルを定義するための手順は次のとおりです。**AIML|REC-009|Load Model Schema**レシピを使用した場合は、ステップ3に進むことができます：

<Stepper>

<Step>

Workatoで、**Tools > Lookup tables**に移動し、利用可能なルックアップテーブルのリストから**AIML|Model Profile**ルックアップテーブルを選択します。

</Step>
<Step>

ルックアップテーブルにエントリを追加し、モデルに**Model Identifier**を指定します。この**Model Identifier**は、**AIML|Data Fields**ルックアップテーブルで指定した**Model Identifier**と一致する必要があります。

</Step>
<Step>

JSON形式で**AIML | Connection Profile**を指定します。Workatoは、機械学習モデルに接続するためにこれらのパラメータを必要とします。

以下はSagemakerの例です：

```json
{
	"endpoint_name":"{Unique Endpoint_name}",
	"role_arn":"arn:aws:iam::xxxx:role/service-role/AmazonSageMaker-xxxxRole-xxxx"
}
```
</Step>
<Step>

JSON形式で**Storage Source Connection Profile**を指定します。Workatoは、ソースデータの保存場所に接続するためにこれらのパラメータを必要とします。

以下はAWS S3の例です：

```json
{ 
	"accelerate": "false", 
	"region": "xx-xxx-x", 
	"bucket": "xxxx", 
	"object_name": "xxxxx_training_data.csv" 
}
```

</Step>
<Step>

JSON形式で**Storage Target Connection Profile**を指定します。Workatoは、検証後にターゲットデータを移動し、Sageに渡すためにこれらのパラメータを必要とします。

以下はAWS S3の例です：

```json
{ 
	"accelerate": "false", 
	"region": "xx-xxx-x", 
	"bucket": "xxxx", 
	"object_name": "xxxxx_training_data.csv" 
}
```

</Step>
</Stepper> Maker. Workatoは、ストレージ場所との接続にこれらのパラメータを必要とします。

以下の例では、AWS S3に対して次のように設定しました。

```json
{ 
	"accelerate": "false", 
	"region": "xx-xxx-x", 
	"bucket": "xxxx", 
	"object_name": "xxxxx_training_data.csv" 
}
```

</Step>
<Step>

**MLモデルの数**を指定してください。この数値は、機械学習モデルが作成するモデルの数を定義します。

</Step>
</Stepper>

::: note MLモデルの数
MLモデルの数が多いほど、計算リソースが増え、ジョブの実行時間が長くなります。また、一般的には、モデルの品質も向上します。
:::