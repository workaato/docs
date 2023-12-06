 ---
title: Workatoコネクター - Asana - IDによるユーザー詳細の取得
date: 2021-09-21 17:07:05 Z
---

# Asanaコネクター - IDによるユーザー詳細の取得
このアクションは、AsanaでIDによってユーザーの詳細を取得します。

## 入力

| フィールド | 説明 |
|:--- |:--- |
| People ID<br>**必須** | ユーザーのGIDです。 |
{: .sdk-ref :}

## 出力

| フィールド | 説明 |
|:--- |:--- |
| People | Peopleオブジェクトには、以下のフィールドが含まれています。<ul><li>People ID</li><li>名前</li><li>メール</li><li>写真</li><li>ワークスペース</li></ul> |
{: .sdk-ref :}