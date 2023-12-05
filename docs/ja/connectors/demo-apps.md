---
title: Workato デモアプリ
date: 2020-02-24 11:15:00 +0800
---

# デモアプリ {: #demo-apps :}
デモアプリは、実際のWorkatoコネクタの動作を模したコネクタのセットです。デモアプリによって、実際のデータまたは実際のアプリケーションへの接続を必要とせずに、レシピ構築の概念をテストし学習できるシミュレーション方法を提供できます。

Additionally, demo apps provide a safe environment for testing and troubleshooting recipes as the data used in demo apps are simulated, generated data. This can help users become more familiar with the platform, recipe building with different types of apps, and the flow of logic in recipes.

## Getting started {: #getting-started :}
::: tip AVAILABILITY
Demo apps are available to workspaces in the private preview program only. Customers or partners who would like to use Demo apps for internal training purposes should contact their Workato representative.
:::

Demo apps can be found in the recipe editor, during app selection. These apps are tagged with `DEMO` and the following are available:

- **Zendesk Demo**

## What can users do with Demo apps? {: #capabilities :}

Demo apps allow builders dive straight into recipe building without having to create connections, trigger events, or provide real data in an application. This makes learning faster and more efficient, enabling builders to focus on recipe building patterns. These patterns and features includes:

- **Triggers:** Demo apps [triggers](/recipes/triggers.md) allow users to build recipes to handle real-time events or a batch of events.

- **Actions:** Try basic Search, Get, Create, and Update [actions](/recipes/steps.md) and learn to handle those that return single or multiple records.

- **Data mapping:** Demo apps allow users to map [datapills](/recipes/data-pills-and-mapping.md#default-datapills) from one application to another. Users learn how to use the datatree and map them to the corresponding fields in the destination app. Users can also learn how to use group mapping with data from demo apps.

- **Logic flows:** Use Demo app triggers and actions alongside trigger conditions and `IF`/`IF/ELSE`/`FOR EACH` statements to learn about the [different operators](/recipes/steps.md#if-condition-step).

- **Testing:** Demo apps enable builders to [test](/recipes/testing.md) and troubleshoot their recipes as they build it. Builders can learn to build iteratively by testing frequently. Both inputs and outputs are simulated and can be viewed after builders test or run a recipe.
