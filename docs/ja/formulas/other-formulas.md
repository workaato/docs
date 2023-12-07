 # その他の数式
このセクションでは、さまざまなデータ型で動作する数式について説明します。

## null

null/nil の値を返します。注意: これを入力フィールドに渡すと、フィールドの値は null に更新されません。フィールドの値を null に更新するには、[clear](#clear) 数式を使用してください。フィールドを数式モードに切り替えることを忘れないでください。

![入力フィールドの null 数式](~@img/formula-docs/null-formula.png)

---

## clear

ターゲットアプリのフィールドの値を null/nil にクリアします。フィールドを数式モードに切り替えることを忘れないでください。

![入力フィールドの clear 数式](~@img/formula-docs/clear-formula.png)
*ターゲットアプリのフィールドをクリアする場合は、null の代わりに clear 数式を使用してください*

---

## skip

このフィールドに対して、宛先アプリに何も渡しません。フィールドに既存の値がある場合、そのままにしておかれます。

### 例
この例では、更新された Salesforce レコードを使用して Marketo のリードを更新しようとしています。Salesforce の <kbd>Company</kbd> が存在するかどうかをチェックします。存在する場合、Salesforce の <kbd>Company</kbd> を Marketo に出力します。それ以外の場合、Marketo のレコードはそのままにしておかれます。

![入力フィールドの skip 数式](~@img/formula-docs/skip-formula.png)
_skip 数式の使用例_

::: tip データピルが空の場合は、このフィールドをスキップします
更新アクションで既存の値をそのままにしたい場合は、skip 数式を使用してください。
:::

---

## uuid

UUID を生成します。

### 例

| 例    | 結果                                |
| -----------| ------------------------------------- |
| uuid       | "c52d735a-aee4-4d44-ba1e-bcfa3734f553"|

---

## encrypt

AES-256-CBC アルゴリズムを使用して、入力文字列を秘密鍵で暗号化します。暗号化された出力文字列は、[RNCryptor V3](https://github.com/RNCryptor/RNCryptor-Spec/blob/master/RNCryptor-Spec-v3.md) 形式でパックされ、Base64 エンコードされます。

_注意: 暗号化キーはレシピにハードコードしないでください。暗号化キーを保存するために、環境プロパティ (名前に `key` または `password` を含む) を使用してください。_

### 例

`encrypt([ssn], [encryption_key])`

---

## decrypt

AES-256-CBC アルゴリズムを使用して、暗号化された入力文字列を秘密鍵で復号化します。暗号化された入力文字列は、[RNCryptor V3](https://github.com/RNCryptor/RNCryptor-Spec/blob/master/RNCryptor-Spec-v3.md) 形式でパックされ、Base64 エンコードされている必要があります。

_注意: 暗号化キーはレシピにハードコードしないでください。暗号化キーを保存するために、環境プロパティ (名前に `key` または `password` を含む) を使用してください。_

### 例

`decrypt([encrypted_ssn], [encryption_key])`

---

## encode_sha256

文字列またはバイナリ配列を SHA256 アルゴリズムを使用してエンコードします。

### 例

`"hello".encode_sha256`

---

## encode_hex

バイナリ文字列を 16 進数表現に変換します。

### 例

| 例                               | 結果                            |
| --------------------------------------| ----------------------------------|
| `"0101010101011010".encode_hex`       | "30313031303130313031303131303130"|


---

## decode_hex

16 進数をバイナリ文字列にデコードします。

### 例

| 例                                               | 結果            |
| ------------------------------------------------------| ------------------|
| `"30313031303130313031303131303130".decode_hex`       | "0101010101011010"|

---

## decode_url

文字列を URL デコードします。この数式は URL デコードに `CGI.unescape` を使用します。

### 例

| 例                                               | 結果            |
| ------------------------------------------------------| ------------------|
| `'https%3A%2F%2Fworkato.com%2Ffoo%3Fbar%3Dat%23anchor'.decode_url`       | "https://workato.com/foo?bar=at#anchor"|
| `'%27Stop%21%27+said+Fred"'.decode_url`       | "'Stop!' said Fred"|

---

## encode_base64

Base64 アルゴリズムを使用してエンコードします。

### 例

| 例    | 結果 |
| -------------------- | ------ |
| `"Hello World!".encode_base64` | "aGVsbG8gd29ybGQh"|

---

## decode_base64

Base64 アルゴリズムを使用してデコードします。

### 例

| 例    | 結果 |
| -------------------- | ------ |
| `"aGVsbG8gd29ybGQh".decode_base64.as_utf8` | "Hello World!"|

---

## encode_url

文字列を URL エンコードします。

### 例

| 例                    | 結果          |
| -------------------------- | --------------- |
| `"Hello World".encode_url` | "Hello%20World" |

---

## encode_urlsafe_base64

URL 安全な変更版 Base64 アルゴリズムを使用してエンコードします。

### 例

| 例                    | 結果          |
| -------------------------- | --------------- |
| `"Hello World".encode_urlsafe_base64` | "SGVsbG8gV29ybGQ=" |

---

## decode_urlsafe_base64

URL 安全な変更版 Base64 アルゴリズムを使用してデコードします。

### 例

| 例                    | 結果          |
| -------------------------- | --------------- |
| `"SGVsbG8gV29ybGQ".decode_urlsafe_base64` | "Hello World" |

---

## as_string

バイトシーケンスを指定したエンコーディングで文字列にデコードします。

### 例

| 例                    | 結果          |
| -------------------------- | --------------- |
| `"SGVsbG8gV29ybGQ=".d ecode_base64.as_string('utf-8')` | "Hello World" |

---

## as_utf8

UTF-8文字列としてバイトシーケンスをデコードします

### 例

| 例                    | 結果          |
| -------------------------- | --------------- |
| `"SGVsbG8gV29ybGQ=".decode_base64.as_utf8` | "Hello World" |

---

## to_hex

バイナリ文字列を16進数表現に変換します

### 例

| 例                    | 結果          |
| -------------------------- | --------------- |
| `"SGVsbG8gV29ybGQ=".decode_base64.to_hex` | "48656c6c6f20576f726c64" |

---


## SHA1

指定された文字列をSHA1暗号化アルゴリズムを使用して暗号化します。[詳細はこちら](https://ruby-doc.org/stdlib-2.4.0/libdoc/digest/rdoc/Digest/SHA1.html)

### 例

| 例                       | 結果                         |
| ----------------------------- | ------------------------------ |
| `"abcdef".sha1.encode_base64` | "H4rBDyPFtbwRZ72oS4M+XAV6d9I=" |

---


## HMAC formulae

さまざまな署名アルゴリズムを使用してHMAC署名を作成します

### 例

| 署名アルゴリズム    | 例 |
| -------------------- | ------ |
| SHA-256  | "username:password:nonce".hmac_sha256("key")|
| SHA-1    | "username:password:nonce".hmac_sha1("key")|
| SHA-512  | "username:password:nonce".hmac_sha512("key")|
| MD5     | "username:password:nonce".hmac_md5("key")|

---

## md5_hexdigest

指定された文字列を使用してMD5メッセージダイジェストを作成します

### 例

| 例    | 結果 |
| -------------------- | ------ |
| `"hello".md5_hexdigest`  | "5d41402abc4b2a76b9719d911017c592"|

---
## jwt_decode

JSON Web Token (JWT)をRS256、RS384、RS512、HS256、HS384、HS512、ES256、ES384、またはES512のいずれかのアルゴリズムを使用してデコードします。

### 例

| 例    | 結果 |
| -------------------- | ------ |
| `workato.jwt_decode( "eyJhbGciO...", "PEM key", \'RS256\')`  | "{"payload" => {"sub"=>"123", "name"=>"John", ...}, "header" => {"typ"=>"JWT", "alg"=>"RS256"}}"|
| `workato.jwt_decode( "eyJhbGciO...", "PEM key", \'RS512\')`  | "{"payload" => {"sub"=>"123", "name"=>"John", ...}, "header" => {"typ"=>"JWT", "alg"=>"RS512"}}"|
| `workato.jwt_decode( "eyJhbGciO...", "my$ecretK3y", \'HS256\')`  | "{"payload" => {"sub"=>"123", "name"=>"John", ...}, "header" => {"typ"=>"JWT", "alg"=>"HS256"}}"|

---

## jwt_encode

JSON Web Token (JWT)をRS256、RS384、RS512、HS256、HS384、HS512、ES256、ES384、またはES512のいずれかのアルゴリズムを使用して作成します。以下の例では、`kid`をヘッダーに追加しています。

### 例

| 例    | 結果 |
| -------------------- | ------ |
| `workato.jwt_encode({ name: "John Doe" }, "PEM key", 'RS256')`  | "eyJhbGciO..."|
| `workato.jwt_encode({ name: "John Doe" }, "PEM key", 'RS512', kid: "24668")`  | "eyJ0eXAiO..."|
| `workato.jwt_encode({ name: "John Doe" }, "my$ecretK3y", 'HS256', kid: "24668")`  | "eyJ0eXAiO..."|
| `workato.jwt_encode({ name: "John Doe" }, "my$ecretK3y", 'HS256')`  | "eyJ0eXAiO..."|
| `workato.jwt_encode({ name: "John Doe" }, "ECDSA Key", 'ES256')`  | "eyJhbGciOiJ..."|
---

## parse_yaml

YAML文字列を解析します。true、false、nil、数値、文字列、配列、ハッシュをサポートしています。

### 例

| 例    | 結果 |
| -------------------- | ------ |
| `workato.parse_yaml("---\nfoo: bar")`  | "{ "foo" => "bar" }"|
| `workato.parse_yaml("---\n- 1\n- 2\n- 3\n")`  | "[1, 2, 3]"|

---

## render_yaml

オブジェクトをYAML文字列にレンダリングします。

### 例

| 例    | 結果 |
| -------------------- | ------ |
| `workato.render_yaml({ "foo" => "bar" })`  | "---\nfoo: bar\n"|
| `workato.render_yaml([1,2,3])`  | "---\n- 1\n- 2\n- 3\n"|

---

## lookup

この式を使用すると、Workatoのルックアップテーブルからキーを使用して値を検索できます。大文字と小文字、データ型に注意してください。

ルックアップ式でデータピルを使用する場合、データが適切な形式に変換されることをお勧めします。たとえば、整数型のデータピルは、整数と文字列の両方を含む列と比較する場合、`.to_s`式で文字列に変換する必要があります。

### 例
以下のような名前が「Department Codes」でIDが6のルックアップテーブルを使用します。

![Sample department codes lookup table](~@img/formula-docs/department-codes-lookup-table.png)
*サンプルの部門コードのルックアップテーブル*

| 例                                                                       | 結果        |
| ----------------------------------------------------------------------------- | ------------- |
| `lookup('Department Lookup table', 'Department code': 'ACC')['Department']`          | "会計"  |
| `lookup('Department Lookup table', 'Department code': 'SLS')['Department']`          | "営業"       |
| `lookup('Department Lookup table', 'Department': 'Marketing')['Department code']`    | "MKT"         |
| `lookup('Department Lookup table', 'Department': 'marketing')['Department code']`    | nil <br>大文字と小文字が区別されるため、値"Marketing"が見つかりません|
| `lookup('Department Lookup table', 'Department': 'Marketing')`    | nil <br>大文字と小文字が区別されるため、値"Marketing"が見つかりません| ['Department Code']`    | nil <br>カラム "Department Code" が見つかりません。大文字と小文字を区別します。|
| `lookup('6', 'Department code': 'ACC')['Department']`                         | "会計"  <br>注意: ルックアップテーブルのIDは引用符 `""` で囲んでください。 |

::: tip ルックアップテーブルのIDの使用方法
ルックアップテーブルの名前とIDは互換性があります。ルックアップテーブルのIDはURLから確認できます。

例:
```
https://app.workato.com/lookup_tables/<lookup_table_id>
```
:::

---

## lookup_table

この式は、静的なルックアップテーブルを作成し、キーと値を定義することができます。大文字と小文字、データ型に注意してください。

### 例
| 例                                                                | 結果    |
| ---------------------------------------------------------------------- | --------- |
| `{"key1" => "value1", "key2" => "value2", "key3" => "value3"}["key2"]` | "value2"  |
| `{"High" => "urgent", "Medium" => "mid", "Low" => "normal"}["Low"]`    | "normal"  |
| `{"High" => "urgent", "Medium" => "mid", "Low" => "normal"}["low"]`    | nil       |
| `{"High" => "urgent", "Medium" => "mid", "Low" => "normal"}["normal"]` | nil       |
| `{1 => "1", 2 => "2", 3 => "3"}[2]`                                    | "2"       |
| `{1 => "1", 2 => "2", 3 => "3"}[2.0]`                                  | nil       |
| `{1 => "1", 2 => "2", 3 => "3"}["2"]`                                  | nil       |

---