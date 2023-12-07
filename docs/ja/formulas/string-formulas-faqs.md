 # String formulas FAQs

よくある文字列の数式に関する質問に対する回答をご覧ください。

::: details Workatoの文字列数式とは何ですか？
文字列はテキストと文字のシーケンスです。Workatoの文字列数式は、文字列を操作したり処理したりするためのRubyメソッドを許可するものです。
:::

::: details 文字列数式における条件分岐の目的は何ですか？
条件分岐を使用することで、文字列に対してif-elseのロジックを適用することができます。これにより、条件に基づいてさまざまなアクションを実行することができます。詳細な手順については、[条件分岐](/formulas/conditions.md#conditionals)を参照してください。
:::

::: details 文字列数式での含めると除外する方法はありますか？
[`include?`数式](/formulas/string-formulas.md#include)は、特定の部分文字列が文字列内に存在するかどうかをチェックし、見つかった場合は`true`を返します。

[`exclude?`数式](/formulas/string-formulas.md#exclude)は、特定の部分文字列が文字列内に存在しないかどうかをチェックし、見つからなかった場合は`true`を返します。
:::

::: details 文字列数式でテキスト操作を使用できますか？
はい。以下の数式を使用して、文字列内のテキストを操作することができます。

- [`parameterize`](/formulas/string-formulas.md#parameterize)
    - 特殊文字を置き換えます。

- [`strip`](formulas/string-formulas.md#strip)
    - 先頭と末尾の空白を削除します。

- [`upcase`](/formulas/string-formulas.md#upcase)、[`downcase`](/formulas/string-formulas.md#downcase)、[`capitalize`](/formulas/string-formulas.md#capitalize)、[`titleize`](/formulas/string-formulas.md#titleize)
    - 必要な形式に応じて文字列の大文字と小文字を変更します。
:::


::: details alpha-2とalpha-3のコンテンツを変換できますか？

はい。以下の数式を使用して、alpha-2およびalpha-3の国コードを国名に変換したり、国名を国コードに変換したりすることができます。

- [`to_country_alpha2`](/formulas/string-formulas.md#to-country-alpha2)
- [`to_country_alpha3`](/formulas/string-formulas.md#to-country-alpha3)
- [`to_country_name`](/formulas/string-formulas.md#to-country-name)

以下の数式を使用して、alpha-2およびalpha-3の国コードを通貨コードまたは通貨名に変換することもできます。

- [`to_currency_code`](/formulas/string-formulas.md#to-currency-code)
- [`to_currency_name`](/formulas/string-formulas.md#to-currency-name)
:::

::: details ordinalize数式の目的は何ですか？

[`ordinalize`数式](/formulas/string-formulas.md#ordinalize)は、数値を序数の文字列（例：1st、2nd、3rdなど）に変換します。
:::

::: details データ型を変換するためにどの数式を使用すればよいですか？

[`to_s`数式](/formulas/string-formulas.md#to-s)を使用して、数値や日付などのさまざまなデータ型を文字列データ型に変換することができます。
:::