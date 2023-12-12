---
title: List and hash formulas FAQs
date: 2023-11-06 05:00:00 Z
page_nav_depth: 3
---

# List and hash formulas FAQs

Get answers to frequently asked list and hash formula questions.

::: details How are lists used in Workato?

A list in Workato is an ordered, integer-indexed collection of objects, similar to arrays in other programming languages.
:::

::: details How do you access items inside a list in Workato?

You can access items in a list using indexing, starting at 0. For example, `number_list[0]` would access the first line item.
:::

::: details Does Workato support negative indexes for lists?

Yes, Workato supports negative indexes for lists. For example, `number_list[-1]` would access the last item in a list.
:::

::: details What do the first and last formulas do?

The [`first` formula](/formulas/array-list-formulas.md#first) returns the first item in a list. The [`last` formula](/formulas/array-list-formulas.md#last) returns the last item in a list.
:::

::: details What is a hash, and how does it differ from a list?

A hash in Workato is a collection of unique keys and their corresponding values. Unlike lists, hashes allow you to use any object type as keys.
:::

::: details How are lists of hashes used?

Lists of hashes represent complex data structures where each item in the list is a hash with multiple key-value pairs. Lists of hashes are often used for organizing and processing structured data.

:::

::: details How do you access values in a hash?

You can access values in a hash using the keys. For example, `line_item["item_name"]` accesses the value associated with the `item_name` key.

:::

::: details Is there a direct union (&) operand for combining lists in Workato?

Workato doesn't support a direct union (&) operand. To achieve a similar result, you can combine lists using the `concat` formula and then remove duplicates with the `uniq` formula. [Learn how](/formulas/array-list-formulas.md#union).

:::

::: details How can you find the difference between two lists?

To find the difference between two lists, you can use the subtraction (-) operand. For example, `list - updated_list` returns the items present in `list` but not in `updated_list`.

:::
