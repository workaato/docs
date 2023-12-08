 # 文字列の式

Rubyでは、文字列はテキストと文字のシーケンスを指します。

Workatoでは、さまざまな文字列の式をサポートしています。Workatoの式は、Rubyのメソッドをホワイトリストに登録したものであり、すべてのRubyメソッドがサポートされているわけではありません。追加の式をホワイトリストに追加するためには、いつでも[お問い合わせください](/contact-us.md)。これらの式の構文と機能は一般的に変更されません。ほとんどの式は、null（Rubyでは`nil`と表される）に対して操作を行う場合にエラーが発生し、ジョブが停止します。ただし、`present?`、`presence`、`blank?`は例外です。

詳細な情報については、完全な[Rubyの文字列のドキュメント](https://ruby-doc.org/core-2.3.3/String.html)を参照してください。

以下の例は、Workatoで文字列を操作するために使用できるメソッドを示しています。

---

# 条件分岐

このセクションでは、文字列に条件（if-else）を適用するための式について説明します。条件分岐の使用方法については、[こちら](/formulas/conditions.md)をご覧ください。

---

## `blank?`

この式は、入力された文字列が空の文字列またはnullである場合にtrueを返します。

### 構文

<kbd>Input</kbd>.blank?

- <kbd>Input</kbd> - 入力データピル。文字列、数値、日付、または日時のデータ型である可能性があります。

### 使用例

| 式                           | 結果  |
| ----------------------------- | ------- |
| <kbd>"Any Value"</kbd>.blank? | false   |
| <kbd>123</kbd>.blank?         | false   |
| <kbd>0</kbd>.blank?           | false   |
| <kbd>""</kbd>.blank?          | true    |

### 動作原理

入力がnullまたは空の文字列の場合、式はtrueを返します。それ以外のデータに対しては、falseを返します。

### 関連情報

- [presence](/formulas/string-formulas.md#presence): データが存在する場合はデータを返し、存在しない場合はnilを返します。
- [present?](/formulas/string-formulas.md#present): 有効な入力がある場合はtrueを返します。

---

## `is_not_true?`

ブール値を評価し、評価された値がtrueでない場合にtrueを返します。

### 構文

<kbd>Input</kbd>.is_not_true?

- <kbd>Input</kbd> - 入力ブール値、整数（`1`または`0`）、または受け入れられる文字列値です。

### 使用例

| 式                           | 結果 |
| --------------------------------- | ------ |
| <kbd>true</kbd>.is_not_true?      | false  |
| <kbd>false</kbd>.is_not_true?     | true   |
| <kbd>0</kbd>.is_not_true?         | true   |
| <kbd>nil</kbd>.is_not_true?       | true   |

### 動作原理

入力を受け取り、trueまたはfalseであるかを評価します。

::: tip 文字列の値
`"true"`、`"t"`、`"yes"`、`"y"`、および`"1"`は、ブール値**true**として評価されます。

`"false"`、`"f"`、`"no"`、`"n"`、および`"0"`は、ブール値**false**として評価されます。

ただし、空の文字列（`""`）はブール値として評価されません。この式は、文字列データ型で使用するとエラーが表示されます。
:::

### 関連情報

- [is_true](/formulas/string-formulas.md#is-true): ブール値を評価し、評価された値がtrueである場合にtrueを返します。

---

## `is_true?`

ブール値を評価し、評価された値がtrueである場合にtrueを返します。

### 構文

<kbd>Input</kbd>.is_true?

- <kbd>Input</kbd> - 入力ブール値、整数（`1`または`0`）、または受け入れられる文字列値です。

### 使用例

| 式                       | 結果 |
| ----------------------------- | ------ |
| <kbd>true</kbd>.is_true?      | true   |
| <kbd>false</kbd>.is_true?     | false  |
| <kbd>0</kbd>.is_true?         | false  |
| <kbd>nil</kbd>.is_true?       | false  |

### 動作原理

入力を受け取り、trueであるかどうかを評価します。 以下のように、英語で書かれたマークダウン形式のファイル（例：xxx.md）を日本語に翻訳してください。ただし、以下の部分（①-③）は英語のままにして、翻訳せずに元のままにしてください。また、マークダウン形式のファイルの形式を崩さないようにしてください。
① < > で囲まれた部分（例：<step>、</step>、<dd>など）
② {: :} で囲まれた部分（例：{: #prediction-get :}、{: #azure :}など）
③ ** ** で囲まれた部分（例：**Source**、**Enterprise Applications > Workato > Single Sign On > Attributes & Claims > Add a new claim**など）

```markdown
<step>
::: tip 文字列の値
`"true"`、`"t"`、`"yes"`、`"y"`、および`"1"`は真のブール値として評価されます。

`"false"`、`"f"`、`"no"`、`"n"`、および`"0"`は偽のブール値として評価されます。

ただし、空の文字列（`""`）はブール値として評価されません。この式は文字列データ型で使用するとエラーが表示されます。
:::

### 関連情報

- [is_not_true](/formulas/string-formulas.md#is-not-true): ブール値を評価し、評価された値が true でない場合に true を返します。

---

## `present?`

この式は入力をチェックし、値が存在する場合は true を返します。入力が nil、ブール値の false、空の文字列、または空のリストの場合、この式は false を返します。

### 構文

<kbd>Input</kbd>.present?

- <kbd>Input</kbd> - 入力データピル。文字列、数値、日付、またはリストのデータ型を持つことができます。

### 使用例

| 式                                                    | 結果    |
| ------------------------------------------------------ | ------- |
| <kbd>"Any Value"</kbd>.present?                        | true    |
| <kbd>123</kbd>.present?                                | true    |
| <kbd>0</kbd>.present?                                  | true    |
| <kbd>"2017-04-02T12:30:00.000000-07:00"</kbd>.present? | true    |
| <kbd>nil</kbd>.present?                                | false   |
| <kbd>""</kbd>.present?                                 | false   |
| <kbd>[]</kbd>.present?                                 | false   |

### 動作原理

入力が null、空の文字列、または空のリストの場合、この式は false を返します。それ以外のデータに対しては true を返します。

::: tip nil 値を含むリストの評価
- 空のリストのみが false を返します。

<kbd>[]</kbd>.present? は false を返します。

- nil と空の文字列を含むリストは true を返します。

<kbd>[nil,""]</kbd>.present? は true を返します。
:::

### 関連情報

- [presence](/formulas/string-formulas.md#presence): データが存在する場合はデータを返し、存在しない場合は nil を返します。
- [blank?](/formulas/string-formulas.md#blank): データが存在しないか、文字列が空白のみで構成されている場合は nil を返します。

---

## `presence`

データが存在する場合はデータを返し、存在しない場合は nil を返します。

### 構文

<kbd>Input</kbd>.presence

- <kbd>Input</kbd> - 入力データピル。文字列、数値、日付、または日時のデータ型を持つことができます。

### 使用例

| 式                         | 結果      |
| ------------------------------- | ----------- |
| <kbd>nil</kbd>.presence         | nil         |
| <kbd>""</kbd>.presence          | nil         |
| <kbd>"Any Value"</kbd>.presence | "Any Value" |
| <kbd>45.0</kbd>.presence        | 45.0        |
| <kbd>0</kbd>.presence           | 0           |

### 動作原理

入力が null または空の文字列の場合、この式は nil を返します。それ以外のデータに対しては、元の入力データを返します。

### 関連情報

- [blank?](/formulas/string-formulas.md#blank): データが存在しないか、文字列が空白のみで構成されている場合は nil を返します。
- [present?](/formulas/string-formulas.md#present): 有効な入力がある場合は true を返します。

---

## `include?`

文字列が特定の部分文字列を含んでいるかどうかをチェックします。含んでいる場合は true を返します。

### 構文

<kbd>Input</kbd>.include?(<span style="color:#FF0000">substring</span>)

- <kbd>Input</kbd> - 文字列の入力です。
- <span style="color:#FF0000">substring</span> - チェックする部分文字列です。

### 使用例

| 式                                           | 結果 |
| ---------------------------------------------- | ---- |
| <kbd>"Hello, World!"</kbd>.include?("Hello")   | true |
| <kbd>"Hello, World!"</kbd>.include?("Goodbye") | false |

### 動作原理

入力文字列が指定した部分文字列を含んでいる場合、この式は true を返します。

### 関連情報

- [starts_with?](/formulas/string-formulas.md#starts-with): 文字列が指定した部分文字列で始まるかどうかをチェックします。
- [ends_with?](/formulas/string-formulas.md#ends-with): 文字列が指定した部分文字列で終わるかどうかをチェックします。
```
 ------------------------------- | ------ |
| <kbd>"Partner account"</kbd>.include?("Partner")  | true   |
| <kbd>"Partner account"</kbd>.include?("partner")  | false  |

### 動作原理

この式は、文字列が特定の部分文字列を含んでいるかどうかをチェックします。文字列が部分文字列を含んでいる場合はtrueを返し、含んでいない場合はfalseを返します。部分文字列は大文字と小文字を区別します。

この式は[exclude?](/formulas/string-formulas.md#exclude)とは逆の動作をします。入力された文字列が指定されたキーワードを含んでいる場合にのみtrueを返します。

### 関連情報

- [exclude?](/formulas/string-formulas.md#exclude): 文字列が特定の部分文字列を含んでいるかどうかをチェックします。含んでいる場合はfalseを返します。

---

## `exclude?`

文字列が特定の部分文字列を含んでいるかどうかをチェックします。含んでいる場合はfalseを返します。

### 構文

<kbd>Input</kbd>.exclude?(<span style="color:#FF0000">substring</span>)

- <kbd>Input</kbd> - 文字列の入力です。
- <span style="color:#FF0000">substring</span> - チェックする部分文字列です。

### 使用例

| 式                                               | 結果   |
| ------------------------------------------------- | ------ |
| <kbd>"Partner account"</kbd>.exclude?("Partner")  | false  |
| <kbd>"Partner account"</kbd>.exclude?("partner")  | true   |

### 動作原理

この式は、文字列が特定の部分文字列を含んでいるかどうかをチェックします。含んでいる場合はfalseを返し、含んでいない場合はtrueを返します。この部分文字列は大文字と小文字を区別します。

この関数は[include?](/formulas/string-formulas.md#include)とは逆の動作をします。入力された文字列が指定されたキーワードを含んでいない場合にのみtrueを返します。

### 関連情報

- [include?](/formulas/string-formulas.md#include): 文字列が特定の部分文字列を含んでいるかどうかをチェックします。含んでいる場合はtrueを返します。

---

## `match?`

文字列が特定の正規表現（regex）パターンを含んでいるかどうかをチェックします。含んでいる場合はtrueを返します。

### 構文

<kbd>Input</kbd>.match?(<span style="color:#FF0000">pattern</span>)

- <kbd>Input</kbd> - 文字列の入力です。
- <span style="color:#FF0000">pattern</span> - チェックする正規表現パターンです。

### 使用例

| 式                                               | 結果   |
| ------------------------------------------------- | ------ |
| <kbd>"Jean Marie"</kbd>.match?(/Marie/)           | true   |
| <kbd>"Jean Marie"</kbd>.match?(/ /)               | true   |
| <kbd>"Partner account"</kbd>.match?(/partner/)    | false  |

### 動作原理

この式は、文字列が特定の正規表現パターンを含んでいるかどうかをチェックします。含んでいる場合はtrueを返し、含んでいない場合はfalseを返します。

### 関連情報

- [include?](/formulas/string-formulas.md#include): 文字列が特定の部分文字列を含んでいるかどうかをチェックします。含んでいる場合はtrueを返します。
- [exclude?](/formulas/string-formulas.md#exclude): 文字列が特定の部分文字列を含んでいるかどうかをチェックします。含んでいる場合はfalseを返します。

---

## `ends_with?`

文字列が特定の部分文字列で終わっているかどうかをチェックします。終わっている場合はtrueを返します。

### 構文

<kbd>Input</kbd>.ends_with?(<span style="color:#FF0000">substring</span>)

- <kbd>Input</kbd> - 文字列の入力です。
- <span style="color:#FF0000">substring</span> - チェックする部分文字列です。

### 使用例

| 式                                               | 結果   |
| ------------------------------------------------- | ------ |
| <kbd>"Jean Marie"</kbd>.ends_with?("rie")         | true   |
| <kbd>"Jean Marie"</kbd>.ends_with?("RIE")         | false  |
| <kbd>"Jean Marie"</kbd>.upcase.ends_with?("RIE")  | true   |

### 動作原理

この式は、文字列が特定の部分文字列で終わっているかどうかをチェックします。終わっている場合はtrueを返します。

 特定のサブストリングで文字列が終わるかどうかをチェックします。終わる場合はtrueを返し、それ以外の場合はfalseを返します。

### 関連情報

- [include?](/formulas/string-formulas.md#include): 文字列が特定のサブストリングを含むかどうかをチェックします。含む場合はtrueを返します。
- [exclude?](/formulas/string-formulas.md#exclude): 文字列が特定のサブストリングを含むかどうかをチェックします。含まない場合はfalseを返します。
- [match?](/formulas/string-formulas.md#match): 文字列が特定のパターンを含むかどうかをチェックします。含む場合はtrueを返します。
- [starts_with?](/formulas/string-formulas.md#starts-with): 文字列が特定のサブストリングで始まるかどうかをチェックします。始まる場合はtrueを返します。

---

## `starts_with?`

文字列が特定のサブストリングで始まるかどうかをチェックします。始まる場合はtrueを返します。

### 構文

<kbd>Input</kbd>.starts_with?(<span style="color:#FF0000">substring</span>)

- <kbd>Input</kbd> - 文字列の入力です。
- <span style="color:#FF0000">substring</span> - チェックするサブストリングです。

### 使用例

| 式                                              | 結果 |
| ---------------------------------------------------- | ------ |
| <kbd>"Jean Marie"</kbd>.starts_with?("Jean")         | true   |
| <kbd>"Jean Marie"</kbd>.starts_with?("JEAN")         | false  |
| <kbd>"Jean Marie"</kbd>.upcase.starts_with?("JEAN")  | true   |

### 動作

この式は、文字列が特定のサブストリングで始まるかどうかをチェックします。始まる場合はtrueを返し、それ以外の場合はfalseを返します。

### 関連情報

- [include?](/formulas/string-formulas.md#include): 文字列が特定のサブストリングを含むかどうかをチェックします。含む場合はtrueを返します。
- [exclude?](/formulas/string-formulas.md#exclude): 文字列が特定のサブストリングを含むかどうかをチェックします。含まない場合はfalseを返します。
- [match?](/formulas/string-formulas.md#match): 文字列が特定のパターンを含むかどうかをチェックします。含む場合はtrueを返します。
- [ends_with?](/formulas/string-formulas.md#ends-with): 文字列が特定のサブストリングで終わるかどうかをチェックします。終わる場合はtrueを返します。

---

# テキストの操作

このセクションには、文字列内のテキストを操作するための式が含まれています。

---

## `parameterize`

文字列内の特殊文字を標準の文字に置き換えます。アプリが非標準の文字を受け付けない場合に使用します。

### 構文

<kbd>Input</kbd>.parameterize

- <kbd>Input</kbd> - 入力文字列です。

### 使用例

| 式                       | 結果  |
| ----------------------------- | ------- |
| <kbd>"öüâ"</kbd>.parameterize | "oua"   |

### 動作

この式は、文字列内のすべての特殊文字を検索し、標準の文字に置き換えます。

------

## `lstrip`

この式は、入力文字列の先頭の空白を削除します。

### 構文

<kbd>String</kbd>.lstrip

- <kbd>String</kbd> - 入力文字列です。

### 使用例

| 式                             | 結果      |
| ----------------------------------- | ----------- |
| <kbd>"     Test     ".</kbd>.lstrip | "Test     " |

### 動作

この式は、文字列の先頭から空白を削除します。文字列の先頭に空白がない場合は、入力文字列がそのまま返されます。

::: tip 選択的に空白を削除する
- 文字列の末尾から空白を削除するには、[rstrip](/formulas/string-formulas.md#rstrip)を使用します。
- 文字列の中央から空白を削除するには、[gsub](/formulas/string-formulas.md#gsub)を使用します。<br>
<kbd>"a b c d e"</kbd>.gsub(" " , "") は `"abcde"` を返します。
:::

### 関連情報

- [strip](/formulas/string-formulas.md#strip): 入力文字列の先頭と末尾の空白を削除します。 ## `rstrip`

この式は、入力文字列の末尾の空白を削除します。

### 構文

<kbd>String</kbd>.rstrip

- <kbd>String</kbd> - 入力文字列です。

### 使用例

| 式                                   | 結果        |
| ----------------------------------- | ----------- |
| <kbd>"     テスト     ".</kbd>.rstrip | "     テスト" |

### 動作

この式は、文字列の末尾から空白を削除します。文字列の末尾に空白がない場合、入力文字列はそのまま返されます。

::: tip 選択的に空白を削除する
- 文字列の先頭からの空白のみを削除するには、[lstrip](/formulas/string-formulas.md#lstrip)を使用します。
- 文字列の中央から空白を削除するには、[gsub](/formulas/string-formulas.md#gsub)を使用します。<br>
<kbd>"a b c d e"</kbd>.gsub(" " , "") は `"abcde"` を返します。
:::

### 関連情報

- [strip](/formulas/string-formulas.md#rstrip): 入力文字列の先頭と末尾の空白を削除します。
- [lstrip](/formulas/string-formulas.md#lstrip): 入力文字列の先頭の空白を削除します。
- [gsub](/formulas/string-formulas.md#gsub): テキスト文字列の一部を置換します。置換された文字で新しい文字列を返します。

---

## `scrub`

もし文字列が無効なバイトシーケンスである場合、この式は無効なバイトを置換文字で置き換えます。もし文字列が無効でない場合、この式は元の文字列を返します。

### 構文

<kbd>String</kbd>.scrub(<span style="color:#FF0000">置換文字列</span>)

- <kbd>String</kbd> - 入力文字列です。

### 使用例

| 式                                    | 結果         |
| ------------------------------------------ | ------------ |
| <kbd>"abc\u3042\x81"</kbd>.scrub("*")      | "abc\u3042*" |

---

## `strip`

この式は、入力文字列の先頭と末尾の空白を削除します。

### 構文

<kbd>String</kbd>.strip

- <kbd>String</kbd> - 入力文字列です。

### 使用例

| 式                                                      | 結果                                 |
| ------------------------------------------------------------ | -------------------------------------- |
| <kbd>"自動化の未来へようこそ！     "</kbd>.strip | "自動化の未来へようこそ！" |
| <kbd>"   これは例です   "</kbd>.strip                  | "これは例です"                   |

### 動作

この式は、文字列の両側から空白を削除します。文字列の両側に空白がない場合、入力文字列はそのまま返されます。

::: tip 選択的に空白を削除する
- 一方の側の空白のみを削除するには、[lstrip](/formulas/string-formulas.md#lstrip)または[rstrip](/formulas/string-formulas.md#rstrip)を使用します。
- 文字列の中央から空白を削除するには、[gsub](/formulas/string-formulas.md#gsub)を使用します。<br>
<kbd>"a b c d e"</kbd>.gsub(" " , "") は `"abcde"` を返します。
:::

### 関連情報

- [lstrip](/formulas/string-formulas.md#lstrip): 入力文字列の先頭の空白を削除します。
- [rstrip](/formulas/string-formulas.md#rstrip): 入力文字列の末尾の空白を削除します。
- [gsub](/formulas/string-formulas.md#gsub): テキスト文字列の一部を置換します。置換された文字で新しい文字列を返します。 ## `gsub`

テキスト文字列の一部を置換します。置換された文字で新しい文字列を返します。

### 構文

<kbd>String</kbd>.gsub(<span style="color:#FF0000">find</span>,<span style="color:#FF0000">replace</span>)

- <kbd>String</kbd> - 入力文字列。データピルまたは静的な文字列値を使用できます。
- <span style="color:#FF0000">find</span> - 置換する文字列を指定します。

### サンプルの使用法

| 入力                                   | 結果           |
| -------------------------------------- | -------------- |
| <kbd>"Hello, World!".</kbd>.gsub("o", "a") | "Hella, Warld!" |
| <kbd>"Hello, World!".</kbd>.gsub("l", "L") | "HeLLo, WorLd!" |

### 詳細

この式は、入力文字列内の指定された文字列を検索し、置換します。複数の一致がある場合、すべての一致が置換されます。

### 関連情報

- [sub](/formulas/string-formulas.md#sub): 最初の一致した文字列を置換します。
- [gsub!](/formulas/string-formulas.md#gsub!): 入力文字列自体を置換します。 以下のように、英語で書かれたマークダウン形式のファイル（例：xxx.md）を日本語に翻訳してください。ただし、以下の部分（①-③）は英語のままにして、翻訳せずに元のマークダウン形式のままにしてください。また、翻訳された内容が口語的でなく、翻訳言語で自然な音になるようにしてください。
① < > で囲まれた部分（例：<step>、</step>、<dd>など）
② {: :} で囲まれた部分（例：{: #prediction-get :}、{: #azure :}など）
③ ** ** で囲まれた部分（例：**Source**、**Enterprise Applications > Workato > Single Sign On > Attributes & Claims > Add a new claim**など）

検索するための文字列または正規表現（regex）です。正規表現の場合は `/pattern/` の構文を使用します。
- <span style="color:#FF0000">replace</span> - 置換する文字列です。文字列または [ハッシュ](/formulas/array-list-formulas.md#hashes) を使用して置換を定義できます。

### 使用例

| 式                                                                   | 結果                               |
| ------------------------------------------------------------------- | ---------------------------------- |
| <kbd>"I have a blue house and a blue car"</kbd>.gsub("blue", "red") | "I have a red house and a red car" |
| <kbd>"Jean Marie"</kbd>.gsub("J", "M")                              | "Mean Marie"                       |
| <kbd>"Jean Marie"</kbd>.gsub(/[Jr]/, 'M')                           | "Mean MaMie"                       |
| <kbd>"Jean Marie"</kbd>.downcase.gsub("j", "M")                     | "Mean marie"                       |

### 高度な使用例

`gsub` メソッドの詳細な使用方法については、[Ruby ドキュメント](https://ruby-doc.org/core-2.7.2/String.html#method-i-gsub.)を参照してください。

| 式                                               | 結果    |
| ------------------------------------------------- | ------- |
| <kbd>"Awesome"</kbd>.gsub(/[Ae]/, 'A'=>'E', 'e'=>'a') | "Ewasoma" |
| <kbd>"Anna's Cafe"</kbd>.gsub("'", "\\\\'")           | "Annas Cafes Cafe"<br>これは改行後のテキストで引用符を置き換えます。 |
| <kbd>"Anna's Cafe"</kbd>.gsub("'", {"'"=>"\\\\'"})    | "Anna\\\\'s Cafe"<br>これは引用符を置換文字列に置き換えます。|

### 動作原理

この式は、検索して置換する操作に似ています。2つの入力パラメータを使用します。
- **最初の入力**: 置換する文字列です。入力は大文字と小文字を区別するため、正確な一致のすべての出現を見つけるために大文字と小文字を正確に入力してください。
- **2番目の入力**: 最初の入力のすべての出現を置き換える新しい文字列です。

### 関連項目

- [sub](/formulas/string-formulas.md#sub): 検索語の最初の出現を置換します。

---

## `sub`

文字列内の最初の出現を、2番目の入力値で置き換えます。この式は大文字と小文字を区別します。大文字と小文字の区別について心配な場合は、比較の前に大文字または小文字を入力してください。

### 構文

<kbd>String</kbd>.sub(<span style="color:#FF0000">find</span>,<span style="color:#FF0000">replace</span>)

- <kbd>String</kbd> - 入力文字列。データピルまたは静的な文字列値を使用できます。
- <span style="color:#FF0000">find</span> - 検索する文字列または正規表現（regex）。正規表現の場合は `/pattern/` の構文を使用します。
- <span style="color:#FF0000">replace</span> - 置換する文字列。文字列または [ハッシュ](/formulas/array-list-formulas.md#hashes) を使用して置換を定義できます。

### 使用例
| 式                                      | 結果       |
| -------------------------------------------- | ------------ |
| <kbd>"Mean Marie"</kbd>.sub(/M/, "J")        | "Jean Marie" |
| <kbd>"Hello"</kbd>.sub(/[aeiou]/, "*")       | "H*llo"      |

---

## `length`

空白を含む入力文字列の文字数を返します。

### 構文

<kbd>String</kbd>.length

- <kbd>String</kbd> - 入力文字列。

### 使用例

| 式                          | 結果 |
| -------------------------------- | ------ |
| <kbd>"Jean Marie"</kbd>.length   | 10     |
| <kbd>" jean marie "</kbd>.length | 12   | ---

## `slice`

文字列の一部を返します。

### 構文

<kbd>String</kbd>.slice(<span style="color:#FF0000">start</span>,<span style="color:#FF0000">end</span>)

- <kbd>String</kbd> - 入力文字列。
- <span style="color:#FF0000">start</span> - 部分的なセグメントの開始位置のインデックスです。文字列はゼロから始まります。
- <span style="color:#FF0000">end</span> - (オプション) 返す文字数です。指定しない場合、式は1文字のみを返します。

### 使用例

| 式                                   | 結果    |
| ----------------------------------- | ------- |
| <kbd>"Jean Marie"</kbd>.slice(0,3)  | "Jea"   |
| <kbd>"Jean Marie"</kbd>.slice(5)    | "M"     |
| <kbd>"Jean Marie"</kbd>.slice(3,3)  | "n M"   |
| <kbd>"Jean Marie"</kbd>.slice(-5,5) | "Marie" |

### 動作の仕組み

この式は文字列の一部を返します。2つのパラメータを受け取ります。最初のパラメータは、どの部分の文字列を返すかを決定するインデックスです。文字列の最初の文字はインデックス0に対応します。負の数は最後の文字から始まりますので、インデックス-1は文字列の最後の文字です。2番目のパラメータは、返す文字数を決定します。最初のパラメータのみを渡す場合、1文字が返されます。

---

## `scan`

文字列を正規表現パターンでスキャンし、配列を取得して返します。

### 構文

<kbd>String</kbd>.scan(<span style="color:#FF0000">pattern</span>)

- <kbd>String</kbd> - 入力文字列。
- <span style="color:#FF0000">regex pattern</span> - 検索する正規表現パターンです。

### 使用例

| 式                                             | 結果               |
| ----------------------------------------------- | ------------------ |
| <kbd>"Thu, 01/23/2014"</kbd>.scan(/\d+/)        | ["01","23","2014"] |
| <kbd>"Thu, 01/23/2014"</kbd>.scan(/\d+/).join("-")  | "01-23-2014"       |

---

## `encode`

文字列をエンコードして返します。

### 構文

<kbd>String</kbd>.encode(<span style="color:#FF0000">encoding</span>)

- <kbd>String</kbd> - 入力文字列。
- <span style="color:#FF0000">encoding</span> - エンコーディングの名前 (例: Windows-1252)。詳細は[こちら](https://en.wikibooks.org/wiki/Ruby_Programming/Encoding)を参照してください。

### 使用例

| 式                   |
| ------------------------- |
| "Jean Marie".encode("Windows-1252") |

---

## `transliterate`

非ASCII文字をASCIIの近似文字に置き換えます。近似文字が存在しない場合は、デフォルトで'?'という置換文字を使用します。

### 構文

<kbd>String</kbd>.transliterate

- <kbd>String</kbd> - 入力文字列。

### 使用例

| 式                   | 結果    |
| ------------------------- | ------- |
| <kbd>"Chloé"</kbd>.transliterate     | "Chloe"   |

- [parameterize](/formulas/string-formulas.md#parameterize): 文字列内の特殊文字を置換します。

---

# テキストの大文字・小文字変換

このセクションでは、単語の一部の大文字・小文字を変更するための式について説明します。

------

## `capitalize`

入力文字列を文の先頭が大文字で、それ以外が小文字の形式に変換します。

### 構文

<kbd>String</kbd>.capitalize

- <kbd>String</kbd> - 入力文字列。

### 使用例

| 式                                | 結果                    |
| -------------------------------------- | ------------------------- |
| <kbd>"ticket opened. Gold SLA"</kbd>.cap ## `titleize`

入力された文字列をタイトルケースに変換します。各単語の最初の文字が大文字で、他の文字はすべて小文字になります。

### 構文

<kbd>String</kbd>.titleize

- <kbd>String</kbd> - 入力文字列。

### 使用例

| 式                              | 結果                    |
| ------------------------------------ | ------------------------- |
| <kbd>"ticket opened. Gold SLA"</kbd>.titleize | "Ticket Opened. Gold Sla" |
| <kbd>"jean MARIE"</kbd>.titleize              | "Jean Marie"              |

---

## `upcase`

テキストを大文字に変換します。

### 構文

<kbd>String</kbd>.upcase

- <kbd>String</kbd> - 入力文字列。

### 使用例

| 式                                        | 結果                       |
| ---------------------------------------------- | ---------------------------- |
| <kbd>"Automation at its FINEST!"</kbd>.upcase | "AUTOMATION AT ITS FINEST!" |
| <kbd>"Convert to UPCASE"</kbd>.upcase          | "CONVERT TO UPCASE"          |

### 動作方法

この式は、小文字の文字を検索し、大文字の文字で置き換えます。

::: tip UPCASE を使用して文字列の検索を改善する
([gsub](/formulas/string-formulas.md#gsub) や [sub](/formulas/string-formulas.md#sub) などの) 検索式は、大文字と小文字を区別します。検索する前に、すべての文字が同じケースになるように `upcase` 式を使用してください。
:::

### 関連情報

- [downcase](/formulas/string-formulas.md#downcase): テキストを小文字に変換します。
- [capitalize](/formulas/string-formulas.md#capitalize): テキストをセンテンスケースに変換します。
- [titleize](/formulas/string-formulas.md#titleize): テキストをタイトルケースに変換します。

---

## `downcase`

テキストを小文字に変換します。
::: details ビデオチュートリアル: Downcase 式の使用例
<Video src="https://www.youtube.com/embed/HXBe9PVwH0M"/>
:::

### 構文

<kbd>String</kbd>.downcase

- <kbd>String</kbd> - 入力文字列。

### 使用例

| 式                                          | 結果                      |
| ------------------------------------------------ | --------------------------- |
| <kbd>"Automation at its FINEST!"</kbd>.downcase | "automation at its finest!" |
| <kbd>"Convert to DOWNCASE"</kbd>.downcase        | "convert to downcase"       |

### 動作方法

この式は、大文字の文字を検索し、小文字の文字で置き換えます。

::: tip DOWNCASE を使用して文字列の検索を改善する
([gsub](/formulas/string-formulas.md#gsub) や [sub](/formulas/string-formulas.md#sub) などの) 検索式は、大文字と小文字を区別します。検索する前に、すべての文字が同じケースになるように `downcase` 式を使用してください。
:::

### 関連情報

- [upcase](/formulas/string-formulas.md#upcase): テキストを大文字に変換します。
- [capitalize](/formulas/string-formulas.md#capitalize): テキストをセンテンスケースに変換します。
- [titleize](/formulas/string-formulas.md#titleize): テキストをタイトルケースに変換します。

---

## `quote`

文字列を引用符で囲み、' (シングルクォート) の文字をエスケープします。

### 構文

<kbd>String</kbd>.quote

- <kbd>String</kbd> - 入力文字列。

### 使用例

| 式                              | 結果                    |
| ------------------------------------ | ------------------------- |
| <kbd>"Paula's Baked Goods"</kbd>.quote        | "Paula\'s Baked Goods"    |

---

# 配列への変換と戻し

このセクションでは、 ## `split`

この式は、指定された文字を基準に文字列を分割し、文字列の配列を返します。
::: details ステップバイステップのビデオチュートリアルをご覧ください
<Video src="https://www.youtube.com/embed/trpODHgNzCY"/>
:::
### 構文

<kbd>String</kbd>.split(<span style="color:#FF0000">char</span>)

- <kbd>String</kbd> - 入力文字列の値です。データピルまたは静的な値を使用できます。
- <span style="color:#FF0000">char</span> - (オプション) テキストを分割する文字です。大文字と小文字が区別されます。文字が定義されていない場合、デフォルトでは文字列は空白で分割されます。

### 使用例

| 式                                     | 結果                    |
| ------------------------------------- | ----------------------- |
| <kbd>"Ms-Jean-Marie"</kbd>.split("-") | ["Ms", "Jean", "Marie"] |
| <kbd>"Ms Jean Marie"</kbd>.split      | ["Ms", "Jean", "Marie"] |
| <kbd>"Split string"</kbd>.split()     | ["Split", "string"]     |
| <kbd>"Split string"</kbd>.split("t")  | ["Split", " s", "ring"]  |
| <kbd>"01/23/2014"</kbd>.split("/")    | ["01", "23", "2014"]    |
| <kbd>"01/23/2014"</kbd>.split("/").join("-") | "01-23-2014"     |

### 動作原理

この式は、入力文字列内で指定された文字を検索します。見つかるたびに、入力は新しい文字列に分割されます。

::: tip 分割文字
分割引数として複数の文字列を一緒に使用することができます（例: `"and"`）。

<kbd>"You and Me"</kbd>.split(`"and"`) は `["You","Me"]` を返します。
:::

### 関連情報

- [strip](/formulas/string-formulas.md#strip): 入力文字列の周りの空白を削除します。
- [slice](/formulas/string-formulas.md#slice): 文字列の一部を返します。
- [match](/formulas/string-formulas.md#match): 入力文字列に特定のパターンが含まれているかを確認します。
- [join](/formulas/array-list-formulas.md#join): リストの項目を文字列に結合します。

---

## `bytes`

指定された文字列のバイト配列を返します。

### 構文

<kbd>String</kbd>.bytes

- <kbd>String</kbd> - 入力文字列です。

### 使用例

| 式                    | 結果            |
| -------------------------- | ----------------- |
| <kbd>"Hello"</kbd>.bytes   | ["72", "101", "108", "108", "111"] |

---

## `bytesize`

指定された文字列のバイト数を返します。

### 構文

<kbd>Input</kbd>.bytesize

- <kbd>Input</kbd> - 任意の入力文字列です。

### 使用例

| 式                                  | 結果               |
| ---------------------------------------- | -------------------- |
| <kbd>"Hello"</kbd>.bytesize              | 5           |

---

## `byteslice`

指定されたバイト数の代わりに、指定されたバイトの部分文字列を返します。日本語や中国語などの非ASCII文字は、複数のバイトを使用する場合があります。

### 構文

<kbd>Input</kbd>.byteslice(0,4)

- <kbd>Input</kbd> - 任意の入力文字列です。

### 使用例

| 式                                  | 結果               |
| ---------------------------------------- | -------------------- |
| <kbd>"hello"</kbd>.byteslice(1)           | e                    |
| <kbd>"hello"</kbd>.byteslice(-1)          | o                    |
| <kbd>"hello"</kbd>.byteslice(1,2)         | el                   |
| <kbd>"abc漢字"</kbd>.byteslice(0,4)        | abc漢                |

---

# 変換式 {: #conversions :}

## 他のデータ型を文字列に変換する

---

## `to_s`

数値や日付などの非文字列データ型を文字列（テキスト）データ型に変換します。
::: details ビデオを見る チュートリアル: to_s フォーミュラの使用例
<Video src="https://www.youtube.com/embed/nOkGS8fYv5g"/>
:::

### 構文

<kbd>Input</kbd>.to_s

- <kbd>Input</kbd> - 任意の入力データ。数値、配列、オブジェクト、または日時のデータ型を使用できます。

### 使用例

| フォーミュラ                                                | 結果                               |
| ---------------------------------------------------------- | ---------------------------------- |
| <kbd>-45.67</kbd>.to_s                                     | "-45.67"                           |
| <kbd>"123"</kbd>.to_s                                      | "123"                              |
| <kbd>[1, 2, 3]</kbd>.to_s                                  | "[1, 2, 3]"                        |
| <kbd>{key: "Workato"}</kbd>.to_s                           | "{:key=>"Workato"}"                |
| <kbd>"2020-06-05T17:13:27.000000-07:00"</kbd>.to_s         | "2020-06-05T17:13:27.000000-07:00" |
| <kbd>"2020-06-05T17:13:27.000000-07:00"</kbd>.to_s(:short) | "05 Jun 17:13"                     |
| <kbd>"2020-06-05T17:13:27.000000-07:00"</kbd>.to_s(:long)  | "June 05, 2020 17:13"              |

### 動作原理

このフォーミュラは、入力データの文字列表現を返します。

::: tip 出力は文字列データ型です
リストの文字列表現は、[**繰り返しステップ**](/recipes/steps.md#repeat-step)で使用できません。
:::

### 関連項目

- [to_f](/formulas/string-formulas.md#to-f): データを浮動小数点数（数値）データ型に変換します。
- [to_i](/formulas/string-formulas.md#to-i): データを整数（整数）データ型に変換します。

---

## `ordinalize`

数値を順序を示す文字列に変換します。例えば、1st、2nd、3rd、4th などの順序を示す文字列です。

### 構文

<kbd>Input</kbd>.ordinalize

- <kbd>Input</kbd> - 任意の数値の入力です。

### 使用例

| フォーミュラ                    | 結果               |
| -------------------------- | -------------------- |
| <kbd>1</kbd>.ordinalize    | "1st"                |
| <kbd>2</kbd>.ordinalize    | "2nd"                |
| <kbd>3</kbd>.ordinalize    | "3rd"                |
| <kbd>1003</kbd>.ordinalize | "1003rd"             |
| <kbd>-3</kbd>.ordinalize   | "-3rd"               |

---

## 文字列から他のデータ型への変換

---

## `to_f`

データを浮動小数点数（数値）データ型に変換します。

### 構文

<kbd>Input</kbd>.to_f

- <kbd>Input</kbd> - 数値の入力データです。文字列データ型または整数データ型を使用できます。

### 使用例

| フォーミュラ                   | 結果 |
| ------------------------- | ------ |
| <kbd>45</kbd>.to_f        | 45.0   |
| <kbd>-45</kbd>.to_f       | -45.0  |
| <kbd>"45.67"</kbd>.to_f   | 45.67  |
| <kbd>"Workato"</kbd>.to_f | 0      |

### 動作原理

このフォーミュラは、入力に数値が含まれているかどうかをチェックします。数値が見つからない場合は、0を返します。数値に小数点がない場合は、数値に `.0` が追加されます。

### 関連項目

- [to_i](/formulas/string-formulas.md#to-i): データを整数（整数）データ型に変換します。

---

## `to_i`

データを整数（整数）データ型に変換します。

### 構文

<kbd>Input</kbd>.to_i

- <kbd>Input</kbd> - 数値の入力データです。文字列データ型または浮動小数点数データ型を使用できます。

### 使用例

| フォーミュラ                   | 結果 |
| ------------------------- | ------ |
| <kbd>45.43</kbd>.to_i     | 45     |
| <kbd>-45.43</kbd>.to_i    | -45    |
| <kbd>"123"</kbd>.to_i     | 123    |
| <kbd>"Workato"</kbd>.to_i | 0      |

### 動作原理

このフォーミュラは、入力に数値が含まれているかどうかをチェックします。 任意の文字列に整数が含まれているかどうかを確認するために、次の数式を使用できます。もし数字が見つからない場合は、`0`を返します。小数点が含まれている場合は、小数点以下の部分は切り捨てられます。

::: tip 整数の確認
この数式を使用して、文字列に整数が含まれているかどうかを確認できます。もし入力に数字が含まれていない場合、数式は`0`を返します。
:::

### 関連情報

- [to_f](/formulas/string-formulas.md#to-f): データを浮動小数点数（数値）のデータ型に変換します。

---

## `to_country_alpha2`

アルファ-3の国コードまたは国名をアルファ-2の国コード（最初の2文字）に変換します。

### 構文

<kbd>Input</kbd>.to_country_alpha2

- <kbd>Input</kbd> - 任意の入力文字列。

### 使用例

| 数式                            | 結果 |
| ---------------------------------- | ------ |
| <kbd>"GBR"</kbd>.to_country_alpha2            | "GB"     |
| <kbd>"United Kingdom"</kbd>.to_country_alpha2 | "GB"     |

---

## `to_country_alpha3`

アルファ-2の国コードまたは国名をアルファ-3の国コード（最初の3文字）に変換します。

### 構文

<kbd>Input</kbd>.to_country_alpha3

- <kbd>Input</kbd> - 任意の入力文字列。

### 使用例

| 数式                            | 結果 |
| ---------------------------------- | ------ |
| <kbd>"GB"</kbd>.to_country_alpha3            | "GBR"     |
| <kbd>"United Kingdom"</kbd>.to_country_alpha3 | "GBR"     |

---

## to_country_name

アルファ-2、アルファ-3の国コードまたは国名をISO3166の国名に変換します。

### 構文

<kbd>Input</kbd>.to_country_name

- <kbd>Input</kbd> - 任意の入力文字列。

### 使用例

| 数式               | 結果         |
| --------------------- | -------------- |
| <kbd>"GBR"</kbd>.to_country_name | "United Kingdom" |
| <kbd>"GB"</kbd>.to_country_name  | "United Kingdom" |

---

## `to_currency`

整数または数値を通貨スタイルにフォーマットし、文字列の先頭にデフォルトの通貨記号を追加します。

### 構文

<kbd>Input</kbd>.to_currency

- <kbd>Input</kbd> - 任意の入力文字列。

### 使用例

| 数式                         | 説明                      | 結果    |
| ------------------------------- | -------------------------------- | --------- |
| <kbd>"345.60"</kbd>.to_currency | デフォルトの通貨記号 "$" を追加します | "$345.60" |

### 応用的な使用例

to_currency数式の応用的な使用方法について詳しく学びます。これらのカンマ区切りの組み合わせを使用して、所望の通貨形式を実現することができます。例えば:

```ruby
"12345.678".to_currency(delimiter: ".", format: "%n %u", precision: 2, separator: ",", unit: "€")
```

| 数式           |  説明  |  結果  |
| ------------------| ------------- | -------- |
| <kbd>"345.60"</kbd>.to_currency(unit: "€") | デフォルトの通貨単位を変更します | "€345.60" |
| <kbd>"345.60"</kbd>.to_currency(format: "%n %u") | 数字の位置を単位に対して変更します（数字は`%n`で表され、通貨単位は`%u`で表されます）。間に0または1のスペースを受け入れます。デフォルトは`"%u%n"`です。 | "345.60 $" |
| <kbd>"-345.60"</kbd>.to_currency(negative_format: "(%u%n)") | 数字が負の場合のフォーマットを指定します（数字は`%n`で表され、通貨単位は`%u`で表されます）。 | "($345.60)" |
| <kbd>"345.678"</kbd>.to_currency               | 精度はデフォルトで小数点以下2桁です | "$345.68"  |
| <kbd>"345.678"</kbd>.to_currency(precision: 3) | 小数点以下の桁数を指定して精度を変更します | "$345.678" |
| <kbd>"345.678"</kbd>.to_currency(separator: ",") | **小数点の区切り記号**を"."に指定します。 ","または" "。デフォルトは"."です。 | "$345,68" |
| <kbd>"12345.678"</kbd>.to_currency(delimiter: ".") | **千の区切り文字**を","、"."または" "で指定します。デフォルトは","です。| "$12.345.68"|

---

## `to_currency_code`

アルファ-2、アルファ-3の国コード、または国名をISO4217通貨コードに変換します。

### 構文

<kbd>Input</kbd>.to_currency_code

- <kbd>Input</kbd> - 任意の入力文字列。

### 使用例

| 式                | 結果 |
| ---------------------- | ------ |
| <kbd>"GBR"</kbd>.to_currency_code | "GBP"    |
| <kbd>"US"</kbd>.to_currency_code  | "USD"    |

---

## `to_currency_name`

アルファ-3の通貨コード、またはアルファ-2/3の国コード、または国名をISO4217通貨名に変換します。

### 構文

<kbd>Input</kbd>.to_currency_name

- <kbd>Input</kbd> - 任意の入力文字列。

### 使用例

| 式                | 結果  |
| ---------------------- | ------- |
| <kbd>"GBR"</kbd>.to_currency_code | "ポンド"   |
| <kbd>"USD"</kbd>.to_currency_code | "ドル" |

---

## `to_currency_symbol`

アルファ-3の通貨コード、またはアルファ-2/3の国コード、または国名をISO4217通貨記号に変換します。

### 構文

<kbd>Input</kbd>.to_currency_symbol

- <kbd>Input</kbd> - 任意の入力文字列。

### 使用例

| 式                | 結果 |
| ---------------------- | ------ |
| <kbd>"GBR"</kbd>.to_currency_symbol | "£"      |
| <kbd>"USD"</kbd>.to_currency_symbol | "$"      |

---

## `to_phone`

文字列または数値を指定した形式の電話番号に変換します（ユーザー定義）。

### 構文

<kbd>Input</kbd>.to_phone

- <kbd>Input</kbd> - 任意の入力文字列または数値。

### 使用例

| 式                                  | 結果               |
| ---------------------------------------- | -------------------- |
| <kbd>"5551234"</kbd>.to_phone                     | 555-1234             |
| <kbd>1235551234</kbd>.to_phone                    | 123-555-1234         |
| <kbd>1235551234</kbd>.to_phone(area_code: true)   | (123) 555-1234       |
| <kbd>1235551234</kbd>.to_phone(delimiter: " ")    | 123 555 1234         |
| <kbd>1235551234</kbd>.to_phone(area_code: true, extension: 555) | (123) 555-1234 x 555 |
| <kbd>1235551234</kbd>.to_phone(country_code: 1)   | +1-123-555-1234      |
| <kbd>"123a456</kbd>.to_phone                     | 123a456              |

---

## `to_state_code`

州名をコードに変換します。

### 構文

<kbd>Input</kbd>.to_state_code

- <kbd>Input</kbd> - 任意の入力文字列。

### 使用例

| 式                                  | 結果               |
| ---------------------------------------- | -------------------- |
| <kbd>"California"</kbd>.to_state_code    | CA                   |

---

## `to_state_name`

州コードを名前に変換します。

### 構文

<kbd>Input</kbd>.to_state_name

- <kbd>Input</kbd> - 任意の入力文字列。

### 使用例

| 式                                  | 結果               |
| ---------------------------------------- | -------------------- |
| <kbd>"CA"</kbd>.to_state_name            | カリフォルニア           |

---