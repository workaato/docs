 ---
title: Workatoコネクター - Active Directory 検索エントリーアクション
date: 2018-02-02 06:10:00 Z
---

# Active Directory - 検索エントリーアクション

## エントリーの検索
このアクションは、Active Directory内の条件に一致するエントリーを検索します。

![検索エントリーアクション](~@img/active_directory/search_entries.png)
*検索エントリーアクション*

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
      <td>サンプルエントリーDN</td>
      <td>
        エントリーオブジェクトの属性を調査するために使用します。既存のエントリーの識別名を指定してください。このオブジェクトの属性は、このトリガーの出力フィールドで利用できます。
      </td>
    </tr>
    <tr>
      <td>エントリーの検索条件</td>
      <td>
        フィルタリングするための各属性の値を指定します。すべての値に一致するエントリーのみが処理されます。
      </td>
    </tr>
    <tr>
      <td>エントリーの検索フィルター</td>
      <td>
        このトリガーで処理されるエントリーをフィルタリングするために使用します。これは<b>検索条件</b>と似ていますが、より複雑な条件を実行するためにLDAP構文を使用できます。複合条件やネストされた条件を使用する必要がある場合は、この入力を使用してください。<br><br>
        たとえば、<code>&(ou=Dev)(objectClass=Person)</code>を使用して、<b>Dev</b>組織単位から<b>Person</b>エントリーのみを取得します。
      </td>
    </tr>
  </tbody>
</table>

### 出力フィールド
このトリガーの出力はエントリーのリストです。各エントリーの属性は、トリガーの入力で指定された**サンプルエントリーDN**に基づいています。

![エントリーの出力フィールド](~@img/active_directory/entries_output_schema.png)
*エントリーの出力フィールド*