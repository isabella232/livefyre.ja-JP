---
description: Livefyre.jsを使用して日付とタイムスタンプをカスタマイズします。
seo-description: Livefyre.jsを使用して日付とタイムスタンプをカスタマイズします。
seo-title: 日付とタイムスタンプのカスタマイズ
solution: Experience Manager
title: 日付とタイムスタンプのカスタマイズ
uuid: 632ea405-56b7-4664-8d2b-0dd0a7611bd8
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# 日付とタイムスタンプのカスタマイズ{#customize-the-date-and-time-stamp}

Livefyre.jsを使用して日付とタイムスタンプをカスタマイズします。

Livefyre Appsには、以下に説明するように日付形式を指定するオプションパラメーターdatetimeFormatが用意されています。

* [用語](#c_date_time_stamp/section_xsk_jn4_xz)
* [形式](#c_date_time_stamp/section_ynx_gn4_xz)
* [記号指定](#c_date_time_stamp/section_inq_2n4_xz)

## 用語 {#section_xsk_jn4_xz}

* **絶対タイムスタンプ** は、正確で具体的な時刻として定義されます（例：2012年1月1日午後12時）。
* **相対タイムスタンプ** は、一般的で精度の低い時間（例：25秒前、14分前、1日前、1年前など）と定義されます。

## 形式 {#section_ynx_gn4_xz}

引数が指定されない場合、datetimeFormatパラメーターは次のデフォルト動作を持ちます。

* 日付の形式：yyyy年MMMM d（2012年1月8日）
* 絶対時間（相対タイムスタンプが絶対タイムスタンプになるまで14日）までの20160分（14日）

datetimeFormatパラメーターは、次の3つの引数型を受け付けます。datetime、formatおよびstring。

```
// Example 1 (Datetime format string)  
var convConfig = { 
   "collectionMeta":"eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJ0aXRsZSI6InBvc3QgMiIsInVybCI6Imh0dHA6XC9cL29yYW5nZXNhcmVncmVhdC5jb21cL3VzZWExcDcwXzEyXC8_cD01IiwidGFncyI6IiIsImNoZWNrc3VtIjoiYjBiYzRkMmVmY2UyZWZkYzZkYTE4NmQ2ZGZhNmVkYzAiLCJhcnRpY2xlSWQiOjV9.XZJTJgwpiFZCQ6dv8vvl91sMbFSJndzZPTHhmtOaImo", 
   "checksum":"b0bc4d2efce2efdc6da186d6dfa6edc", 
   "siteId":"12345", 
   "articleId":5, 
   "el":"comments1", 
   "datetimeFormat": 'MMM d y Ka' 
}; 
var conv = fyre.conv.load(networkConfig, [convConfig]);
```

absoluteFormatまたはminutesUntilAbsoluteTimeを指定するオブジェクトです。 値が —1のminutesUntilAbsoluteTimeは、時間の絶対時間を即時にします。

```
// Example 2 (Object)  
var convConfig = { 
   "collectionMeta":"eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJ0aXRsZSI6InBvc3QgMiIsInVybCI6Imh0dHA6XC9cL29yYW5nZXNhcmVncmVhdC5jb21cL3VzZWExcDcwXzEyXC8_cD01IiwidGFncyI6IiIsImNoZWNrc3VtIjoiYjBiYzRkMmVmY2UyZWZkYzZkYTE4NmQ2ZGZhNmVkYzAiLCJhcnRpY2xlSWQiOjV9.XZJTJgwpiFZCQ6dv8vvl91sMbFSJndzZPTHhmtOaImo", 
   "checksum":"b0bc4d2efce2efdc6da186d6dfa6edc", 
   "siteId":"12345", 
   "articleId":5, 
   "el":"comments1", 
   "datetimeFormat": { 
      minutesUntilAbsoluteTime: 10, 
      absoluteFormat: 'MMM d y Ka' 
   } 
};  
var conv = fyre.conv.load(networkConfig, [convConfig]);
```

Dateオブジェクトを引数として受け取り、表示する日時文字列を返す関数です

```
// Example 3 (Function accepting a Date object, returning a datetime string to display) 
var convConfig = { 
   "collectionMeta":"eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJ0aXRsZSI6InBvc3QgMiIsInVybCI6Imh0dHA6XC9cL29yYW5nZXNhcmVncmVhdC5jb21cL3VzZWExcDcwXzEyXC8_cD01IiwidGFncyI6IiIsImNoZWNrc3VtIjoiYjBiYzRkMmVmY2UyZWZkYzZkYTE4NmQ2ZGZhNmVkYzAiLCJhcnRpY2xlSWQiOjV9.XZJTJgwpiFZCQ6dv8vvl91sMbFSJndzZPTHhmtOaImo", 
   "checksum":"b0bc4d2efce2efdc6da186d6dfa6edc", 
   "siteId":"12345", 
   "articleId":5, 
   "el":"comments1", 
   "datetimeFormat": function(theDateInput) { 
      return +theDateInput; 
   } 
};  
var conv = fyre.conv.load(networkConfig, [convConfig]);
```

## 記号指定 {#section_inq_2n4_xz}

JDK、ICU、CLDRで定義されているパターン仕様に従う日時の書式設定関数。JSでの一般的な使用方法に対しては、若干の変更が加えられています。 詳しくは、 [Google Closure Library Documentationを参照してください](https://developers.google.com/closure/library/docs/overview)。

```
  Symbol Meaning Presentation        Example 
  ------   -------                 ------------        ------- 
  G        era designator          (Text)              AD 
  y#       year                    (Number)            1996 
  Y* year (week of year)     (Number)            1997 
  u* extended year           (Number)            4601 
  M        month in year           (Text & Number)     July & 07 
  d        day in month            (Number)            10 
  h        hour in am/pm (1~12)    (Number)            12 
  H        hour in day (0~23)      (Number)            0 
  m        minute in hour          (Number)            30 
  s        second in minute        (Number)            55 
  S        fractional second       (Number)            978 
  E        day of week             (Text)              Tuesday 
  e* day of week (local 1~7) (Number)            2 
  D* day in year             (Number)            189 
  F* day of week in month    (Number)            2 (2nd Wed in July) 
  w* week in year            (Number)            27 
  W* week in month           (Number)            2 
  a        am/pm marker            (Text)              PM 
  k        hour in day (1~24)      (Number)            24 
  K        hour in am/pm (0~11)    (Number)            0 
  z        time zone               (Text)              Pacific Standard Time 
  Z        time zone (RFC 822)     (Number)            -0800 
  v        time zone (generic)     (Text)              Pacific Time 
  g* Julian day              (Number)            2451334 
  A* milliseconds in day     (Number)            69540000 
  '        escape for text         (Delimiter)         'Date=' 
  ''       single quote            (Literal)           'o''clock'
```

「*」のマークが付いた項目は、まだサポートされていません。

「#」でマークされた項目は、Javaとは異なる動作をします。

パターン文字の数によって形式が決まります。

* **** テキスト：4つ以上のフォームを使用します。 4未満の場合は、短い形式または短い形式を使用します（存在する場合）。 (例：「EEE」は「Monday」を生成し、「EEE」は「Mon」を生成します。)
* **** 番号：最小桁数。 数値が小さいほど、この金額にゼロパディングされます(例：「m」の場合は「6」、「mm」の場合は「06」になります。) 年は特別に扱われる。つまり、「y」の数が2の場合、年は2桁に切り捨てられます。 (例：「yyyy」の場合は「1997」、「yy」の場合は「97」になります。)他のフィールドとは異なり、秒の小数部は右側にゼロで埋め込まれます。
* **** テキストと番号：3回以上はテキストを使用します。 3未満の場合は、numberを使用します。 (例：「M」は「1」、「MM」は「01」、「MMM」は「Jan」、「MMM」は「January」を生成します。)

パターン内の「 [a」。..以外の文字zと] ‘ [A’..’Zは引用符で囲ま] れたテキストとして扱われます。 例えば、「:」、「。」、「,」、「@」などの文字は、一重引用符で囲まれていない場合でも、結果の時間テキストに表示されます。
