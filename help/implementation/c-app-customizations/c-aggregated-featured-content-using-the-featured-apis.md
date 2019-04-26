---
description: Livefyreには4つの特集APIが用意されています。これにより、入力ネットワーク、サイト、コレクションの最新の50個のコンテンツアイテム、または入力コレクションの上部にあるコンテンツの2つの部分を取得できます。
seo-description: Livefyreには4つの特集APIが用意されています。これにより、入力ネットワーク、サイト、コレクションの最新の50個のコンテンツアイテム、または入力コレクションの上部にあるコンテンツの2つの部分を取得できます。
seo-title: 重点APIを使用した重点的な特集コンテンツ
solution: Experience Manager
title: 重点APIを使用した重点的な特集コンテンツ
uuid: e9c9ff26-37b6-4328- af85- aa550e7ffdfd
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# 重点APIを使用した重点的な特集コンテンツ{#aggregated-featured-content-using-the-featured-apis}

Livefyreには4つの特集APIが用意されています。これにより、入力ネットワーク、サイト、コレクションの最新の50個のコンテンツアイテム、または入力コレクションの上部にあるコンテンツの2つの部分を取得できます。

## 重点（ネットワーク） {#section_cgm_1nw_xz}

入力ネットワークの特集コンテンツ（および発言者）の50人の最新の部分を取得します。（最新の50ではなく、すべてのコンテンツを返すには、ページングを使用します）。

**リソース**

```
GET https://{networkName}.bootstrap.fyre.co/bs3/v3.1/{network}/featured 
```

**応答の例**

```
{ 
   "paging":{ 
      "hasPrev":false, 
      "limit":null 
   }, 
   "data":{ 
      "content":[ 
  
         { 
            "source":19, 
            "collectionId":"115007930", 
            "collection":null, 
            "content":{ 
               "attachments":[ 
                  { 
                     "provider_url":"https://instagram.com", 
                     "title":"Harry Potter and the Goblet of Fire.\n#harrypotter #thegobletoffire #trimagischesturnier #voldemort #liebe #avadakedavra #quidditch #deatheater, 
                     "url":"https://scontent.cdninstagram.com/hphotos-xaf1/t51.2885-15/s640x640/e15/11820456_903218793066632_2018970577_n.jpg", 
                     "type":"photo", 
                     "thumbnail_width":150, 
                     "height":640, 
                     "width":640, 
                     "version":"1.0", 
                     "link":"https://instagram.com/p/6NyBUxyMuK/", 
                     "author_name":"koraliene", 
                     "provider_name":"Instagram", 
                     "thumbnail_url":"https://scontent.cdninstagram.com/hphotos-xaf1/t51.2885-15/s150x150/e15/11820456_903218793066632_2018970577_n.jpg", 
                     "thumbnail_height":150, 
                     "author_url":"https://www.instagram.com/koraliene" 
                  } 
               ], 
               "generator":{ 
                  "id":"instagram.com" 
               }, 
               "bodyHtml":"Harry Potter and the Goblet of Fire.\n#harrypotter #thegobletoffire #trimagischesturnier #voldemort #liebe #avadakedavra #quidditch  #deatheater", 
               "annotations":{ 
                  "featuredmessage":{ 
                     "authorId":"TEMP-58445cd4e57c1e76@sales.fyre.co", 
                     "value":1439236506.0, 
                     "collectionId":"115007930" 
                  } 
               }, 
               "authorId":"1716944657@instagram.com", 
               "parentId":"", 
               "updatedAt":1439236535, 
               "id":"instagram-1048714281602304906_1716944657@instagram.com", 
               "createdAt":1439236506 
            }, 
            "vis":1, 
            "type":0, 
            "event":1439236744110663 
         }, 
         { 
            "source":0, 
            "collectionId":"117213121", 
            "collection":null, 
            "content":{ 
               "attachments":[ 
                  { 
                     "provider_url":"https://www.youtube.com/", 
                     "title":"GoPro: Shotgun Balloon Drop", 
                     "url":"https://www.youtube.com/watch?v=_hYC-ukmlU0", 
                     "type":"video", 
                     "html":"video", 
                     "author_name":"GoPro", 
                     "height":480, 
                     "width":854, 
                     "version":"1.0", 
                     "link":"https://www.youtube.com/watch?v=_hYC-ukmlU0", 
                     "thumbnail_width":480, 
                     "provider_name":"YouTube", 
                     "thumbnail_url":"https://i.ytimg.com/vi/_hYC-ukmlU0/hqdefault.jpg", 
                     "thumbnail_height":360, 
                     "author_url":"https://www.youtube.com/user/GoProCamera" 
                  } 
               ], 
               "generator":{ 
                  "id":"livefyre.com" 
               }, 
               "bodyHtml":"This is awesome https://www.youtube.com/watch?v=_hYC-ukmlU0", 
               "annotations":{ 
                  "featuredmessage":{ 
                     "authorId":"TEMP-2423f811d093a14f@sales.fyre.co", 
                     "value":1428334500.0, 
                     "collectionId":"117213121" 
                  } 
               }, 
               "authorId":"371505-jonkish21@sales.fyre.co", 
               "parentId":"", 
               "updatedAt":1426798902, 
               "id":"284414041", 
               "createdAt":1426798887 
            }, 
            "vis":1, 
            "type":0, 
            "event":1428334501094017 
         } 
      ], 
      "authors":{ 
         "1716944657@instagram.com":{ 
            "displayName":"Karoline", 
            "tags":[ 
  
            ], 
            "profileUrl":"https://www.instagram.com/koraliene", 
            "avatar":"https://igcdn-photos-g-a.akamaihd.net/hphotos-ak-xfa1/t51.2885-19/11377913_116078835392886_1656868764_a.jpg", 
            "type":8, 
            "id":"1716944657@instagram.com" 
         }, 
         "371505-jonkish21@sales.fyre.co":{ 
            "displayName":"JonKish21", 
            "tags":[ 
            ], 
            "profileUrl":"", 
            "avatar":"https://dpstvy7p9whsy.cloudfront.net/a/anon/50.jpg", 
            "type":1, 
            "id":"371505-jonkish21@sales.fyre.co" 
         }, 
      } 
   } 
}
```

## 重点（サイト） {#section_lq5_ymw_xz}

入力サイトの特集コンテンツ（および発言者）の50人を返します。（最新の50ではなく、すべてのコンテンツを返すには、ページングを使用します）。

**リソース**

```
GET https://{networkName}.bootstrap.fyre.co/bs3/v3.1/{network}/{siteId}/featured 
```

**応答の例**

```
{ 
   "paging":{ 
      "hasPrev":false, 
      "limit":null 
   }, 
   "data":{ 
      "content":[ 
         { 
            "source":19, 
            "collectionId":"132677714", 
            "collection":null, 
            "content":{ 
               "attachments":[ 
                  { 
                     "provider_url":"https://instagram.com", 
                     "title":"Take modern technique and improvisation class every Tuesday at 6:30pm in #ParkSlope #Brooklyn. www.donofriodanceco.com/events  #class #moderntechnique #inthestudio", 
                     "url":"https://scontent.cdninstagram.com/hphotos-xaf1/t51.2885-15/s640x640/sh0.08/e35/11820585_1495140967475672_1192251690_n.jpg", 
                     "type":"photo", 
                     "thumbnail_width":150, 
                     "height":640, 
                     "width":640, 
                     "version":"1.0", 
                     "link":"https://instagram.com/p/7qNEiuiIlG/", 
                     "author_name":"donofriodanceco", 
                     "provider_name":"Instagram", 
                     "thumbnail_url":"https://scontent.cdninstagram.com/hphotos-xaf1/t51.2885-15/s150x150/e35/11820585_1495140967475672_1192251690_n.jpg", 
                     "thumbnail_height":150, 
                     "author_url":"https://www.instagram.com/donofriodanceco" 
                  } 
               ], 
               "generator":{ 
                  "id":"instagram.com" 
               }, 
               "bodyHtml":"Take modern technique and improvisation class every Tuesday at 6:30pm in #ParkSlope #Brooklyn. www.donofriodanceco.com/events  #class #moderntechnique #inthestudio", 
               "annotations":{ 
                  "featuredmessage":{ 
                     "authorId":"TEMP-0b93dcdb2472d860@sales.fyre.co", 
                     "value":1442337695.0, 
                     "collectionId":"132677714" 
                  }, 
                  "geocode":{ 
                     "latitude":40.6753387, 
                     "longitude":-73.9783783 
                  } 
               }, 
               "authorId":"497670545@instagram.com", 
               "parentId":"", 
               "updatedAt":1442337710, 
               "id":"instagram-1074728947851757894_497670545@instagram.com", 
               "createdAt":1442337695 
            }, 
            "vis":1, 
            "type":0, 
            "event":1442337838589493 
         }, 
         { 
            "erefs":[ 
               "M2KJJs0fxNKa5ZoxMg+kNqYWTacF76bsUMrJc7VazNlJknYymBP/EbSIe/Zrcgl7GbkbBoty/t7PfncMKTUCZzcIPk/TT9uV5XIXB3l9EZGb2I0588+cMNmL4NMjpiNUwkJY7w==", 
               "u5xVwcUvddADfY2jrhqmgkETi4XzXOomas2646EX4m6k1tEQO0JcNgg5nQ5TKSXMYDG0AbfSf78kPhuKySQojfNiPLt4q+QutVdMam6r1u2EUfLYdNO3ZpB9bep1/4sGedS2Bg==" 
            ], 
            "source":19, 
            "collectionId":"132677714", 
            "collection":null, 
            "content":{ 
               "id":"instagram-987755210109869306_6402294@instagram.com", 
               "createdAt":1431969618, 
               "parentId":"" 
            }, 
            "vis":3, 
            "type":0, 
            "event":1432053769522037 
         } 
      ], 
      "authors":{ 
         "497670545@instagram.com":{ 
            "displayName":"Donofrio Dance Company", 
            "tags":[ 
  
            ], 
            "profileUrl":"https://www.instagram.com/donofriodanceco", 
            "avatar":"https://igcdn-photos-e-a.akamaihd.net/hphotos-ak-xaf1/t51.2885-19/11856814_802209839897652_651365056_a.jpg", 
            "type":8, 
            "id":"497670545@instagram.com" 
         } 
      } 
   } 
}
```

## 重点（コレクション） {#section_kgc_xmw_xz}

入力コレクションの特集コンテンツ（および発言者）の50人の最新の部分を返します。（最新の50ではなく、すべてのコンテンツを返すには、ページングを使用します）。

**リソース**

```
GET https://{networkName}.bootstrap.fyre.co/bs3/v3.1/{network}/{siteId}/{b64articleId}/featured
```

**応答の例**

```
{ 
   "paging":{ 
      "hasPrev":false, 
      "limit":null 
   }, 
   "data":{ 
      "content":[ 
         { 
            "source":19, 
            "collectionId":"132677714", 
            "collection":null, 
            "content":{ 
               "attachments":[ 
                  { 
                     "provider_url":"https://instagram.com", 
                     "title":"just got our cupcakes in, vanilla chocolate chip & double chocolate chip. #vegancupcake #crueltyfree #delicious #parkslope #brooklyn", 
                     "url":"https://scontent.cdninstagram.com/hphotos-xaf1/t51.2885-15/s640x640/sh0.08/e35/11909349_493164437532074_903287131_n.jpg", 
                     "type":"photo", 
                     "thumbnail_width":150, 
                     "height":640, 
                     "width":640, 
                     "version":"1.0", 
                     "link":"https://instagram.com/p/7qL_8gmDN8/", 
                     "author_name":"thevspotrestaurant", 
                     "provider_name":"Instagram", 
                     "thumbnail_url":"https://scontent.cdninstagram.com/hphotos-xfa1/t51.2885-15/s150x150/e35/c6.0.1068.1068/11950556_841625375936809_874759990_n.jpg", 
                     "thumbnail_height":150, 
                     "author_url":"https://www.instagram.com/thevspotrestaurant" 
                  } 
               ], 
               "generator":{ 
                  "id":"instagram.com" 
               }, 
               "bodyHtml":"just got our cupcakes in, vanilla chocolate chip & double chocolate chip. #vegancupcake #crueltyfree #delicious #parkslope #brooklyn", 
               "annotations":{ 
                  "featuredmessage":{ 
                     "authorId":"TEMP-0b93dcdb2472d860@sales.fyre.co", 
                     "value":1442337134.0, 
                     "collectionId":"132677714" 
                  }, 
                  "geocode":{ 
                     "latitude":40.678052687, 
                     "longitude":-73.979415828 
                  } 
               }, 
               "authorId":"414661547@instagram.com", 
               "parentId":"", 
               "updatedAt":1442337155, 
               "id":"instagram-1074724233891296124_414661547@instagram.com", 
               "createdAt":1442337134 
            }, 
            "vis":1, 
            "type":0, 
            "event":1442337845033953 
         }, 
         { 
            "erefs":[ 
               "M2KJJs0fxNKa5ZoxMg+kNqYWTacF76bsUMrJc7VazNlJknYymBP/EbSIe/Zrcgl7GbkbBoty/t7PfncMKTUCZzcIPk/TT9uV5XIXB3l9EZGb2I0588+cMNmL4NMjpiNUwkJY7w==", 
               "u5xVwcUvddADfY2jrhqmgkETi4XzXOomas2646EX4m6k1tEQO0JcNgg5nQ5TKSXMYDG0AbfSf78kPhuKySQojfNiPLt4q+QutVdMam6r1u2EUfLYdNO3ZpB9bep1/4sGedS2Bg==" 
            ], 
            "source":19, 
            "collectionId":"132677714", 
            "collection":null, 
            "content":{ 
               "id":"instagram-987755210109869306_6402294@instagram.com", 
               "createdAt":1431969618, 
               "parentId":"" 
            }, 
            "vis":3, 
            "type":0, 
            "event":1432053769522037 
         } 
      ], 
      "authors":{ 
         "414661547@instagram.com":{ 
            "displayName":"Restaurant/Comedy Club", 
            "tags":[ 
  
            ], 
            "profileUrl":"https://www.instagram.com/thevspotrestaurant", 
            "avatar":"https://igcdn-photos-f-a.akamaihd.net/hphotos-ak-xfa1/t51.2885-19/11375249_171656349833669_472241260_a.jpg", 
            "type":8, 
            "id":"414661547@instagram.com" 
         } 
      } 
   } 
}
```

## 重点（ヘッド） {#section_n4b_lmw_xz}

入力コレクションのコンテンツの直近の2つの部分を返します。

**リソース**

```
GET https://{networkName}.bootstrap.fyre.co/bs3/{network}/{siteId}/{b64articleId}/featured-head.json
```

**応答の例**

```
{ 
   "content":[ 
      { 
         "source":19, 
         "collectionId":"132677714", 
         "collection":null, 
         "content":{ 
            "attachments":[ 
               { 
                  "provider_url":"https://instagram.com", 
                  "title":"Take modern technique and improvisation class every Tuesday at 6:30pm in #ParkSlope #Brooklyn. www.donofriodanceco.com/events  #class #moderntechnique #inthestudio", 
                  "url":"https://scontent.cdninstagram.com/hphotos-xaf1/t51.2885-15/s640x640/sh0.08/e35/11820585_1495140967475672_1192251690_n.jpg", 
                  "type":"photo", 
                  "thumbnail_width":150, 
                  "height":640, 
                  "width":640, 
                  "version":"1.0", 
                  "link":"https://instagram.com/p/7qNEiuiIlG/", 
                  "author_name":"donofriodanceco", 
                  "provider_name":"Instagram", 
                  "thumbnail_url":"https://scontent.cdninstagram.com/hphotos-xaf1/t51.2885-15/s150x150/e35/11820585_1495140967475672_1192251690_n.jpg", 
                  "thumbnail_height":150, 
                  "author_url":"https://www.instagram.com/donofriodanceco" 
               } 
            ], 
            "generator":{ 
               "id":"instagram.com" 
            }, 
            "bodyHtml":"Take modern technique and improvisation class every Tuesday at 6:30pm in #ParkSlope #Brooklyn. We hope to see you there! www.donofriodanceco.com/events  #class #moderntechnique #inthestudio", 
            "annotations":{ 
               "featuredmessage":{ 
                  "authorId":"TEMP-0b93dcdb2472d860@sales.fyre.co", 
                  "value":1442337695.0, 
                  "collectionId":"132677714" 
               }, 
               "geocode":{ 
                  "latitude":40.6753387, 
                  "longitude":-73.9783783 
               } 
            }, 
            "authorId":"497670545@instagram.com", 
            "parentId":"", 
            "updatedAt":1442337710, 
            "id":"instagram-1074728947851757894_497670545@instagram.com", 
            "createdAt":1442337695 
         }, 
         "vis":1, 
         "type":0, 
         "event":1442337838589493 
      }, 
  
      { 
         "erefs":[ 
            "M2KJJs0fxNKa5ZoxMg+kNqYWTacF76bsUMrJc7VazNlJknYymBP/EbSIe/Zrcgl7GbkbBoty/t7PfncMKTUCZzcIPk/TT9uV5XIXB3l9EZGb2I0588+cMNmL4NMjpiNUwkJY7w==", 
            "u5xVwcUvddADfY2jrhqmgkETi4XzXOomas2646EX4m6k1tEQO0JcNgg5nQ5TKSXMYDG0AbfSf78kPhuKySQojfNiPLt4q+QutVdMam6r1u2EUfLYdNO3ZpB9bep1/4sGedS2Bg==" 
         ], 
         "source":19, 
         "collectionId":"132677714", 
         "collection":null, 
         "content":{ 
            "id":"instagram-987755210109869306_6402294@instagram.com", 
            "createdAt":1431969618, 
            "parentId":"" 
         }, 
         "vis":3, 
         "type":0, 
         "event":1432053769522037 
      } 
   ], 
   "isComplete":true, 
   "size":3, 
   "authors":{ 
      "414661547@instagram.com":{ 
         "displayName":"Restaurant/Comedy Club", 
         "tags":[ 
  
         ], 
         "profileUrl":"https://www.instagram.com/thevspotrestaurant", 
         "avatar":"https://igcdn-photos-f-a.akamaihd.net/hphotos-ak-xfa1/t51.2885-19/11375249_171656349833669_472241260_a.jpg", 
         "type":8, 
         "id":"414661547@instagram.com" 
      }, 
      "497670545@instagram.com":{ 
         "displayName":"Donofrio Dance Company", 
         "tags":[ 
  
         ], 
         "profileUrl":"https://www.instagram.com/donofriodanceco", 
         "avatar":"https://igcdn-photos-e-a.akamaihd.net/hphotos-ak-xaf1/t51.2885-19/11856814_802209839897652_651365056_a.jpg", 
         "type":8, 
         "id":"497670545@instagram.com" 
      } 
   } 
}
```

