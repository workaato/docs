---
title: Formula mode
date: 2020-07-28 00:00:00 Z
---

# Formula mode

::: tip SUMMARY
- To use formulas in Workato, activate formula mode at the field level.
- Formula mode provides approved formulas and guidance for data manipulation.
- The editor shows type-specific formulas based on the datapill type in an input field.
- Text must be explicitly formatted in formula mode, unlike in text mode.
:::

To start using formulas, you need to be in formula mode. Formula mode needs to be switched on at the field level, and most input fields support formula mode.

To toggle from text mode into formula mode, click **formula** on the top-right of the input field. This changes the background color to indicate that you are in formula mode. The type icon on the left will also change to the `fx` icon.

![Formula mode](~@img/formula-docs/formula-mode.png)
_Formula mode is displayed with the `fx` symbol_

When the input field is toggled into formula mode, the string type input field changes icon from String type to `formulas` type.

In formula mode, the formula editor provides a set of formulas that are on the allowlist and available for data transformation/manipulation, and provides additional help on how to use these formulas.

## Filter formulas displayed by data type
The formula editor will display type-specific formulas for your datapills. Refer to [this article](/recipes/data-pills-and-mapping.md) for more on the different types of datapills.

When a string type datapill is dropped into an input field in formula mode, the editor shows the list of formulas applicable to strings.

![String formula list](~@img/formula-docs/string-formula-list.png)
*Formula editor showing the list of string formulas*

## Formula hints and syntax
Once a formula is selected, a detailed description of the formula will be provided. This includes an explanation of how to use this formula and examples for how it can be used. 

![Formula editor hint](~@img/formula-docs/formula-editor-hint.png)
*Detailed description and hints for the split formula*

## Text VS formula mode
::: details Video guide: From text to formula mode
<Video src="https://www.youtube.com/embed/e2vt8x5mHdM"/>
:::

In text mode, text, and pills can be mapped into the input fields easily, and they will result in a text that looks exactly like what is formed. On the other hand, text needs to be explicitly formatted in formula mode.

Let's use an example of a recipe that sends an email to new leads in Salesforce. If a new lead called Madison Diaz is created, we wish to send the following email:

```
Hi Madison,

Thanks for joining our mailing list! We're excited to have you!
```

In text mode, the **Message** can simply be formed like this:

![Welcome email in text mode](~@img/formula-docs/welcome-email-in-text.png)
*Email in text mode. [Example recipe](https://www.workato.com/recipes/504766)*

In formula mode, text must have proper string syntax:

![Welcome email in formula mode](~@img/formula-docs/welcome-email-in-formula.png)
*Email in formula mode. [Example recipe](https://www.workato.com/recipes/496603)*
