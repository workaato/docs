 ---
title: Workatoコネクター - Active Directoryエントリの追加アクション
date: 2018-02-02 06:10:00 Z
---

# Active Directory - エントリの追加アクション

## エントリの追加
このアクションは、Active Directoryに単一のエントリを追加します。

![エントリの追加アクション](~@img/active_directory/add_entry.png)
*エントリの追加アクション*

### 入力フィールド

<table class="unchanged rich-diff-level-one">
  <thead>
    <tr>
        <th width='25%'>入力フィールド</th>
        <th>説明</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>サンプルエントリDN</td>
      <td>
        エントリオブジェクトの属性を調査するために使用されます。既存のエントリの識別名を指定します。このオブジェクトの属性は、このトリガーの出力フィールドで利用できます。
      </td>
    </tr>
    <tr>
      <td>エントリDN</td>
      <td>
        追加するエントリの識別名です。
      </td>
    </tr>
    <tr>
      <td>追加する属性</td>
      <td>
        新しいエントリに追加する属性です。この属性のリストは、提供された<b>サンプルエントリDN</b>に依存します。
      </td>
    </tr>
  </tbody>
</table>

### 出力フィールド
このアクションの出力は、追加されたエントリの詳細情報です。このエントリの属性は、アクションの入力で提供された**サンプルエントリDN**に基づいています。

![エントリの出力フィールド](~@img/active_directory/entry_output_schema.png)
*エントリの出力フィールド*