 ---
title: Workatoコネクター - Bamboo HR
date: 2020-07-01 18:00:00 Z
---

# Bamboo HR

[Bamboo HR](https://www.bamboohr.com/)は、人材データを収集、管理、分析するためのHRソフトウェアソリューションです。

## APIバージョン

Bamboo HRコネクターは[Bamboo REST API v1](https://documentation.bamboohr.com/)を使用しています。

## WorkatoでBamboo HRに接続する方法

![Bamboo HR接続の設定](~@img/connectors/bamboo-hr/connect-to-bamboo-hr.png)
_Bamboo HR接続の設定_

| 入力フィールド   | 説明                                                                                       |
| --------------- | ------------------------------------------------------------------------------------------- |
| 接続名           | この接続に一意の名前を付けて、どのインスタンスに接続されているかを識別します。               |
| APIトークン      | APIトークン。[このAPIトークンの作成方法](#how-to-create-an-api-key-on-bamboo-hr)を参照してください。 |
| サブドメイン     | Bamboo HRインスタンスのベースURL。                                                         |

## Bamboo HRでAPIキーを作成する方法

| 手順 | 説明                                                                                                                                                                                                                                                                    |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1.    | **プロファイル** > **APIキー**に移動<br>![Bamboo HRのAPIキーに移動](~@img/connectors/bamboo-hr/find-api-keys.png)<br>_Bamboo HRのAPIキーに移動_                                                                                                            |
| 2.    | **新しいキーを追加**を選択して、新しいAPIキーを作成<br>![新しいAPIキーを追加](~@img/connectors/bamboo-hr/add-new-api-key.png)<br>_新しいAPIキーを追加_                                                                                                                             |
| 3.    | この新しいAPIキーに説明的な名前を指定します。例えば、`workato_user`。<br>![新しいAPIキーを追加](~@img/connectors/bamboo-hr/add-api-key-name.png)<br>_新しいAPIキーを追加_                                                                                                |
| 4.    | APIキーが生成されます。このキーを安全な場所に保存してください。<br><br>なお、このAPIキーはここでのみ表示されます。この手順の後では、このキーを取得することはできなくなります。<br>![APIキーを保存](~@img/connectors/bamboo-hr/save-api-key.png)<br>_APIキーを保存_ |

詳細については、[Bamboo HRのドキュメント](https://documentation.bamboohr.com/docs#authentication)を参照してください。

## トリガーとアクション

他の章を参照できます:

### Bamboo HRトリガー

- [新しい従業員トリガー](/connectors/bamboo-hr/new-employee-trigger.md)
- [新しい従業員トリガー（リアルタイム）](/connectors/bamboo-hr/new-employee-realtime-trigger.md)
- [更新された従業員トリガー](/connectors/bamboo-hr/updated-employee-trigger.md)
- [更新された従業員トリガー（リアルタイム）](/connectors/bamboo-hr/updated-employee-realtime-trigger.md)
- [カスタム従業員レポートのスケジュールトリガー](/connectors/bamboo-hr/schedule-custom-report-trigger.md)

### Bamboo HRアクション

- [従業員の作成アクション](/connectors/bamboo-hr/create-employee-action.md)
- [有給休暇リクエストの作成/更新アクション](/connectors/bamboo-hr/create-update-time-off-request-action.md)
- [従業員の更新アクション](/connectors/bamboo-hr/update-employee-action.md)
- [有給休暇リクエストのステータスの更新アクション](/connectors/bamboo-hr/update-time-off-request-status-action.md)
- [IDで従業員の詳細を取得するアクション](/connectors/bamboo-hr/get-employee-details-action.md)
- [ディレクトリ内の従業員の一覧を取得するアクション](/connectors/bamboo-hr/list-employees-in-directory-action.md)
- [有給休暇リクエストの一覧を取得するアクション](/connectors/bamboo-hr/list-time-off-requests-action.md)
- [従業員のテーブルレコードを取得するアクション](/connectors/bamboo-hr/get-table-records-of-employee-action.md)
- [カスタム従業員レポートの作成アクション](/connectors/bamboo-hr/create-custom-report-action.md)
- [会社の従業員レポートをIDで取得するアクション](/connectors/bamboo-hr/get-company-report-by-id-action.md)