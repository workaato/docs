 ---
title: Asanaコネクター - サブタスクの作成
date: 2021-09-21 17:07:05 Z
---

# Asanaコネクター - サブタスクの作成
このアクションは、Asanaにサブタスクを作成します。

## 入力

| フィールド | 説明 |
|:--- |:--- |
| Projects | このタスクが所属するプロジェクト。 |
| Task name | タスクの名前。 |
| Description | タスクの説明。 |
| Assignee | このタスクに割り当てられた人。 |
| Assignee status | 割り当てられた人のステータス。 |
| Completed | タスクが完了したかどうか。 |
| Due on | タスクの期限日。 |
| Due at | タスクの期限日と時間。 |
| Followers | このタスクをフォローしている人。 |
| Heart this | このタスクにハートを追加するかどうか。 |
| Start on | 開始日をスケジュールします。この値が指定されている場合、"Due on"または"Due at"フィールドを指定する必要があります。 |
| Like this | このタスクにいいねを追加するかどうか。 |
| Tags | このタスクに添付されたタグ。 |
{: .sdk-ref :}

## 出力

| フィールド | 説明 |
|:--- |:--- |
| Task ID | タスクのID。 |
| Assignee | このタスクに割り当てられた人。 |
| Assignee status | 割り当てられた人のステータス。 |
| Completed | タスクが完了したかどうか。 |
| Completed at | タスクが完了した日時。 |
| Created at | このレコードが作成された日時。 |
| Due on | タスクの期限日。 |
| Due at | タスクの期限日と時間。 |
| Followers | このタスクをフォローしている人。 |
| Number of hearts | タスクに与えられたハートの数。 |
| Hearts | タスクにハートを追加した人。 |
| Start on | このタスクの開始日。 |
| Like this | 承認されたユーザーがこのタスクをいいねしたかどうかを示します。 |
| Number of likes | タスクに追加されたいいねの数。 |
| Likes | このタスクをいいねした人。 |
| Modified at | タスクが最後に変更された日時。 |
| Task name | タスクの名前。 |
| Description | タスクの説明。 |
| Projects | このタスクが所属するプロジェクト。 |
| Parent Task | このタスクの親タスク。 |
| Workspace | このタスクが所属するワークスペース。 |
| Memberships | このタスクに関するメンバーシップの詳細。 |
| Tags | このタスクに添付されたタグ。 |
| Created by | このタスクを作成したユーザー。 |
{: .sdk-ref :}