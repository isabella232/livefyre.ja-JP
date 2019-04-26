---
description: Livefyre. jsを使用して、日付およびタイムスタンプをカスタマイズします。
seo-description: Livefyre. jsを使用して、日付およびタイムスタンプをカスタマイズします。
seo-title: 日付と時間のスタンプのカスタマイズ
solution: Experience Manager
title: 日付と時間のスタンプのカスタマイズ
uuid: 632ea405-56b7-4664-8d2b-0dd0a7611bd8
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# 日付と時間のスタンプのカスタマイズ{#customize-the-date-and-time-stamp}

Livefyre. jsを使用して、日付およびタイムスタンプをカスタマイズします。

Livefyreアプリでは、以下に説明するように、"dateTimeFormat"オプションを指定して日付形式を指定します。

* [用語](#c_date_time_stamp/section_xsk_jn4_xz)
* [フォーマット](#c_date_time_stamp/section_ynx_gn4_xz)
* [シンボルの指定](#c_date_time_stamp/section_inq_2n4_xz)

## 用語 {#section_xsk_jn4_xz}

* **絶対タイムスタンプ** は、正確で特定の時刻として定義されます（例:2012年1月1日、2012年1月1日）
* **相対タイムスタンプ** は、一般的および精度の低い時刻として定義されています（例:25秒前、14分前、1日前、1年前など）。

## フォーマット {#section_ynx_gn4_xz}

引数が指定されていない場合、DateTimeFormatパラメーターには次のデフォルトの動作があります。

* 日付形式:MMMM d yyyy（2012年1月8日）
* 20160分（14日）（相対タイムスタンプが絶対タイムスタンプになるまで14日）

dateTimeFormatパラメーターでは、次の3つの引数タイプを使用できます。datetime、formatおよびstring。

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

AbsoluteFormatおよびminuteUntilabtSolteTimeを指定するオブジェクトです。値-1のminuteUntilableTimeは、時間を絶対時間にします。

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

引数としてDateオブジェクトを受け取り、表示するdateTime文字列を返す関数

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

## シンボルの指定 {#section_inq_2n4_xz}

JDK、CUCおよびCLDRで定義されているパターン仕様の後の日付形式関数。JSで一般的な使用方法を若干変更します。詳しくは [、Google Closure Libraryドキュメント](https://developers.google.com/closure/library/docs/overview)を参照してください。

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

"*"のマークが付いている項目はまだサポートされていません。

"#"のマークが付いている項目は、Javaとは異なります。

パターンレターの数によって形式が決まります。

* **テキスト:** 4つ以上の場合は、フルフォームを使用します。4より小さい場合は、短い形式または省略形のフォームが存在します。（例:"EEEE"は「月曜」を生成し、"EEE"は"Mon"を生成します。
* **数値:** 小数点以上の桁数。この金額には、短い数値を入力します（例:"m"が"6"を生成する場合、"mm"は"06"を生成します。年は特別に処理されます。つまり、"y"の数が2の場合、年は2桁に切り捨てられます。（例:"yyyy"が"1997"を生成する場合、"yy"は"97"を生成します。他のフィールドとは異なり、小数部はゼロで埋められます。
* **テキスト番号:** 3以上の場合は、テキストを使用します。3未満の数値。（例:"M"は"1"、"MM"は"01"、"MMM"は"Jan"、"MMMM"は"January"を生成します。

"a"の [範囲にないパターンの文字。'zと] "A [」.'Zは] 引用符で囲まれたテキストとして扱われます。例えば、':などの文字。'，'.「，」、"#"および"@"は、結果の時間テキストには一重引用符で囲まれずに表示されます。
