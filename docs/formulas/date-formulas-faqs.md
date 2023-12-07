---
title: Date formulas FAQs
date: 2023-10-11 05:00:00 Z
---

# Date formulas FAQs

This page provides answers to frequently asked questions (FAQs) about date formulas.

::: details What are date and datetime formulas used for?

Date and datetime formulas allow you to work with date and time datapills. These formulas are used to manipulate and perform calculations on date and time data in Workato.

:::

::: details Are all Ruby methods supported by date formulas?

No, not all Ruby methods are supported. You can reach out to Workato to add additional formulas to the allowlist. Refer to the [Date formulas](/formulas/date-formulas) documentation for more information.

:::

::: details How can I perform arithmetic with date and datetime data?

You can use keywords like `seconds`, `minutes`, `days`, `months`, and `years` in combination with date and datetime formulas to perform addition and subtraction operations.

:::

::: details What units can I use with the from_now formula, and how does it work?

The **from_now** formula returns a future timestamp by a specified time duration. It calculates the timestamp at runtime.

You can use units like seconds, minutes, hours, days, months, or years with the **from_now** formula to calculate future timestamps. It calculates the current timestamp and offsets it by the specified time duration.

:::


::: details What does the wday formula return?

The **wday** formula returns the day of the week, with Sunday represented as `0` , Monday as `1`, and so on for each day of the week.

:::

::: details How can I convert a string into a date datatype?

You can use the **to_date** formula to convert a string into a date datatype. This formula allows you to specify the date format if necessary.

:::

::: details What does the strftime formula do, and how can I use it?

The **strftime** formula allows you to format a datetime input as a user-defined string. You can customize the output format using various codes, as specified in the parameters.

:::

::: details How can I convert a string into an ISO timestamp?

You can use the **to_time** formula to convert a string into an ISO timestamp, and it will use the UTC timezone.

:::

::: details How can I convert a date or datetime to a different timezone?

The **in_time_zone** formula can be used to convert a date or datetime to a different timezone using timezone names from the IANA time zone database.

You can use the list of timezone names to determine which timezone to use.

:::

::: details How do I determine if a datetime is within Daylight Savings Time (DST)?

You can use the **dst?** formula to check if a datetime is within Daylight Savings Time.

:::
