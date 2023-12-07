---
title: String formulas FAQs
date: 2023-11-06 05:00:00 Z
---

# String formulas FAQs

Get answers to frequently asked string formula questions.

::: details What are string formulas in Workato?
Strings are sequences of text and characters. String formulas in Workato are allowlisted Ruby methods that enable you to manipulate and work with strings.
:::

::: details What is the purpose of conditionals in string formulas?
Conditionals allow you to apply if-else logic to strings, which you can use to perform various actions based on conditions. Refer to [Conditionals](/formulas/conditions.md#conditionals) for more robust instructions on how to add conditionals to formulas.
:::

::: details How do I include and exclude work in string formulas?
The [`include?` formula](/formulas/string-formulas.md#include) checks if a specific substring is present in a string and returns `true` if it is found.

The [`exclude?` formula](/formulas/string-formulas.md#exclude) checks if a specific substring is *not* present in a string and returns `true` if it is *not* found.
:::

::: details Can I use text manipulation with string formulas?
Yes. You can manipulate text within strings with the following formulas:

- [`parameterize`](/formulas/string-formulas.md#parameterize)
    - Replaces special characters.

- [`strip`](formulas/string-formulas.md#strip)
    - Removes white spaces from the beginning and end.

- [`upcase`](/formulas/string-formulas.md#upcase), [`downcase`](/formulas/string-formulas.md#downcase), [`capitalize`](/formulas/string-formulas.md#capitalize), and [`titleize`](/formulas/string-formulas.md#titleize)
    - Changes the case of strings depending on your required format.
:::


::: details Can I convert alpha-2 and alpha-3 content?

Yes. You can convert alpha-2 and alpha-3 country codes to country names or convert country names to country codes with the following formulas:

- [`to_country_alpha2`](/formulas/string-formulas.md#to-country-alpha2)
- [`to_country_alpha3`](/formulas/string-formulas.md#to-country-alpha3)
- [`to_country_name`](/formulas/string-formulas.md#to-country-name)

You can convert alpha-2 and alpha-3 country codes to currency codes or currency names with the following formulas:

- [`to_currency_code`](/formulas/string-formulas.md#to-currency-code)
- [`to_currency_name`](/formulas/string-formulas.md#to-currency-name)
:::

::: details What is the purpose of the ordinalize formula?

The [`ordinalize` formula](/formulas/string-formulas.md#ordinalize) turns a number into an ordinal string, such as 1st, 2nd, 3rd, and so on.
:::

::: details What formula should I use to convert data types?

You can use the [`to_s` formula](/formulas/string-formulas.md#to-s) to convert various data types, including numbers, dates, and more into string data types.
:::