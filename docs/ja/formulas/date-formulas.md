 ---
title: 日付の計算式
date: 2017-03-30 05:00:00 Z
---

# 日付の計算式
::: details 動画ガイド：計算式モードで日付を変換する方法を学ぶ
<Video src="https://www.youtube.com/embed/Saq5ybJauVM"/>
:::
日付と日時の計算式を使用すると、日付と時間のデータピルで作業できます。これらの計算式は[Rubyのメソッド](http://ruby-doc.org/core-2.3.3/Time.html)のallowlistに追加されているため、すべてのRubyメソッドがサポートされているわけではありません。allowlistに追加するためには、[お問い合わせください](https://support.workato.com/en/support/tickets/new)。

## 日付の演算

次のキーワードを使用して、日付と日時のデータで演算を行います：
- `seconds`
- `minutes`
- `days`
- `months`
- `years`

これらのキーワードを計算式と組み合わせることで、加算と減算を行うことができます。

### 使用例

| 日付の演算                                 | 出力         |
| ------------------------------------------ | ------------ |
| <kbd>"2020-01-01"</kbd>.to_date + 2.days   | "2020-01-03" |
| <kbd>"2020-01-01"</kbd>.to_date - 2.days   | "2019-12-30" |
| <kbd>"2020-01-01"</kbd>.to_date + 2.months | "2020-03-01" |
| <kbd>"2020-01-01"</kbd>.to_date - 2.months | "2019-11-01" |
| <kbd>"2020-01-01"</kbd>.to_date + 2.years  | "2022-01-01" |
| <kbd>"2020-01-01"</kbd>.to_date - 2.years  | "2018-01-01" |

---

## `now`

実行時の時刻と日付を米国太平洋標準時（PST）で返します。

### 使用例

| 計算式       | 結果                             |
| ------------- | ---------------------------------- |
| now           | "2022-02-01T07:00:00.000000-08:00" |
| now + 8.hours | "2022-02-01T15:00:00.000000-08:00" |
| now + 2.days  | "2022-02-03T07:00:00.000000-08:00" |

### 動作原理

この計算式は、ジョブが処理されているときのタイムスタンプを計算します。この計算式を使用する各ステップは、ステップが実行されるタイムスタンプを返します。

::: tip 出力データピル
時間を含まない日付のみが必要な場合は、代わりに<u>[today](/formulas/date-formulas.md#today)</u>計算式を使用してみてください。
:::

### 関連項目

- [today](/formulas/date-formulas.md#today)：実行時の日付を返します。
- [in_time_zone](/formulas/date-formulas.md#in-time-zone)：時間値を別のタイムゾーンに変換します。

---

## `today`

実行時の日付を米国太平洋標準時で返します。

### 使用例

| 計算式        | 結果                      			|
| --------------- | ----------------------------------- |
| today           | "2022-02-01" 						|
| today + 8.hours | "2022-02-01T15:00:00.000000-08:00" 	|
| today + 2.days  | "2022-02-03"                		|

### 動作原理

この計算式は、ジョブが処理されているときのタイムスタンプを計算します。この計算式を使用する各ステップは、ステップが実行される日付を返します。

::: tip 出力データピル
日付と時間が必要な場合は、代わりに<u>[now](/formulas/date-formulas.md#now)</u>計算式を使用してみてください。
:::

### 関連項目

- [now](/formulas/date-formulas.md#now)：実行時の時刻と日付を返します。
- [in_time_zone](/formulas/date-formulas.md#in-time-zone)：時間値を別のタイムゾーンに変換します。 rts a time value to a different time zone.

---

## `from_now`

指定された時間間隔後の未来のタイムスタンプを返します。タイムスタンプは実行時に計算されます。

### 構文

<kbd>単位</kbd>.from_now

- <kbd>単位</kbd> - オフセットする時間値です。

### 使用例

| 式       				 | 結果                    		   |
| ------------------------------ | ----------------------------------- |
| <kbd>30.seconds</kbd>.from_now | "2022-02-01T07:00:30.000000-08:00"  |
| <kbd>2.months</kbd>.from_now   | "2022-04-01T07:00:00.000000-08:00"  |
| <kbd>3.days</kbd>.from_now     | "2022-02-04T07:00:00.000000-08:00"  |

### 動作方法

この式は、現在のタイムスタンプを計算し、指定された時間間隔でオフセットします。このタイムスタンプは、ジョブが処理されているときに計算されます。この式を使用する各ステップは、実行される各ステップのタイムスタンプを返します。

::: tip 単位
次のいずれかの単位を使用できます：`seconds`、`minutes`、`hours`、`days`、`months`、または`years`。
:::

### 関連情報

- [ago](/formulas/date-formulas.md#ago): 指定された時間間隔前の過去のタイムスタンプを返します。
- [now](/formulas/date-formulas.md#now): 実行時の時刻と日付を返します。
- [today](/formulas/date-formulas.md#today): 実行時の日付を返します。

---

## `ago`

指定された時間間隔前の過去のタイムスタンプを返します。タイムスタンプは実行時に計算されます。

### 構文

<kbd>単位</kbd>.ago

- <kbd>単位</kbd> - オフセットする時間値です。

### 使用例

| 式        | 結果                      |
| --------------- | --------------------------- |
| <kbd>2.months</kbd>.ago   | "2020-10-04 14:45:29 -0700"  |
| <kbd>3.days</kbd>.ago     | "2020-12-01 14:45:29 -0700"  |
| <kbd>30.seconds</kbd>.ago | "2020-12-04 14:15:29 -0700"  |

### 動作方法

この式は、現在のタイムスタンプを計算し、指定された時間間隔でオフセットします。このタイムスタンプは、ジョブが処理されているときに計算されます。この式を使用する各ステップは、実行される各ステップのタイムスタンプを返します。

::: tip 単位
次のいずれかの単位を使用できます：`seconds`、`minutes`、`hours`、`days`、`months`、または`years`。
:::

### 関連情報

- [from_now](/formulas/date-formulas.md#from-now): 指定された時間間隔後の未来のタイムスタンプを返します。
- [now](/formulas/date-formulas.md#now): 実行時の時刻と日付を返します。
- [today](/formulas/date-formulas.md#today): 実行時の日付を返します。

---

## `wday`

曜日を返します。日曜日は0、月曜日は1です。

### 構文

<kbd>Date</kbd>.wday

- <kbd>Date</kbd> - 日付または日時のデータ型です。

### 使用例

| 例                                                  | 結果 |
| -------------------------------------------------------- | ------ |
| today.wday                                               | 4      |
| <kbd>"01/12/2020"</kbd>.to_date(format:"DD/MM/YYYY").wday | 2      |

### 動作方法

この式は、ジョブが処理されているときに現在の日を計算します。曜日は整数に変換されます。日曜日 = 0、月曜日 = 1、火曜日 = 2、水曜日 = 3、木曜日 = 4、金曜日 = 5、土曜日 = 6です。 y = 1.

::: tip ヒント: 日付データ型への変換
この式は、日付または日時のデータ型でのみ動作します。[to_date](/formulas/date-formulas.md#to-date) を使用して、文字列を日付データ型に変換してください。
:::

### 関連情報

- [yday](/formulas/date-formulas.md#yday): 年の日数を返します。
- [yweek](/formulas/date-formulas.md#yweek): 年の週数を返します。

---

## `yday`

年の日数を返します。

### 構文

<kbd>Date</kbd>.yday

- <kbd>Date</kbd> - 日付または日時のデータ型です。

### 使用例

| 例                                                         | 結果 |
| --------------------------------------------------------- | ------ |
| today.yday                                                | 338    |
| <kbd>"2020-01-01"</kbd>.to_date(format:"YYYY-MM-DD").yday | 1      |
| <kbd>"2020-02-01"</kbd>.to_date(format:"YYYY-MM-DD").yday | 32     |

### 動作方法

この式は、ジョブが処理されている現在の日を計算します。年の日数は整数の出力に変換されます。

::: tip ヒント: 日付データ型への変換
この式は、日付または日時のデータ型でのみ動作します。[to_date](/formulas/date-formulas.md#to-date) を使用して、文字列を日付データ型に変換してください。
:::

### 関連情報

- [wday](/formulas/date-formulas.md#wday): 週の日数を返します。
- [yweek](/formulas/date-formulas.md#yweek): 年の週数を返します。

---

## `yweek`

年の週数を返します。

### 構文

<kbd>Date</kbd>.yweek

- <kbd>Date</kbd> - 日付または日時のデータ型です。

### 使用例

| 例                                                    | 結果 |
| ---------------------------------------------------------- | ------ |
| today.yweek                                                | 49     |
| <kbd>"2020-01-01"</kbd>.to_date(format:"YYYY-MM-DD").yweek | 1      |
| <kbd>"2020-02-01"</kbd>.to_date(format:"YYYY-MM-DD").yweek | 5      |

### 動作方法

この式は、ジョブが処理されている現在の日を計算します。年の週数は整数の出力に変換されます。

::: tip ヒント: 日付データ型への変換
この式は、日付または日時のデータ型でのみ動作します。[to_date](/formulas/date-formulas.md#to-date) を使用して、文字列を日付データ型に変換してください。
:::

### 関連情報

- [wday](/formulas/date-formulas.md#wday): 週の日数を返します。
- [yday](/formulas/date-formulas.md#yday): 年の日数を返します。

---

## `beginning_of_hour`

指定された日時の時刻の先頭を表す日時を返します。

### 構文

<kbd>Datetime</kbd>.beginning_of_hour

- <kbd>Datetime</kbd> - 入力の日時です。

### 使用例

| 式                                                         | 結果                             |
| --------------------------------------------------------------- | ---------------------------------- |
| today.to_time.beginning_of_hour                                 | "2020-12-02T16:00:00.000000-07:00" |
| <kbd>"2020-06-01T01:30:45.000000+00:0 0"</kbd>.beginning_of_hour | "2020-06-01T01:00:00.000000+00:00" |
| <kbd>"2020-06-01"</kbd>.to_time.beginning_of_hour               | "2020-06-01T00:00:00.000000+00:00" |

---

## `beginning_of_day`

指定された日付/日時の午前0時の日時を返します。

### 構文

<kbd>Date</kbd>.beginning_of_day

- <kbd>Date</kbd> - 入力された日付または日時。

### 使用例

| 式                                                              | 結果                               |
| -------------------------------------------------------------- | ---------------------------------- |
| today.beginning_of_day                                         | "2020-12-02T00:00:00.000000-07:00" |
| <kbd>"2020-06-01"</kbd>.to_date.beginning_of_day               | "2020-06-01T00:00:00.000000+00:00" |
| <kbd>"2020-06-01T01:30:45.000000+00:00"</kbd>.beginning_of_day | "2020-06-01T00:00:00.000000+00:00" |

---

## `beginning_of_week`

指定された日付/日時の前の*月曜日*の日付を返します。

### 構文

<kbd>Date</kbd>.beginning_of_week

- <kbd>Date</kbd> - 入力された日付または日時。

### 使用例

| 式                                                              | 結果                               |
| -------------------------------------------------------------- | ---------------------------------- |
| today.beginning_of_week                                         | "2020-11-30T00:00:00.000000+00:00" |
| <kbd>"2020-06-01"</kbd>.to_date.beginning_of_week               | "2020-06-01T00:00:00.000000+00:00" |
| <kbd>"2020-06-01T01:30:45.000000+00:00"</kbd>.beginning_of_week | "2020-06-01T00:00:00.000000+00:00" |

---

## `beginning_of_month`

指定された日付/日時の月の最初の日を返します。

### 構文

<kbd>Date</kbd>.beginning_of_month

- <kbd>Date</kbd> - 入力された日付または日時。

### 使用例

| 式                                                              | 結果                               |
| -------------------------------------------------------------- | ---------------------------------- |
| today.beginning_of_month                                         | "2020-12-01T00:00:00.000000+00:00" |
| <kbd>"2020-06-01"</kbd>.to_date.beginning_of_month               | "2020-06-01T00:00:00.000000+00:00" |
| <kbd>"2020-06-01T01:30:45.000000+00:00"</kbd>.beginning_of_month | "2020-06-01T00:00:00.000000+00:00" |

---

## `beginning_of_year`

指定された日付/日時の年の最初の日を返します。

### 構文

<kbd>Date</kbd>.beginning_of_year

- <kbd>Date</kbd> - 入力された日付または日時。

### 使用例

| 式                                                              | 結果                               |
| -------------------------------------------------------------- | ---------------------------------- |
| today.beginning_of_year                                         | "2020-01-01T00:00:00.000000+00:00" |
| <kbd>"2020-06-01"</kbd>.to_date.beginning_of_year               | "2020-01-01T00:00:00.000000+00:00" |
| <kbd>"2020-0 ## `end_of_month`

指定された日付/日時の月の最終日を返します。この式は、入力データに基づいて日付または日時を返します。

### 構文

<kbd>Date</kbd>.end_of_month

- <kbd>Date</kbd> - 入力の日付または日時です。

### 使用例

| 式                                                          | 結果                             |
| ---------------------------------------------------------------- | ---------------------------------- |
| today.end_of_month                                         | "2020-12-31"                       |
| <kbd>"2020-06-01"</kbd>.to_date.end_of_month               | "2020-06-30"                       |
| <kbd>"2020-06-01T01:30:45.000000+00:00"</kbd>.to_time.end_of_month | "2020-06-30T23:59:59.999999+00:00" |

---

## `strftime`

ユーザー定義の文字列として、日時の入力を返します。

### 構文

<kbd>Date</kbd>.strftime(<span style="color:#FF0000">format</span>)

- <kbd>Date</kbd> - 入力の日付または日時です。
- <span style="color:#FF0000">format</span> - 文字列として書かれたユーザー定義の日時の形式です。

### 使用例

| 式                                                                      | 結果                      |
| ----------------------------------------------------------------------------- | --------------------------- |
| <kbd>"2020-06-05T17:13:27.000000-07:00"</kbd>.strftime("%Y/%m/%d")            | "2020/06/05"                |
| <kbd>"2020-06-05T17:13:27.000000-07:00"</kbd>.strftime("%Y-%m-%dT%H:%M:%S%z") | "2020-06-05T17:13:27-0700"  |
| <kbd>"2020-06-05T17:13:27.000000-07:00"</kbd>.strftime("%B %e, %l:%M%p")      | "6月 5, 5:13 午後"            |
| <kbd>"2020-06-05T17:13:27.000000-07:00"</kbd>.strftime("%A, %d %B %Y %k:%M")  | "金曜日, 05 6月 2020 0:00" |

### パラメータ

上記のように、各コード（%B、%e、%I など）は日時の特定の要素を参照します。カンマ（,）、スラッシュ（/）、コロン（:）などの静的テキストや句読点も追加できます。以下は、Workatoでよく使用されるコードの一覧です：

| コード             | 意味                                | 例<br>(2020-06-05T17:13:27.000000-07:00) |
| ---------------- | -------------------------------------- | ---------------------------------------- |
| %Y               | 世紀付きの年                      | 2020                                     |
| %m               | ゼロを付けた月                 | 06                                       |
| %B               | 月の完全な名前                        | 6月                                     |
| %b               | 月の省略名                 | 6月                                      |
| %d               | ゼロを付けた日付      | 05                                       |
| %e               | ゼロを付けない日付   | 5                                        |
| %H               | 時間（24時間制）  (24時間制)              | 17                                       |
| %k               | 0を付けずに表示される時間 (24時間制) | 17                                       |
| %I (大文字のI)   | 時間 (12時間制)              | 05                                       |
| %l (小文字のL) | 0を付けずに表示される時間 (12時間制) | 5                                        |
| %p               | AMまたはPM                               | PM                                       |
| %M               | 分                     | 13                                       |
| %S               | 秒                   | 27                                       |
| %L               | 分のミリ秒             | 000                                      |
| %z               | UTCからのタイムゾーンオフセット              | -0700                                    |
| %:z              | UTCからのタイムゾーンオフセット（フォーマットあり）    | -07:00                                   |
| %Z               | タイムゾーンの略称                 | UTC                                      |
| %A               | 曜日のフルネーム                          | 金曜日                                   |

完全なリストにアクセスするには、[Rubyのドキュメント](http://ruby-doc.org/core-2.3.3/Time.html#method-i-strftime)を参照してください。

### 動作方法

ユーザーが日時の形式を定義できるようにします。指定された形式で入力された日時を返します。

::: tip 入力データ型
入力は日付または日時のデータ型である必要があります。文字列を日付データ型に変換するには、<u>[to_date](/formulas/date-formulas.md#to-date)</u>式を使用できます。
:::

### 関連項目

- [to_date](/formulas/date-formulas.md#to-date): 日付データ型で日付を返します。

---

## `in_time_zone`

[IANAタイムゾーンデータベース](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)からタイムゾーン名を使用して、日付または日時を別のタイムゾーンに変換します。この式は日時を返します。

### 構文

<kbd>Date</kbd>.in_time_zone(<span style="color:#FF0000">format</span>)

- <kbd>Date</kbd> - 入力の日付または日時です。
- <span style="color:#FF0000">format</span> - ターゲットのタイムゾーンです。指定しない場合、この式はWorkatoアカウントがホストされている[データセンター](/datacenter/datacenter-overview.md)で定義されたタイムゾーンを返します。

### 使用例

| 式                                                    | 結果                             |
| ---------------------------------------------------------- | ---------------------------------- |
| today.in_time_zone("America/New_York")                     | "2020-12-01T20:00:00.000000-04:00" |
| today.to_time.in_time_zone("America/New_York")             | "2020-12-01T20:00:00.000000-04:00" |
| <kbd>"2020-06-01"</kbd>.to_time.in_time_zone               | "2020-05-31T20:00:00.000000-04:00" |
| <kbd>"2020-06-01T01:30:45.000000+00:00"</kbd>.in_time_zone | "2020-05-31T12:30:00.000000-05:00" |

---

## `dst?`

入力が真の場合、inp ut datetime は夏時間 (Daylight Savings Time) の範囲内にあるかどうかを判定します。

### 構文

<kbd>Datetime</kbd>.dst?

- <kbd>Datetime</kbd> - 入力の日付または日時です。

### 使用例

| 式                                                       | 結果   |
| ------------------------------------------------------------- | ------ |
| today.dst?                                                    | false  |
| today.in_time_zone("America/New_York").dst?                   | true   |
| <kbd>"2020-06-01"</kbd>.in_time_zone("America/New_York").dst? | true   |
| <kbd>"2020-09-06T18:30:15.671720-05:00"</kbd>.dst?            | true   |

### 地域の参照
以下の表を参照して、式で使用するタイムゾーン名を確認してください。

| 地域                       | 式で使用するタイムゾーン     | UTC ゾーン  | 夏時間オフセット        |
|------------------------------|--------------------------------|-----------|--------------------|
| International Date Line West | Pacific/Midway                 | UTC-11    |                    |
| Midway Island                | Pacific/Midway                 | UTC-11    |                    |
| American Samoa               | Pacific/Pago_Pago              | UTC-11    |                    |
| Hawaii                       | Pacific/Honolulu               | UTC-10    |                    |
| Alaska                       | America/Juneau                 | UTC-9     | :white_check_mark: |
| Pacific Time (US & Canada)   | America/Los_Angeles            | UTC-8     | :white_check_mark: |
| Tijuana                      | America/Tijuana                | UTC-8     | :white_check_mark: |
| Mountain Time (US & Canada)  | America/Denver                 | UTC-7     | :white_check_mark: |
| Arizona                      | America/Phoenix                | UTC-7     |                    |
| Chihuahua                    | America/Chihuahua              | UTC-7     | :white_check_mark: |
| Mazatlan                     | America/Mazatlan               | UTC-7     | :white_check_mark: |
| Central Time (US & Canada)   | America/Chicago                | UTC-6     | :white_check_mark: |
| Saskatchewan                 | America/Regina                 | UTC-6     |                    |
| Guadalajara                  | America/Mexico_City            | UTC-6     | :white_check_mark: |
| Mexico City                  | America/Mexico_City            | UTC-6     | :white_check_mark: |
| Monterrey                    | America/Monterrey              | UTC-6     | :white_check_mark: |
| Central America              | America/Guatemala              | UTC-6     |                    |
| Eastern Time (US & Canada)   | America/New_York               | UTC-5     | :white_check_mark: |
| Indiana (East)               | America/Indiana/Indianapolis   | UTC-5     | :white_check_mark: |
| Bogota                       | America/Bogota                 | UTC-5     |                    |
| Lima                         | America/Lima                   | UTC-5     |                    |
| Quito               | America/Lima                   | UTC-5     |                    |
| Atlantic Time (Canada)       | America/Halifax                | UTC-4     | :white_check_mark: |
| Caracas                      | America/Caracas                | UTC-4     |                    |
| La Paz                       | America/La_Paz                 | UTC-4     |                    |
| Santiago                     | America/Santiago               | UTC-4     | :white_check_mark: |
| Georgetown                   | America/Guyana                 | UTC-4     |                    |
| Newfoundland                 | America/St_Johns               | UTC-3:30  | :white_check_mark: |
| Brasilia                     | America/Sao_Paulo              | UTC-3     |                    |
| Buenos Aires                 | America/Argentina/Buenos_Aires | UTC-3     |                    |
| Montevideo                   | America/Montevideo             | UTC-3     |                    |
| Greenland                    | America/Godthab                | UTC-3     | :white_check_mark: |
| Mid-Atlantic                 | Atlantic/South_Georgia         | UTC-2     |                    |
| Azores                       | Atlantic/Azores                | UTC-1     | :white_check_mark: |
| Cape Verde Is.              | Atlantic/Cape_Verde            | UTC-1     |                    |
| Dublin                       | Europe/Dublin                  | UTC-1     | :white_check_mark: |
| Lisbon                       | Europe/Lisbon                  | UTC+0     | :white_check_mark: |
| Edinburgh                    | Europe/London                  | UTC+0     | :white_check_mark: |
| London                       | Europe/London                  | UTC+0     | :white_check_mark: |
| Monrovia                     | Africa/Monrovia                | UTC+0     |                    |
| UTC                          | Etc/UTC                        | UTC+0     |                    |
| Casablanca                   | Africa/Casablanca              | UTC+1     |                    |
| Belgrade                     | Europe/Belgrade                | UTC+1     | :white_check_mark: |
| Bratislava                   | Europe/Bratislava              | UTC+1     | :white_check_mark: |
| Budapest                     | Europe/Budapest                | UTC+1     | :white_check_mark: |
| Ljubljana                    | Europe/Ljubljana               | UTC+1     | :white_check_mark: |
| Prague                       | Europe/Prague                  | UTC+1     | :white_check_mark: |
| Sarajevo                     | Europe/Sarajevo                | UTC+1     | :white_check_mark: |
| Skopje                       | Europe/Skopje                  | UTC+1     | :white_check_mark: |
| Warsaw                       | Europe/Warsaw                  | UTC+1     | :white_check_mark: |
| Zagreb                       | Europe/Zagreb                  | UTC+1     | :white_check_mark: |
| Brussels                     | Europe/Brussels                | UTC+1     | :white_check_mark: |

**Source**: [Enterprise Applications > Workato > Single Sign On > Attributes & Claims > Add a new claim](https://example.com) | UTC+1     | :white_check_mark: |
| Copenhagen                   | Europe/Copenhagen              | UTC+1     | :white_check_mark: |
| Madrid                       | Europe/Madrid                  | UTC+1     | :white_check_mark: |
| Paris                        | Europe/Paris                   | UTC+1     | :white_check_mark: |
| Amsterdam                    | Europe/Amsterdam               | UTC+1     | :white_check_mark: |
| Berlin                       | Europe/Berlin                  | UTC+1     | :white_check_mark: |
| Bern                         | Europe/Zurich                  | UTC+1     | :white_check_mark: |
| Zurich                       | Europe/Zurich                  | UTC+1     | :white_check_mark: |
| Rome                         | Europe/Rome                    | UTC+1     | :white_check_mark: |
| Stockholm                    | Europe/Stockholm               | UTC+1     | :white_check_mark: |
| Vienna                       | Europe/Vienna                  | UTC+1     | :white_check_mark: |
| West Central Africa          | Africa/Algiers                 | UTC+1     |                    |
| Bucharest                    | Europe/Bucharest               | UTC+2     | :white_check_mark: |
| Cairo                        | Africa/Cairo                   | UTC+2     |                    |
| Helsinki                     | Europe/Helsinki                | UTC+2     | :white_check_mark: |
| Kyiv                         | Europe/Kiev                    | UTC+2     | :white_check_mark: |
| Riga                         | Europe/Riga                    | UTC+2     | :white_check_mark: |
| Sofia                        | Europe/Sofia                   | UTC+2     | :white_check_mark: |
| Tallinn                      | Europe/Tallinn                 | UTC+2     | :white_check_mark: |
| Vilnius                      | Europe/Vilnius                 | UTC+2     | :white_check_mark: |
| Athens                       | Europe/Athens                  | UTC+2     | :white_check_mark: |
| Jerusalem                    | Asia/Jerusalem                 | UTC+2     | :white_check_mark: |
| Harare                       | Africa/Harare                  | UTC+2     |                    |
| Pretoria                     | Africa/Johannesburg            | UTC+2     |                    |
| Kaliningrad                  | Europe/Kaliningrad             | UTC+2     |                    |
| Istanbul                     | Europe/Istanbul                | UTC+3     |                    |
| Minsk                        | Europe/Minsk                   | UTC+3     |                    |
| Moscow                       | Europe/Moscow                  | UTC+3     |                    |
| St. Petersburg               | Europe/Moscow                  | UTC+3     |                    |
| Kuwait                       | Asia/Kuwait                    | UTC+3     |                    |
| Riyadh                       | Asia/Riyadh                    | UTC+3     |                    | ```
|
| ナイロビ                      | アフリカ/ナイロビ                 | UTC+3     |                    |
| バグダッド                      | アジア/バグダッド                   | UTC+3     |                    |
| テヘラン                       | アジア/テヘラン                    | UTC+3:30  | :white_check_mark: |
| ヴォルゴグラード                    | ヨーロッパ/ヴォルゴグラード               | UTC+4     |                    |
| サマラ                       | ヨーロッパ/サマラ                  | UTC+4     |                    |
| アブダビ                    | アジア/マスカット                    | UTC+4     |                    |
| マスカット                       | アジア/マスカット                    | UTC+4     |                    |
| バクー                         | アジア/バクー                      | UTC+4     |                    |
| トビリシ                      | アジア/トビリシ                   | UTC+4     |                    |
| エレバン                      | アジア/エレバン                   | UTC+4     |                    |
| カブール                        | アジア/カブール                     | UTC+4:30  | :white_check_mark: |
| エカテリンブルク                 | アジア/エカテリンブルク             | UTC+5     |                    |
| イスラマバード                    | アジア/カラチ                   | UTC+5     |                    |
| カラチ                      | アジア/カラチ                   | UTC+5     |                    |
| タシケント                     | アジア/タシケント                  | UTC+5     |                    |
| スリ・ジャヤワルデネプラ          | アジア/コロンボ                   | UTC+5:30  | :white_check_mark: |
| チェンナイ                      | アジア/コルカタ                   | UTC+5:30  | :white_check_mark: |
| コルカタ                      | アジア/コルカタ                   | UTC+5:30  | :white_check_mark: |
| ムンバイ                       | アジア/コルカタ                   | UTC+5:30  | :white_check_mark: |
| ニューデリー                    | アジア/コルカタ                   | UTC+5:30  | :white_check_mark: |
| カトマンズ                    | アジア/カトマンズ                 | UTC+5:45  | :white_check_mark: |
| アスタナ                       | アジア/ダッカ                     | UTC+6     |                    |
| ダッカ                        | アジア/ダッカ                     | UTC+6     |                    |
| アルマトイ                     | アジア/アルマトイ                    | UTC+6     |                    |
| ウルムチ                       | アジア/ウルムチ                    | UTC+6     |                    |
| ヤンゴン                      | アジア/ヤンゴン                   | UTC+6:30  | :white_check_mark: |
| ノヴォシビルスク                  | アジア/ノヴォシビルスク               | UTC+7     |                    |
| バンコク                      | アジア/バンコク                   | UTC+7     |                    |
| ハノイ                        | アジア/バンコク                   | UTC+7     |                    |
| ジャカルタ                      | アジア/ジャカルタ                   | UTC+7     |                    |
| クラスノヤルスク
```
 | Asia/Krasnoyarsk               | UTC+7     |                    |
| Beijing                      | Asia/Shanghai                  | UTC+8     |                    |
| Chongqing                    | Asia/Chongqing                 | UTC+8     |                    |
| Hong Kong                    | Asia/Hong_Kong                 | UTC+8     |                    |
| Kuala Lumpur                 | Asia/Kuala_Lumpur              | UTC+8     |                    |
| Singapore                    | Asia/Singapore                 | UTC+8     |                    |
| Taipei                       | Asia/Taipei                    | UTC+8     |                    |
| Perth                        | Australia/Perth                | UTC+8     |                    |
| Irkutsk                      | Asia/Irkutsk                   | UTC+8     |                    |
| Ulaanbaatar                  | Asia/Ulaanbaatar               | UTC+8     |                    |
| Seoul                        | Asia/Seoul                     | UTC+9     |                    |
| Osaka                        | Asia/Tokyo                     | UTC+9     |                    |
| Sapporo                      | Asia/Tokyo                     | UTC+9     |                    |
| Tokyo                        | Asia/Tokyo                     | UTC+9     |                    |
| Yakutsk                      | Asia/Yakutsk                   | UTC+9     |                    |
| Darwin                       | Australia/Darwin               | UTC+9:30  |                    |
| Adelaide                     | Australia/Adelaide             | UTC+9:30  | :white_check_mark: |
| Canberra                     | Australia/Melbourne            | UTC+10    | :white_check_mark: |
| Melbourne                    | Australia/Melbourne            | UTC+10    | :white_check_mark: |
| Sydney                       | Australia/Sydney               | UTC+10    | :white_check_mark: |
| Brisbane                     | Australia/Brisbane             | UTC+10    |                    |
| Hobart                       | Australia/Hobart               | UTC+10    | :white_check_mark: |
| Vladivostok                  | Asia/Vladivostok               | UTC+10    |                    |
| Guam                         | Pacific/Guam                   | UTC+10    |                    |
| Port Moresby                 | Pacific/Port_Moresby           | UTC+10    |                    |
| Magadan                      | Asia/Magadan                   | UTC+11    |                    |
| Srednekolymsk                | Asia/Srednekolymsk             | UTC+11    |                    |
| Solomon Is.                 | Pacific/Guadalcanal            | UTC+11    |                    |
| New Caledonia                | Pacific/Noumea                 | UTC+11    |                    |
| Fiji                         | Pacific/Fiji                   | UTC+12    | :white_check_mark: |
| Kamchatka                    | Asia/Kamchatka                 | UTC+12    |                    |

**Source**: [Time Zone List](https://www.timeanddate.com/time/zones/)

**Enterprise Applications > Workato > Single Sign On > Attributes & Claims > Add a new claim** tka                 | UTC+12    |                    |
| Marshall Is.                | Pacific/Majuro                 | UTC+12    |                    |
| Auckland                     | Pacific/Auckland               | UTC+12    | :white_check_mark: |
| Wellington                   | Pacific/Auckland               | UTC+12    | :white_check_mark: |
| Nuku'alofa                   | Pacific/Tongatapu              | UTC+13    |                    |
| Tokelau Is.                 | Pacific/Fakaofo                | UTC+13    |                    |
| Samoa                        | Pacific/Apia                   | UTC+13    |                    |
| Chatham Is.                 | Pacific/Chatham                | UTC+13:45 | :white_check_mark: |

---

## `to_date`

この式は、入力データを日付に変換します。日付はYYYY-MM-DD形式で返されます。

### 構文

<kbd>String</kbd>.to_date(format: <span style="color:#FF0000">format</span>)

- <kbd>String</kbd> - 入力日時または日付を表す文字列。
- <span style="color:#FF0000">format</span> - (オプション) 入力の日付形式を文字列で指定します。指定しない場合、Workatoは入力文字列を自動的に解析します。

### 使用例

| 式                                                      | 結果        |
| ------------------------------------------------------------- | ------------- |
| <kbd>"23-01-2020 10:30 pm"</kbd>.to_date(format: "DD-MM-YYYY") | "2020-01-23"  |
| <kbd>"01-23-2020 10:30 pm"</kbd>.to_date(format: "MM-DD-YYYY") | "2020-01-23"  |
| <kbd>"2020/01/23"</kbd>.to_date(format: "YYYY/MM/DD")         | "2020-01-23"  |

### 動作方法

入力データを日付データ型に変換します。

::: tip 入力データのベストプラクティス
入力データの形式を指定することをおすすめします。形式が指定されていない場合、Workatoは入力文字列を自動的に解析します。

この式が機能するためには、入力文字列が日付に似ている必要があります。
:::

### 関連情報

- [strftime](/formulas/date-formulas.md#strftime): カスタム形式で日時を返します。
- [to_time](/formulas/date-formulas.md#to-time): 文字列をISOタイムスタンプに変換します。

---

## `to_time`

文字列をISOタイムスタンプに変換します。応答はUTCタイムゾーン（+00:00）を使用します。

### 構文

<kbd>String</kbd>.to_time(<span style="color:#FF0000">format</span>)

- <kbd>String</kbd> - 日付または日時を表す文字列。
- <span style="color:#FF0000">format</span> - ユーザー定義の日時の形式を文字列で指定します。

### 使用例

| 式                                               | 結果        |
| ----------------------------------------------------- | ------------- |
| <kbd>"2020-04-02T12:30:30.462659-07:00"</kbd>.to_time | "2020-04-02T19:30:30.462659+00:00"  |
| <kbd>"2020-04-02"</kbd>.to_time                       | "2020-04-02T00:00:00.000000+00:00"  |

### 動作方法

入力文字列を日時データ型に変換します。出力される日時はUTCタイムゾーン（+00:00）に変換されます。 0).

::: tip 時間の自動入力
入力データに時間が含まれていない場合、出力は `00:00:00.000000 +00:00` にデフォルトされます。
:::

### 関連情報

- [strftime](/formulas/date-formulas.md#strftime): カスタム形式で日時を返します。
- [to_date](/formulas/date-formulas.md#to-date): この式は、日付のような入力を日付に変換します。日付はYYYY-MM-DD形式で返されます。

### パラメータ

上記のように、各コード（`%B`、`%e`、`%I`など）は `datetime` の特定の要素を参照します。カンマ（`,`）、スラッシュ（`/`）、コロン（`:`）などの静的テキストや句読点も追加できます。よく使用されるコードの一覧は次の通りです：

| コード            | 意味                                   | 例<br>(2020-06-05T17:13:27.000000-07:00) |
| ---------------- | -------------------------------------- | ---------------------------------------- |
| %Y               | 世紀付きの年                           | 2020                                     |
| %m               | ゼロを付けた月                         | 06                                       |
| %B               | 月の完全な名前                         | 6月                                      |
| %b               | 月の省略名                             | 6月                                      |
| %d               | ゼロを付けた日                         | 05                                       |
| %e               | ゼロを付けない日                       | 5                                        |
| %H               | 時間（24時間制）                       | 17                                       |
| %k               | ゼロを付けない時間（24時間制）         | 17                                       |
| %I (大文字のI)   | 時間（12時間制）                       | 05                                       |
| %l (小文字のL)   | ゼロを付けない時間（12時間制）         | 5                                        |
| %p               | AMまたはPM                             | PM                                       |
| %M               | 時間の分                               | 13                                       |
| %S               | 分の秒                                 | 27                                       |
| %L               | 分のミリ秒                             | 000                                      |
| %z               | UTCからのタイムゾーンオフセット         | -0700                                    |
| %:z              | UTCからのフォーマットされたタイムゾーンオフセット | -07:00                                   |
| %Z               | タイムゾーンの略称                     | UTC                                      |
| %A               | 曜日の完全な名前                       | 金曜日                                   |

完全な一覧にアクセスするには、[Rubyのドキュメント](http://ruby-doc.org/core-2.3.3/Time.html#method-i-strftime)を参照してください。

---

## `to_i`

日時をエポック時間に変換します。エポック時間をUTC (+00:00) で返します。

### 構文

<kbd>Datetime</kbd>.to_i i

- <kbd>Datetime</kbd> - 入力の日時です。

### 使用例

| 式                                               | 結果       |
| ------------------------------------------------- | ---------- |
| today.to_time.to_i 								| 1645660800 |
| now.to_i                     						| 1645714000 |

### 動作

入力の日時を整数に変換し、エポックタイム（秒単位）を返します。出力の日時はUTCタイムゾーン（+00:00）に変換されます。

::: tip エポックタイムと日時の変換

Workatoの式を使用して、時間形式を簡単に変換できます。

### 人間が読める時間をエポックタイムに変換する方法

`to_i` を使用して、日時データピルをエポックタイム（UTC）に変換します。[動作の詳細](#to-i)をご覧ください。


### エポックタイムを人間が読める時間に変換する方法

以下の式を使用して、エポックタイムを人間が読める日時に変換します。

なお、出力はUTCタイムゾーン（+00:00）で表示されます。

`"1970-01-01".to_time + `<kbd>エポックタイム</kbd>`.seconds`

エポックタイムを特定のタイムゾーンに変換する場合は、[in_time_zone](#in-time-zone)で指定する必要があります。

`"1970-01-01".to_time.in_time_zone("US/Pacific") + `<kbd>エポックタイム</kbd>`.seconds`
:::

::: danger データ型が間違っています: undefined method `to_i`
エポックタイムには日時データピルが必要です。日付データピルを使用している場合は、エラーが発生します。

エポックタイムに変換する前に、[to_time](#to-time)を使用して日付を日時に変換してください。
:::

### 関連情報

- [to_time](/formulas/date-formulas.md#to-time): 文字列をISOタイムスタンプに変換します。
- [to_date](/formulas/date-formulas.md#to-date): この式は、日付のような入力を日付に変換します。日付はYYYY-MM-DD形式で返されます。
- [in_time_zone](/formulas/date-formulas.md#in-time-zone): 時間値を別のタイムゾーンに変換します。