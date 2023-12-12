 # Active Directory - エントリの更新アクション

## エントリの更新
このアクションは、Active Directory内の既存のエントリを更新します。

![エントリの更新アクション](~@img/active_directory/update_entry.png)
*エントリの更新アクション*

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
        エントリオブジェクトの属性を調査するために使用されます。既存のエントリの識別名を指定してください。このオブジェクトの属性は、このトリガーの出力フィールドで利用できます。
      </td>
    </tr>
    <tr>
      <td>エントリDN</td>
      <td>
        更新するエントリの識別名です。
      </td>
    </tr>
    <tr>
      <td>更新する属性</td>
      <td>
        エントリの更新する属性です。この属性リストは、提供された<b>サンプルエントリDN</b>に依存します。
      </td>
    </tr>
  </tbody>
</table>

### 出力フィールド
このアクションの出力は、更新されたエントリの詳細情報です。このエントリの属性は、アクションの入力で提供された**サンプルエントリDN**に基づいています。

![エントリの出力フィールド](~@img/active_directory/entry_output_schema.png)
*エントリの出力フィールド*