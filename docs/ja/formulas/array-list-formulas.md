 # リストとハッシュの式

基本的なデータ型（例：文字列や整数）に加えて、複数のアイテムに関する情報や単一のアイテムに関する複数の情報を含む、より複雑なデータ構造に遭遇することがあります。

以下のデータ構造に遭遇することがあります：

- [リスト](#lists-arrays)（または配列とも呼ばれます）
- [ハッシュ](#hashes)
- [ハッシュのリスト](#lists-of-hashes)

Workatoの式はRubyメソッドのallowlistに追加されるため、すべてのRubyメソッドがサポートされているわけではありません。追加の式をallowlistに追加するには、[お問い合わせください](https://support.workato.com/en/support/tickets/new)。

---

## リスト（配列）

配列は、任意のオブジェクトの順序付けられた整数インデックスのコレクションです。リストのインデックスは0から始まります。リストと配列は同じデータ構造を指します。

以下の例では、整数のリストが次のように表されています：

```ruby
number_list = [100, 101, 102, 103, 104]
```

リストは順序があるため、以下の式を使用して値を取得できます。Workatoでは、この構文を使用して最大5つのアイテムまで取得できます。

| 式                 | 結果   |
| ------------------ | ------ |
| number_list.first  | 100    |
| number_list.second | 101    |
| number_list.third  | 102    |
| number_list.fourth | 103    |
| number_list.fifth  | 104    |
| number_list.last   | 104    |

インデックスを使用して対応する値を取得することもできます。インデックスは0から始まることを覚えておいてください：

| 式           | 結果   |
| ------------ | ------ |
| number_list[0] | 100    |
| number_list[1] | 101    |
| number_list[2] | 102    |
| number_list[3] | 103    |

Rubyのリストは負のインデックスもサポートしています。

| 式             | 結果   |
| --------------- | ------ |
| number_list[-1] | 104    |
| number_list[-2] | 103    |
| number_list[-3] | 102    |
| number_list[-4] | 101    |

リストは範囲もインデックスとしてサポートしています。これにより、値だけでなく別のリストが返されます。

| 式                 | 結果               |
| ------------------- | -------------------- |
| number_list[0..2]   | [100, 101, 102]      |
| number_list[-3..-1] | [102, 103, 104]      |
| number_list[0..-2]  | [100, 101, 102, 103] |

---

## ハッシュ

ハッシュは、一意のキーとその値の辞書のようなコレクションです。リストと似ていますが、リストは整数をインデックスとして使用するのに対し、ハッシュでは任意のオブジェクト型を使用できます。ハッシュは、対応するキーが挿入された順序で値を列挙します。

次の例では、item_nameに `'Acme widgets'`、item_quantityに `10` の値を持つハッシュを取り上げます。

```ruby
line_item = { 'item_name' => 'Acme widgets', 'item_qty' => 10 }
```

| 式                     | 結果           |
| ---------------------- | -------------- |
| line_item["item_name"] | "Acme widgets" |
| line_item["item_qty"]  | 10             |

---

## ハッシュのリスト

複数のラインアイテムを持つ請求書の例を以下に示します。これはハッシュのリストとして表されます。 ashes.

```ruby
line_items = [
  { 'item_no': 1, 'item_name' => 'Acme widgets', 'item_qty' => 10 },
  { 'item_no': 2, 'item_name' => 'RR bearings',  'item_qty' => 99 },
  { 'item_no': 3, 'item_name' => 'Coyote tyres', 'item_qty' => 7 }
]
```

---

### ハッシュのリストの例

以下は、**Contacts** と呼ばれるハッシュのリストの例です。

このリストは、テーブル形式で表示されます。

| name | email        | state | company | company_rev |
| ---- | ------------ | ----- | ------- | ----------- |
| Joe  | joe@abc.om   | CA    | ABC     | 1000        |
| Jill | jill@nbc.com | MA    | NBC     | 1000        |
| Joan | joan@nbc.com | MA    | NBC     | 10000       |
| Jack | jack@hbo.com | CA    | HBO     | 30000       |

このリストは、ハッシュのリスト形式で表示されます。

```ruby
[
  {
    'name' => 'Joe',
    'email' => 'joe@abc.com',
    'state' => 'CA',
    'company' => 'ABC',
    'company_rev' => 1000,
    'description' => { 'summary' => '初めての購入者', 'estimated_value' => 300 }
  },
  {
    'name' => 'Jill',
    'email' => 'jill@nbc.com',
    'state' => 'MA',
    'company' => 'NBC',
    'company_rev' => 1000,
    'description' => { 'summary' => '紹介', 'estimated_value' => 500 }
  },
  {
    'name' => 'Joan',
    'email' => 'joan@nbc.com',
    'state' => 'MA',
    'company' => 'NBC',
    'company_rev' => 10000,
    'description' => { 'summary' => 'リピーター', 'estimated_value' => 900 }
  },
  {
    'name' => 'Jack',
    'email' => 'jack@hbo.com',
    'state' => 'CA',
    'company' => 'HBO',
    'company_rev' => 30000,
    'description' => { 'summary' => 'リピーター', 'estimated_value' => 1000 }
  }
]
```
---

## リストの数式

---

### `first`

この数式は、リストの最初のアイテムを返します。

また、リストの最初の _n_ 個のアイテムを返すこともできます。この場合、出力はリスト形式でフォーマットされます。

#### 構文

<kbd>List</kbd>.first(<span style="color:#FF0000">number</span>)

- <kbd>List</kbd> - 入力リスト。
- <span style="color:#FF0000">number</span> - (オプション) リストから取得するアイテムの数。指定しない場合、数式は _1_ つのアイテムのみを返します。

#### 使用例

| 数式                                                  | 結果          |
| ------------------------------------------------------- | ------------- |
| <kbd>["One","Two","Three","Four","Five"]</kbd>.first()  | "One"         |
| <kbd>["One","Two","Three","Four","Five"]</kbd>.first(2) | ["One","Two"] |
| <kbd>[1,2,3,4,5]</kbd>.first()                          | 1             |
| <kbd>[1,2,3,4,5]</kbd>.first(3)                         | [1,2,3]       |

#### 動作原理

この数式は、リストから最初の _n_ 個のアイテムを返します。_n_ が 1 より大きい場合、出力はリスト形式でフォーマットされます。

::: tip 出力のデータ型
アイテムが 1 つだけの場合 (つまり引数が指定されていない場合)、出力はアイテムのデータ型に従ってフォーマットされます。

複数のアイテムを返す場合、出力はリストのデータ型でフォーマットされます。 :::

#### 関連情報

- [last](/formulas/array-list-formulas.md#last): リスト内の最後の _n_ 個のアイテムを返します。
- [where](/formulas/array-list-formulas.md#where): 特定の条件を満たすリストアイテムのサブセットを返します。

---

### `last`

この式は、リスト内の最後のアイテムを返します。

また、リスト内の最後の _n_ 個のアイテムを返すためにも使用できます。この場合、出力はリストとしてフォーマットされます。

#### 構文

<kbd>List</kbd>.last(<span style="color:#FF0000">number</span>)

- <kbd>List</kbd> - 入力リスト。
- <span style="color:#FF0000">number</span> - (オプション) リストから取得するアイテムの数。指定しない場合、式は _1_ つのアイテムのみを返します。

#### 使用例

| 式                                                     | 結果            |
| ------------------------------------------------------- | --------------- |
| <kbd> ["One","Two","Three","Four","Five"]</kbd>.last()  | "Five"          |
| <kbd> ["One","Two","Three","Four","Five"]</kbd>.last(2) | ["Four","Five"] |
| <kbd>[1,2,3,4,5]</kbd>.last()                           | 5               |
| <kbd>[1,2,3,4,5]</kbd>.last(3)                          | [3,4,5]         |

#### 動作原理

この式は、リストから最後の _n_ 個のアイテムを返します。_n_ が 1 より大きい場合、出力はリストとしてフォーマットされます。

::: tip 出力のデータ型
単一のアイテムを返す場合 (つまり引数が指定されていない場合)、出力はアイテムのデータ型に従ってフォーマットされます。

複数のアイテムを返す場合、出力はリストのデータ型としてフォーマットされます。
:::

#### 関連情報

- [first](/formulas/array-list-formulas.md#first): リスト内の最初の _n_ 個のアイテムを返します。
- [where](/formulas/array-list-formulas.md#where): 特定の条件を満たすリストアイテムのサブセットを返します。

---

### `index`

指定された値に一致する最初のアイテムのインデックスを返します。一致するアイテムが見つからない場合は `nil` を返します。

#### 構文

<kbd>Input</kbd>.index(<span style="color:#FF0000">value</span>)

- <kbd>Input</kbd> - 入力リスト。
- <span style="color:#FF0000">value</span> - リスト内で検索する値。

#### 使用例

| 式               | 結果 |
| ----------------- | ------ |
| [4, 5, 6, 7].index(6) | 2      |
| [4, 5, 6, 7].index(8) | nil    |

---

### `where`

指定された WHERE 条件を満たす行 (ハッシュ) のみを取得します。この式は、1 つ以上のキーと値のペアを持つハッシュ形式の単一の引数を受け入れます。

条件のデフォルト演算子は **等しい** (`==`) です。この式はまた、以下の演算子もサポートしています。演算子はキーの末尾にスペースで区切って追加する必要があります。

| 名前                  | 表記 | 例                                  |
| --------------------- | -------- | ---------------------------------------- |
| 等しい (デフォルト)    | ==       | leads.where('state': 'CA')               |
| より大きい             | >        | leads.where('company_revenue >': 10000)  |
| 以上                   | >=       | leads.where('com pany_revenue >=': 10000) |
| Less than             | <        | leads.where('company_revenue <': 10000)  |
| Less than or equal to | <=       | leads.where('company_revenue <=': 10000) |
| Not equal to          | !=       | leads.where('state !=': 'CA')            |

::: tip データピルを条件引数として使用する
静的な値（例：`'CA'`）の代わりに、実行時にデータピルを条件引数として使用することができます。データピルの値は実行時に処理されます。

`contacts.where(state: ` <kbd>datapill</kbd> `)`
:::

#### 使用例

::: details 単一の where 条件の例
`contacts.where('state': 'CA')` は以下の行を返します：

| name | email        | state | company | company_rev |
| ---- | ------------ | ----- | ------- | ----------- |
| Joe  | joe@abc.om   | CA    | ABC     | 1000        |
| Jack | jack@hbo.com | CA    | HBO     | 30000       |

これらの行はハッシュのリストとして表されます：

```ruby
[
  {
    'name' => 'Joe',
    'email' => 'joe@abc.com',
    'state' => 'CA',
    'company' => 'ABC',
    'company_rev' => 1000
  },
  {
    'name' => 'Jack',
    'email' => 'jack@hbo.com',
    'state' => 'CA',
    'company' => 'HBO',
    'company_rev' => 30000
  }
]
```

:::

::: details 複合 where 式の例
複合 WHERE 式は、すべての条件に一致する行のみを取得します。

`contacts.where('state': 'CA', 'company_revenue >=': 10000)`

以下の行を返します：

| name | email        | state | company | company_rev |
| ---- | ------------ | ----- | ------- | ----------- |
| Jack | jack@hbo.com | CA    | HBO     | 30000       |

これらの行はハッシュのリストとして表されます：

```ruby
[
  {
    'name' => 'Jack',
    'email' => 'jack@hbo.com',
    'state' => 'CA',
    'company' => 'HBO',
    'company_rev' => 30000
  }
]
```

:::

::: details 複数の一致条件の例
特定のフィールドに対して複数の値に基づいてレコードをフィルタリングすることができます。これは、WHERE 条件に配列値を渡すことで行われます。

`contacts.where('company': ['ABC','HBO'])`

この WHERE 条件は、会社が **ABC** または **HBO** の場合に行が返されます：

| name | email        | state | company | company_rev |
| ---- | ------------ | ----- | ------- | ----------- |
| Joe  | joe@abc.om   | CA    | ABC     | 1000        |
| Jack | jack@hbo.com | CA    | HBO     | 30000       |

これらの行はハッシュのリストとして返されます。

```ruby
[
  {
    'name' => 'Joe',
    'email' => 'joe@abc.com',
    'state' => 'CA',
    'company' => 'ABC',
    'company_rev' => 1000
  },
  {
    'name' => 'Jack',
    'email' => 'jack@hbo.com',
    'state' => 'CA',
    'company' => 'HBO',
    'company_rev' => 30000
  }
]
```

:::

::: details パターンマッチングを使用した where 条件の例
正規表現を使用してレコードをフィルタリングすることもできます。これは、文字列の代わりに正規表現を渡すことで行われます。

`contacts.where('name': /^Jo/)`

この WHERE 条件は、名前が **Jo** で始まる行を返します：

| name | email        | state | company | company_rev |
| ---- | ------------ | ----- | ------- | ----------- |
| Joe  | joe@abc.om   | CA    | ABC     | 1000        |
| John | john@xyz.com | NY    | XYZ     | 5000        |

これらの行はハッシュのリストとして返されます。

```ruby
[
  {
    'name' => 'Joe',
    'email' => 'joe@abc.com',
    'state' => 'CA',
    'company' => 'ABC',
    'company_rev' => 1000
  },
  {
    'name' => 'John',
    'email' => 'john@xyz.com',
    'state' => 'NY',
    'company' => 'XYZ',
    'company_rev' => 5000
  }
]
```

:::

以上が、WHERE 条件の使用例です。これにより、データベースから特定の条件に一致する行を取得することができます。 te | company | company_rev |
| ---- | ------------ | ----- | ------- | ----------- |
| Joe  | joe@abc.om   | CA    | ABC     | 1000        |
| Joan | joan@nbc.com | MA    | NBC     | 10000       |

これらの行はハッシュのリストとして表されます:

```ruby
[
  {
    'name' => 'Joe',
    'email' => 'joe@abc.com',
    'state' => 'CA',
    'company' => 'ABC',
    'company_rev' => 1000
  },
  {
    'name' => 'Joan',
    'email' => 'joan@nbc.com',
    'state' => 'MA',
    'company' => 'NBC',
    'company_rev' => 10000
  }
]
```

:::

::: details データピルを使用したパターンマッチングの条件の例
正規表現パターン内でデータピルを使用して、マッチングする文字列を動的に変更することができます。ただし、正規表現パターン内で変数を使用する場合は、正規表現式内でエスケープする必要があります。

例: `contacts.where(state: /#{` <kbd>datapill</kbd> `}/)`

以下の画像は、Salesforceのデータピル `State | Step 2` の文字列を含む 'State' 列の値を持つルックアップテーブル内のすべての 'Emails' を取得する方法を示しています。

![Datapill in regex expression](~@img/formula-docs/regex-datapill.png)
_正規表現式内でデータピルを使用する_

**注意:** 正規表現のメタ文字は、メタ文字として解釈されない場合はすべてエスケープする必要があります。
:::

::: details WHERE 条件を連結する例
WHERE 条件を連結する場合、式は各 WHERE 条件を順番に評価します。

`contacts.where('state': 'CA').where('company_revenue >=': 10000)` は、次の行を返します。これは複合 WHERE 式と同じです。

| name | email        | state | company | company_rev |
| ---- | ------------ | ----- | ------- | ----------- |
| Jack | jack@hbo.com | CA    | HBO     | 30000       |

ただし、この場合、連結により中間配列が生成されます。

`contacts.where('state': 'CA')` は最初に次の結果を返します。

| name | email        | state | company | company_rev |
| ---- | ------------ | ----- | ------- | ----------- |
| Joe  | joe@abc.om   | CA    | ABC     | 1000        |
| Jack | jack@hbo.com | CA    | HBO     | 30000       |

そして、`.where('company_revenue >=': 10000)` はこの中間配列をさらにフィルタリングして次の行のみを返します。

| name | email        | state | company | company_rev |
| ---- | ------------ | ----- | ------- | ----------- |
| Jack | jack@hbo.com | CA    | HBO     | 30000       |

結果はハッシュのリストとして表されます:

```ruby
[
  {
    'name' => 'Jack',
    'email' => 'jack@hbo.com',
    'state' => 'CA',
    'company' => 'HBO',
    'company_rev' => '30000'
  }
]
```
:::

::: details NOT 演算子を連結する例
WHERE 式を使用して、NOT 演算子を連結することで、2つの配列の差分を見つけることができます。これは、元のリストと更新されたリストの2つのリストがあり、更新されたリストが元のリストのすべての値を含むことを確認するために比較する場合に便利です。

例: `contacts.where.not("id":updated_contacts.pluck('id'))` は、次の値を特定します。 ---

### `except`

指定されたキーを除いたハッシュを返します。

```ruby
hash = { a: true, b: false, c: nil }
hash.except(:c)     # => { a: true, b: false }
hash.except(:a, :b) # => { c: nil }
hash                # => { a: true, b: false, c: nil }
```

---

### `pluck`

指定された列のみを取得します。

#### 使用例

::: details 単一の列の出力の例
`contacts.pluck("email")` は次の結果を返します。

| email        |
| ------------ |
| joe@abc.com  |
| jill@nbc.com |
| joan@nbc.com |
| jack@hbo.com |

単一の列の場合、結果は配列として返されます。

```ruby
["joe@abc.com", "jill@nbc.com", "joan@nbc.com", "jack@hbo.com"]
```

:::

::: details 複数の列のデータセットの例
`contacts.where("state ==": "CA").pluck("email", "company")` は次の結果を返します。

| email        | company |
| ------------ | ------- |
| joe@abc.com  | ABC     |
| jill@nbc.com | NBC     |
| joan@nbc.com | NBC     |
| jack@hbo.com | HBO     |

結果はリストのリストとして返されます。

```ruby
[["joe@abc.com", "ABC"], ["jill@nbc.com", "NBC"], ["joan@nbc.com", "NBC"], ["jack@hbo.com", "HBO"]]
```

:::

::: details ネストされたフィールドの取得の例
このメソッドはネストされたフィールドを抽出するために使用できます。取得するフィールドを `[<1st-level field>,<2nd-level field>...]` の形式で定義します。

`contacts.pluck("email", ["description", "summary"])` は次の結果を返します。

| email        | summary            |
| ------------ | ------------------ |
| joe@abc.com  | 初めての購入者     |
| jill@nbc.com | 紹介               |
| joan@nbc.com | リピーター         |
| jack@hbo.com | リピーター         |

結果はリストのリストとして返されます。

```ruby
[
  ["joe@abc.com", "初めての購入者"],
  ["jill@nbc.com", "紹介"],
  ["joan@nbc.com", "リピーター"],
  ["jack@hbo.com", "リピーター"]
]
```

:::

---

### `format_map`

与えられたハッシュの配列の各行をフォーマットして文字列の配列を作成します。作成された文字列に静的テキストを追加することもできます。フォーマットするフィールドは %{**\<field_name>**} の形式で指定します。

#### 使用例

`contacts.format_map('名前: %{name}, メール: %{email}, 会社: %{company}') ` は次の結果を返します。

```ruby
[
  '名前: Joe, メール: joe@abc.com, 会社: ABC' ,
  '名前: Jill, メール: jill@nbc.com, 会社: NBC' ,
  '名前: Joan, メール: joan@nbc.com, 会社: NBC' ,
  '名前: Jack, メール: jack@hbo.com, 会社: HBO' ,
]
```

上記の例では、リスト **"contacts"** の各行に対して、名前、メール、会社の3つのフィールドからデータを使用して、文字列のリストを取得します。

---

### `join`

リスト内のすべてのアイテムをテキスト文字列に結合します。各アイテムの間にはセパレータが追加されます。

#### 構文

<kbd>List</kbd>.join(<span style="color:#FF0000">separator</span>)

- <kbd>List</kbd> - リストデータ型の入力です。
- <span style="color:#FF0000">separator</span> - 結合時にアイテム間に追加する文字です。 #### サンプルの使用方法

| 式                                            | 結果             |
| --------------------------------------------- | ---------------- |
| <kbd>["Ms", "Jean", "Marie"]</kbd>.join("-")  | "Ms-Jean-Marie"  |
| <kbd>[1,2,3]</kbd>.join("--")                 | "1--2--3"        |
| <kbd>["ab", "cd", "ef"]</kbd>.join            | "abcdef"         |

#### 動作原理

リストの要素は、1つのテキスト文字列に結合されます。各アイテムの間にはセパレータ文字が追加されます。

::: tip セパレータ文字
セパレータ引数として、文字列の連続を使用できます（たとえば、`", "`）。

<kbd>["Open","Pending","Closed"]</kbd>.join(", ") は `"Open, Pending, Closed"` を返します。
:::

#### 関連情報

- [split](/formulas/string-formulas.md#split): 指定された文字を基準に文字列を分割し、文字列の配列を返します。

---

### `smart_join`

リストの要素を文字列に結合します。空の値とnil値は削除され、結合前に空白がトリムされます。

#### 構文

<kbd>List</kbd>.smart_join(<span style="color:#FF0000">separator</span>)

- <kbd>List</kbd> - リストデータ型の入力です。
- <span style="color:#FF0000">separator</span> - 結合時にアイテム間に追加する文字。セパレータが指定されていない場合、結合文字として空白が使用されます。

#### サンプルの使用方法

| 式                                                                                   | 結果                                         |
| ------------------------------------------------------------------------------------- | ---------------------------------------------- |
| <kbd>[nil, "", "Hello", " ", "World"]</kbd>.smart_join(" ")                           | "Hello World"                                  |
| <kbd>["111 Vinewood Drive", "", "San Francisco", "CA", "95050"]</kbd>.smart_join(",") | "111 Vinewood Drive, San Francisco, CA, 95050" |

---

### `concat`

2つのリストを1つのリストに連結します。ネストされたリストはフラット化されません。

#### 構文

<kbd>List</kbd>.concat(<span style="color:#FF0000">list_to_be_joined</span>)

- <kbd>List</kbd> - リストデータ型の入力です。
- <span style="color:#FF0000">list_to_be_joined</span> - 元のリスト入力と連結する他のリストです。

#### サンプルの使用方法

| 式                                                                                           | 結果                                                                        |
| -------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| <kbd>["Hello", "World"]</kbd>.concat(<kbd>["Workato", "Rocks"]</kbd>)                        | <kbd>["Hello", "World", "Workato", "Rocks"]</kbd>                             |
| <kbd>["Hello", "World", ["Sub-array", "Here"]]</kbd>.concat(<kbd>["Workato", "Rocks"]</kbd>) | <kbd>["Hello", "World", ["Sub-array", "Here"], "Workato", "Rocks"]</kbd>      | 以下のように、英語で書かれたマークダウン形式のファイル（例：xxx.md）を日本語に翻訳してください。ただし、以下の部分（①-③）は英語のままにして、翻訳せずに元のままにしてください。また、マークダウン形式のファイルの形式を崩さないようにしてください。
① < > で囲まれた部分（例：<step>、</step>、<dd>など）
② {: :} で囲まれた部分（例：{: #prediction-get :}、{: #azure :}など）
③ ** ** で囲まれた部分（例：**Source**、**Enterprise Applications > Workato > Single Sign On > Attributes & Claims > Add a new claim**など）

 "Here"], "Workato", "Rocks"]</kbd>      |
| <kbd>["Hello", "World", nil, ["Sub-array", "Here"]]</kbd>.concat(<kbd>["Workato", "Rocks"]</kbd>) | <kbd>["Hello", "World", nil, ["Sub-array", "Here"], "Workato", "Rocks"]</kbd> |

---

### `reverse`

リストの順序を逆にします。

#### 構文

<kbd>List</kbd>.reverse

- <kbd>List</kbd> - リストデータ型の入力です。

#### 使用例

| 式                                                | 結果                          |
| -------------------------------------------------- | ------------------------------- |
| <kbd>["Joe", "Jill", "Joan", "Jack"]</kbd>.reverse | ["Jack", "Joan", "Jill", "Joe"] |
| <kbd>[100, 101, 102, 103]</kbd>.reverse            | [103, 102, 101, 100]            |

---

### `sum`

整数と小数の場合、数値は合計され、合計値が得られます。文字列の場合、文字列は連結されてより長い文字列が形成されます。

#### 構文

<kbd>List</kbd>.sum

- <kbd>List</kbd> - リストデータ型の入力です。

#### 使用例

| 式                       | 結果   |
| ----------------------------- | -------- |
| <kbd>[1, 2, 3]</kbd>.sum      | 6        |
| <kbd>[1.5, 2.5, 3]</kbd>.sum  | 7.0      |
| <kbd>["abc", "xyz"]</kbd>.sum | "abcxyz" |

---

### `uniq`

一意のアイテムを含むリストを返します。

#### 構文

<kbd>List</kbd>.uniq

- <kbd>List</kbd> - リストデータ型の入力です。

#### 使用例

| 式                                                | 結果                 |
| ------------------------------------------------------ | ---------------------- |
| <kbd>["joe", "jack", "jill", "joe", "jack"]</kbd>.uniq | ["joe","jack", "jill"] |
| <kbd>[1, 2, 3, 1, 1, 3]</kbd>.uniq                     | [1, 2, 3]              |
| <kbd>[1.0, 1.5, 1.0]</kbd>.uniq                        | [1.0, 1.5]             |

---

### `flatten`

多次元配列（つまり、配列の配列）を単一次元の配列に平坦化します。

#### 構文

<kbd>List</kbd>.flatten

- <kbd>List</kbd> - リストデータ型の入力です。

#### 使用例

| 式                                        | 結果                |
| ---------------------------------------------- | --------------------- |
| <kbd>[[1, 2, 3], [4, 5, 6]]</kbd>.flatten      | [1, 2, 3, 4, 5, 6]    |
| <kbd>[[1, [2, 3], 3], [4, 5, 6]]</kbd>.flatten | [1, 2, 3, 3, 4, 5, 6] |
| <kbd>[[1, [2, 3], 9], [9, 8, 7]]</kbd>.flatten | [1, 2, 3, 9, 9, 8, 7] |

---

### `length`

自身の要素数を返します。リストが空の場合は0を返します。

#### 構文

<kbd>List</kbd>.length

- <kbd>List</kbd> - リストデータ型の入力です。

#### 使用例

| 式                               | 結果 |
| ------------------------------------- | ------ |
| <kbd>[ 1, 2, 3, 4, 5 ]</kbd>.length   | 5      |
| <kbd>[{..}, {..}, {..}]</kbd>.length  | 3      |
| <kbd>[" ", nil, "", nil]</kbd>.length | 4      |
| <kbd>[]</kbd>.length                  | 0      |

---

### `max`

配列内の最大値を返します。数値を比較する場合、 #### Syntax

<kbd>List</kbd>.max

- <kbd>List</kbd> - リストデータ型の入力です。

#### 使用例

| 式                                      | 結果 |
| --------------------------------------- | ---- |
| <kbd>[-5, 0, 1, 2, 3, 4, 5]</kbd>.max   | 5    |
| <kbd>[-1.5, 1.5, 2, 3, 3.5]</kbd>.max   | 3.5  |
| <kbd>["cat", "dog", "rat"]</kbd>.max    | "rat"|

---

### `min`

配列内の最小値を返します。数値を比較する場合、最小の数値が返されます。文字列を比較する場合、ASCII値が最小の文字列が返されます。

#### 構文

<kbd>List</kbd>.min

- <kbd>List</kbd> - リストデータ型の入力です。

#### 使用例

| 式                                      | 結果 |
| --------------------------------------- | ---- |
| <kbd>[-5, 0, 1, 2, 3, 4, 5]</kbd>.min   | -5   |
| <kbd>[-1.5, 1.5, 2, 3, 3.5]</kbd>.min   | -1.5 |
| <kbd>["cat", "dog", "rat"]</kbd>.min    | "cat"|

---

### `compact`

配列とハッシュからnilの値を削除します。

#### 使用例

| 式                                                  | 結果             |
| --------------------------------------------------- | ---------------- |
| <kbd>["foo", nil, "bar"]</kbd>.compact              | ["foo", "bar"]   |
| <kbd>{ foo: 1, bar: nil, baz: 2 }</kbd>.compact     | { foo: 1, baz: 2 }|

---

## 条件分岐

---

### `blank?`

この式は、入力文字列が空の文字列またはnullである場合にtrueを返します。

#### 構文

<kbd>Input</kbd>.blank?

- <kbd>Input</kbd> - 入力データピルです。文字列、数値、日付、または日時データ型が使用できます。

#### 使用例

| 式                                      | 結果 |
| --------------------------------------- | ---- |
| <kbd>"Any Value"</kbd>.blank?           | false|
| <kbd>123</kbd>.blank?                   | false|
| <kbd>0</kbd>.blank?                     | false|
| <kbd>""</kbd>.blank?                    | true |

#### 動作方法

入力がnullまたは空の文字列の場合、式はtrueを返します。それ以外のデータに対しては、falseを返します。

#### 関連項目

- [presence](/formulas/string-formulas.md#presence): データが存在する場合はデータを返し、存在しない場合はnilを返します。
- [present?](/formulas/string-formulas.md#present): 有効な入力がある場合にtrueを返します。

---

### `include?`

文字列が特定の部分文字列を含んでいるか、リストが要素を含んでいるかを確認します。含んでいる場合はtrueを返します。

#### 構文

<kbd>Input</kbd>.include?(<span style="color:#FF0000">substring</span>)

- <kbd>Input</kbd> - 文字列またはリストの入力です。
- <span style="color:#FF0000">substring_or_element</span> - 確認する部分文字列または要素です。

#### 使用例

| 式                                                                 | 結果 |
| ------------------------------------------------------------------ | ---- |
| <kbd>"Partner account"</kbd>.include?("Partner")                   | true |

 >```markdown
>```ruby
>"Partner account".include?("partner")                                               | false  |
>["Hello", "World", ["Sub-array","Here"]"].include?("Hello")                         | true   |
>["Hello", "World", ["Sub-array","Here"]"].include?(["Sub-array","Here"]) | true   |
>```
>```
>
>#### 動作原理
>
>この式は、特定の部分文字列が含まれているか、リストに特定の要素が含まれているかをチェックします。含まれている場合はtrueを返し、それ以外の場合はfalseを返します。部分文字列の比較は大文字と小文字を区別し、要素の比較は完全一致です。
>
>この関数は[exclude?](#exclude)とは逆の動作をします。後者は、入力された文字列/リストが指定されたキーワード/要素を含まない場合にのみtrueを返します。
>
>#### 関連項目
>
>- [exclude?](#exclude): 特定の部分文字列が含まれているか、リストに要素が含まれているかをチェックします。含まれている場合はfalseを返します。
>
>---
>
>### `exclude?`
>
>特定の部分文字列が含まれているか、リストに要素が含まれているかをチェックします。含まれている場合はfalseを返します。
>
>#### 構文
>
><kbd>Input</kbd>.exclude?(<span style="color:#FF0000">substring</span>)
>
>- <kbd>Input</kbd> - 文字列またはリストの入力です。
>- <span style="color:#FF0000">substring_or_element</span> - チェックする部分文字列または要素です。
>
>#### 使用例
>
>| 式                                                                                        | 結果 |
>| ---------------------------------------------------------------------------------------------- | ------ |
>| <kbd>"Partner account"</kbd>.exclude?("Partner")                                               | false  |
>| <kbd>"Partner account"</kbd>.exclude?("partner")                                               | true   |
>| <kbd>["Hello", "World", ["Sub-array","Here"]"]</kbd>.include?("Hello")                         | false  |
>| <kbd>["Hello", "World", ["Sub-array","Here"]"]</kbd>.include?(<kbd>["Sub-array","Here"]</kbd>) | false  |
>
>#### 動作原理
>
>この式は、特定の部分文字列が含まれているか、リストに特定の要素が含まれているかをチェックします。含まれている場合はfalseを返し、それ以外の場合はtrueを返します。部分文字列の比較は大文字と小文字を区別し、要素の比較は完全一致です。
>
>この関数は[include?](#include)とは逆の動作をします。後者は、入力された文字列/リストが指定されたキーワード/要素を含む場合にのみtrueを返します。
>
>#### 関連項目
>
>- [include?](#include): 特定の部分文字列が含まれているか、リストに要素が含まれているかをチェックします。
>
>---
>
>### `present?`
>
>この式は、入力が存在する場合にtrueを返します。入力がnil、論理値false、空の文字列、または空のリストの場合、式はfalseを返します。
>
>#### 構文
>
><kbd>Input</kbd>.present?
>
>- <kbd>Input</kbd> - 入力データピルです。文字列、数値、日付、またはリストのデータ型であることができます。
>
>#### 使用例
>
>| 式                                                | 結果 |
>| ----------------------------------------------- ------- | ------ |
| <kbd>"Any Value"</kbd>.present?                        | true   |
| <kbd>123</kbd>.present?                                | true   |
| <kbd>0</kbd>.present?                                  | true   |
| <kbd>"2017-04-02T12:30:00.000000-07:00"</kbd>.present? | true   |
| <kbd>nil</kbd>.present?                                | false  |
| <kbd>""</kbd>.present?                                 | false  |
| <kbd>[]</kbd>.present?                                 | false  |

#### 動作原理

入力がnull、空の文字列、または空のリストの場合、この式はfalseを返します。それ以外のデータに対しては、trueを返します。

::: tip nil値を含むリストの評価

- 空のリストのみがfalseを返します。

<kbd>[]</kbd>.present? はfalseを返します。

- nilと空の文字列を含むリストはtrueを返します。

<kbd>[nil,""]</kbd>.present? はtrueを返します。
:::

#### 関連情報

- [presence](/formulas/array-list-formulas.md#presence): データが存在する場合はデータを返し、存在しない場合はnilを返します。
- [blank?](/formulas/array-list-formulas.md#blank): データが存在しないか、文字列が空白のみで構成されている場合はnilを返します。

---

### `presence`

データが存在する場合はデータを返し、存在しない場合はnilを返します。

#### 構文

<kbd>Input</kbd>.presence

- <kbd>Input</kbd> - 入力データピル。文字列、数値、日付、または日時のデータ型が使用できます。

#### 使用例

| 式                               | 結果        |
| ------------------------------- | ----------- |
| <kbd>nil</kbd>.presence         | nil         |
| <kbd>""</kbd>.presence          | nil         |
| <kbd>"Any Value"</kbd>.presence | "Any Value" |
| <kbd>45.0</kbd>.presence        | 45.0        |
| <kbd>0</kbd>.presence           | 0           |

#### 動作原理

入力がnullまたは空の文字列の場合、この式はnilを返します。それ以外のデータに対しては、元の入力データを返します。

#### 関連情報

- [blank?](/formulas/array-list-formulas.md#blank): データが存在しないか、文字列が空白のみで構成されている場合はnilを返します。
- [present?](/formulas/array-list-formulas.md#present): 有効な入力がある場合はtrueを返します。

---

## 変換

---

以下の式は、配列から他のデータ型にデータを変換するために使用できます。

---

### `to_csv`

配列からCSV行を生成します。エスケープ処理も行います。nil値と空の文字列もCSV行内で表現されます。

#### 構文

<kbd>Input</kbd>.to_csv

- <kbd>Input</kbd> - リストデータ型の入力です。

#### 使用例

| 式                                                            | 結果                            |
| ------------------------------------------------------------------ | --------------------------------- |
| <kbd>["John Smith", "No-Email", " ", nil, "555-1212"]</kbd>.to_csv | "John Smith,No-Email, ,,555-1212" |
| <kbd>["John Smith", "No-Email", " ", nil, 1212]</kbd>.to_csv       | "John Smith,No-Email, ,,1212"     |

---

### `to_json`

ハッシュまたは配列をJSON文字列に変換します。

#### 構文

<kbd>Input</kbd >.to_json

- <kbd>Input</kbd> - 入力データピル。リストまたはハッシュのデータ型が使用できます。

#### 使用例

| 式                                                     | 結果                          |
| ------------------------------------------------------ | ---------------------------- |
| <kbd>{"pet" => "cat", "color" => "gray"}</kbd>.to_json | {"pet":"cat","color":"gray"} |
| <kbd>["1","2","3"]</kbd>.to_json                       | ["1", "2", "3"]              |

---

### `to_xml`

ハッシュまたは配列をXML文字列に変換します。

#### 構文

<kbd>Input</kbd>.to_xml

- <kbd>Input</kbd> - 入力データピル。リストまたはハッシュのデータ型が使用できます。

#### 使用例

| 式                                              | 結果                                             |
| ------------------------------------------------ | ------------------------------------------------ |
| <kbd>{"name" => "Ken"}</kbd>.to_xml(root: "user") | \<user>\<name>Ken\</name>\</user>                  |
| <kbd>[{"name" => "Ken"}]</kbd>.to_xml(root: "users") | \<users>\<user>\<name>Ken\</name>\</user>\</users> |

---

### `from_xml`

XML文字列をハッシュに変換します。

#### 構文

<kbd>Input</kbd>.from_xml

- <kbd>Input</kbd> - 入力XMLデータ。

#### 使用例

::: details XML文字列をハッシュに変換する

このXML文字列:

`<?xml version=\"1.0\" encoding=\"UTF-8\" ?> <hash><foo type="integer">123</foo></hash>`

は、以下のXMLデータを表しています。

```xml
<?xml version=\"1.0\" encoding=\"UTF-8\" ?>

<hash>
  <foo type="integer">123</foo>
</hash>

```

<kbd>XML文字列</kbd>.from_xml は、以下のハッシュを返します。

```ruby
{ "hash":
  [ "foo":
    [
      { "@type": "integer",
        "content!": "1"
      }
    ]
  ]
}
```

:::

---

### `encode_www_form`

ハッシュをURLエンコードされたパラメータの文字列に結合します。

#### 構文

<kbd>Input</kbd>.encode_www_form

- <kbd>Input</kbd> - ハッシュの入力データ。

#### 使用例

| 式                                                         | 結果                |
| ----------------------------------------------------------- | --------------------- |
| <kbd>{"apple" => "red green", "2" => "3"}</kbd>.encode_www_form | "apple=red+green&2=3" |

---

### `to_param`

URLクエリ文字列として使用するための文字列表現を返します。

#### 構文

<kbd>Input</kbd>.to_param

- <kbd>Input</kbd> - ハッシュの入力データ。

#### 使用例

| 式                                       | 結果             |
| ----------------------------------------- | ------------------ |
| <kbd>{name: 'Jake', age: '22'}</kbd>.to_param | "name=Jake&age=22" |

---

### `keys`

入力ハッシュからキーの配列を返します。

#### 構文

<kbd>Input</kbd>.keys

- <kbd>Input</kbd> - ハッシュの入力データ。

#### 使用例

| 式                                           | 結果          |
| --------------------------------------------- | --------------- |
| <kbd>{"name" => 'Jake', "age" => '22'}</kbd>.keys | ["name", "age"] |

---

## List ope rands

### 差分 (`-`)

2つの配列の差分を返します。つまり、第2の配列にも存在しない第1の配列のアイテムを除いた新しい配列を作成します。

#### 構文

`list` - `updated_list`

- `-` 差分/引き算の演算子
- `list` - 元のリスト
- `updated_list` - 更新されたリスト


#### 使用例

`contacts` と `updated_contacts` という2つの配列があるとします：

`contacts = ["Ariel", "Max", "Kai", "Noam", "Tal"]`

`updated_contacts = ["Ariel", "Max", "Kai", "Lee", "Quinn"]`


|式| 結果 |
|-------|--------|
| `contacts - updated_contacts` | ["Noam", "Tal"] |
| `updated_contacts - contacts` | ["Lee", "Quinn"] |


#### 動作の仕組み

この演算子は、2つの配列の差分を作成します。最初の例では、`contacts - updated_contacts` は `contacts` に存在し、`updated_contacts` に存在しないアイテムの配列を返します。重複するアイテムを単純に削除するだけではないことに注意してください。演算の順序を逆にすると、異なる結果が得られます。たとえば、`updated_contacts` と `contacts` の差分を見つけると、新しい配列には `updated_contacts` に存在し、`contacts` に存在しないアイテムが含まれます。

#### 関連項目

- [where](/formulas/array-list-formulas.md#where): 特定の条件を満たすリストアイテムのサブセットを返します。2つのリストを比較するために not 演算子をチェーンする例については、`where` の使用方法を参照してください。

---

### 和集合 (`&`)

Workatoは直接配列を操作するための和集合 (`&`) 演算子をサポートしていませんが、[concat](#concat) と [uniq](#uniq) の式を組み合わせることで同様の結果を得ることができます。

#### 構文

`list.concat(updated_list).uniq`

- `list` - リスト
- `concat` - 2つのリストを1つのリストに連結します
- `updated_list` - 更新されたリスト
- `uniq` - 重複のない値を含むリストを返します

#### 使用例

| 式 | 結果 |
|---------|--------|
| `contacts.concat(updated_contacts).uniq` | ["Ariel", "Kai", "Lee", "Max", "Noam", "Quinn", "Tal"]

#### 動作の仕組み

`concat` は2つのリストを1つのリストに連結し、`uniq` は重複のないアイテムを含むリストを返します。2つの式を組み合わせることで、2つのリストを結合し、重複するアイテムを削除することができます。