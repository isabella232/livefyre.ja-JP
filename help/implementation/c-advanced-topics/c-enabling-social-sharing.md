---
description: ユーザーがコンテンツを様々なソーシャルネットワークに共有できるようにする資格情報を設定します。
seo-description: ユーザーがコンテンツを様々なソーシャルネットワークに共有できるようにする資格情報を設定します。
seo-title: ソーシャルシェアを有効にする
solution: Experience Manager
title: ソーシャルシェアを有効にする
uuid: f584a0ae-46c7-48c1- aea4-36da9f1e259b
translation-type: tm+mt
source-git-commit: d77b633b9892e3ea4aaec860317887f1fdf66830

---


# ソーシャルシェアを有効にする {#enabling-social-sharing}

ユーザーがコンテンツを様々なソーシャルネットワークに共有できるようにする資格情報を設定します。

ソーシャルメディアサイト全体でコンテンツを共有できるようにするには、Livefyreのソーシャルシェア機能を実装し、これらのサイトに適切な認証を提供するOAuthシステムを作成します。このシステムでは、ソーシャルメディアを通じてコンテンツを共有することを選択すると、Livefyreがユーザーに代わって動作します。

>[!NOTE]
>
>異なるプロバイダーのOAuth要件が異なります。OAuthの実装に関連する情報を入手するには、プロバイダにご相談ください。

## 必須のソーシャル資格情報 {#section_gff_cjm_b1b}

カスタムユーザーIDシステムを使用する場合、ユーザーがLivefyreアプリからTwitter、FacebookまたはLinkedInと共有できるようにするには、ソーシャル資格情報を提供する必要があります。

>[!NOTE]
>
>Janrain Engingを使用しているお客様は、自社のエンゲージメントドメインと&quot;APIキー」のみを提供する必要があります。

管理コンソールの統合設定パネルを使用して、次のソーシャル資格情報を入力または更新します。

### 必須資格情報:

* **Facebook** クライアントIDクライアントシークレットOAuthプロキシリダイレクト
* **LinkedIn** APIキーAPIシークレット
* **Twitter** アクセストークンアクセストークンシークレットAPIキーAPIシークレット

## Twitter {#section_qp5_1yl_b1b}

Twitterの資格情報は、Twitter App Dashboardから利用できます。これらの資格情報を見つけるには:

* [Twitterのアプリ開発ページ](https://dev.twitter.com/apps) をアプリ所有者として開き、アプリを見つけて、タイトルをクリックします。
* 「アクセストークン」まで下にスクロールし、「アクセストークン」および「アクセストークンシークレット」から値を取得します。

次のように指定する必要があります。

* Twitterアプリの「コールバックURL&quot;フィールドに値を入力します。このフィールドは単純なプレースホルダーにすることができますが、空白のままにすることはできません。
* アプリケーションの種類を読み取りおよび ******書き込み** アクセスの両方に設定します。
* Twitter AppのWebサイトURLがLivefyre Coreアプリと同じホストドメインにあることを確認します。

>[!NOTE]
>
>Twitterコンテンツを表示するすべてのアプリは、表示要件に従うために必要です。詳しくは [、Twitterの表示ガイドライン](https://dev.twitter.com/terms/display-requirements) を参照してください。

## LinkedIn {#section_lfz_zxl_b1b}

LinkedIn資格情報は、LinkedInアプリケーションのAPIキーの&quot;OAuthキー」セクションから利用できます。

* LinkedInの開発者ページ [https://developer.linkedin.com/からアカウントにサインイン](https://developer.linkedin.com/)します。
* 右上の名前にマウスポインターを置き、ドロップダウンメニューから&quot;APIキー」を選択します。
* アプリケーションのタイトルをクリックします。
* &quot;OAuthキー」セクションからAPIキーおよびシークレットキーの値を取得します

## Facebook {#section_zyb_gpl_b1b}

Facebook資格情報は、開発者用アプリページから入手できます。

* [Facebookの開発者アプリページをアプリの所有者](https://developers.facebook.com/apps) として開き、アプリを見つけて、タイトルをクリックします。
* アプリIDとアプリシークレットの値を取得します。アプリシークレットの場合は、「表示」ボタンをクリックして表示する必要があります。

Facebookへの共有には、Facebookリクエストを行うためのリダイレクトページを設定し、 [Facebookに必要なドメインプラクティスに従っている必要](https://developers.facebook.com/docs/reference/dialogs/oauth/)があります。ページをドメイン上でホストする必要があるので、Facebookは、そのリクエストが正当なソースから来たことを確認できるようにします。

### Facebookリダイレクト

ホストされているページには次のコードが含まれている必要があります。

### ルビ

これは、RubyとRailを使用してFacebook OAuthリダイレクトを行う例です。

```ruby
require "base64" 
  
class Controller < ActionController::Base 
   def base64url_decode(str) 
      str.gsub! '-_', '+/' 
      Base64.decode64(str.ljust(str.length+str.length%4, '=')) 
   end 
  
   def index 
      lfoauth = params[:lfoauth] 
      if not lfoauth 
         render :status => :forbidden, :text => 'Missing lfoauth.' 
      end 
  
      redirect = base64url_decode lfoauth 
  
      match = /^(http:\/\/|https:\/\/)?([^\/?]+)/i.match(redirect) 
      host = match[2] 
  
         if not host.include? 'fyre.co' 
      render :status => :forbidden, :text => 'Invalid host.' 
         end 
  
         sep = (redirect.include? '?') ? '&' : '?' 
      params.delete :lfoauth 
  
         rdir = redirect + sep + params.to_query 
      redirect_to rdir 
   end 
end
```

### Python

これは、Facebook OAuthリダイレクトを行うPythonおよびDjangoを使用する例です。

```python
import base64, re 
from django.views.decorators.http import require_GET 
from django.http.response import HttpResponseRedirect, HttpResponseBadRequest 
  
def base64url_decode(st): 
    return base64.b64decode(re.sub("-_","+/", st).ljust(len(st)+len(st)%4, '=')) 
  
@require_GET 
def handle_lfoauth(request): 
    lfoauth = request.GET.get('lfoauth', None) 
    import pdb; pdb.set_trace() 
    if not lfoauth: 
        return HttpResponseBadRequest('Missing lfoauth.') 
     
    redirect = base64url_decode(lfoauth) 
     
    match = re.match(r"^(http:\/\/|https:\/\/)?([^\/?]+)", redirect, re.IGNORECASE) 
    host = match.group(2) 
     
    # validate the destination to secure this proxy 
    if not 'fyre.co' in host: 
        return HttpResponseBadRequest('Invalid host.') 
     
    # if params were included in the uri already, append with &, otherwise ? 
    sep = '&' if '?' in redirect else '?' 
     
    # remove lfoauth from query param 
    dict_ = request.GET.copy() 
    dict_.pop('lfoauth') 
  
    # attach remaining param to redirect 
    rdir = redirect + sep + dict_.urlencode() 
  
    # this does the actual redirection 
    return HttpResponseRedirect(rdir)
```

### NodeJS

これは、NodeJSおよびTort/Expressを使用してFacebook OAuthリダイレクトを行う例です。

```nodejs
/* 
 * 
 */ 
var S = require('string'), 
     querystring = require('querystring'); 
  
var base64UrlDecode = function(str) { 
     var temp = S(str.replace('-_', '+/')).padRight(str.length+(str.length%4), '=').s 
     return new Buffer(temp, 'base64').toString('utf8'); 
} 
  
module.exports = { 
  index: function(req, res) { 
     var lfoauth = req.param('lfoauth'); 
  
     if (typeof lfoauth === 'undefined') { 
        res.send(400, 'Missing lfoauth.'); 
     } 
  
     var redirect = base64UrlDecode(lfoauth); 
  
     var match = redirect.match(/^(http:\/\/|https:\/\/)?([^\/?]+)/i); 
     var host = match[2] 
  
     if (host.indexOf('fyre.co') <= -1) { 
        res.send(400, 'Invalid host.'); 
     } 
  
     var sep = redirect.indexOf('?') > -1 ? '&' : '?'; 
  
     delete req.query['lfoauth']; 
     var rdir = redirect + sep + querystring.stringify(req.query); 
  
     res.redirect(rdir); 
  }, 
  
  _config: {} 
};
```

### Java

これは、JavaおよびSpringコントローラーを使用してFacebook OAuthリダイレクトを実行する例です。

```java
/* 
 *  
 */ 
import java.util.Collection; 
import java.util.HashMap; 
import java.util.Map; 
import java.util.regex.Matcher; 
import java.util.regex.Pattern; 
  
import org.apache.commons.codec.binary.Base64; 
import org.apache.commons.lang.StringUtils; 
import org.jboss.resteasy.spi.BadRequestException; 
import org.springframework.stereotype.Controller; 
import org.springframework.web.bind.annotation.RequestMapping; 
import org.springframework.web.bind.annotation.RequestParam; 
import org.springframework.web.servlet.View; 
import org.springframework.web.servlet.view.RedirectView; 
  
@Controller 
public class RedirectController { 
    @RequestMapping("/fbredirect") 
    public View facebook(@RequestParam Map<string,object> allRequestParams) { 
        if (!allRequestParams.containsKey("lfoauth")) { 
            throw new BadRequestException("Missing lfoauth."); 
        } 
             
        String redirect = base64UrlDecode((String) allRequestParams.get("lfoauth")); 
  
        Pattern p = Pattern.compile("^(http:\\/\\/|https:\\/\\/)?([^\\/?]+)", Pattern.CASE_INSENSITIVE); 
        Matcher m = p.matcher(redirect); 
        if (!m.find() || !m.group(2).contains("fyre.co")) { 
            throw new BadRequestException("Invalid host."); 
        } 
         
        Map<string, object=""> params = new HashMap<string, object="">(allRequestParams); 
        params.remove("lfoauth"); 
        String rdir = redirect + (redirect.contains("?") ? '&' : '?') + mapToQueryString(params); 
         
        return new RedirectView(rdir); 
    } 
     
    private String base64UrlDecode(String str) { 
        return new String(Base64.decodeBase64(StringUtils.rightPad(str.replaceAll("-_", "+/"), str.length()+(str.length()%4), '='))); 
    } 
     
    private String mapToQueryString(Map<string, object=""> map) { 
        String queryparam = ""; 
        for (String key : map.keySet()) { 
            if (map.get(key) instanceof Collection) { 
                for (Object item : (Collection) map.get(key)) { 
                    queryparam = queryparam.concat(String.format("%1$s=%2$s&", key, item.toString())); 
                } 
            } else { 
                queryparam = queryparam.concat(String.format("%1$s=%2$s&", key, map.get(key).toString())); 
            } 
        } 
        return StringUtils.removeEnd(queryparam, "&"); 
    } 
}
```

### PHP

```php
<?php 
/* 
Purpose: Provide a landing page for the last step of successful oAuth 
         that is on the correct (Facebook approved) domain. 
  
Location: This file should be hosted on the same domain as your  
          Facebook App's "site url". 
  
Input Parameters:  
    - (GET) lfoauth: This should be a url-safe base64-encoded URL that  
      is the "real" final redirection URL. Livefyre sets this. 
  
      For testing purposes, this can be set to a url-safe base64-encoded  
      URL of your choosing, but the domain name must end in .fyre.co in  
      order to be considered valid. 
  
    - (GET) [all other parameters]: Any other parameters should simply  
      be passed thru on the redirection URL. If the decoded URL from "lfoauth"  
      includes querystring parameters, then the additional parameters included  
      with the initial request should be appended with "&..." 
  
Output: The response should indicate that the browser redirect (302) to the  
        "real" URL which is encoded in the "lfoauth" parameter. 
  
*/ 
  
function base64url_decode($data) { 
  return base64_decode(str_pad(strtr($data, '-_', '+/'), strlen($data) % 4, '=', STR_PAD_RIGHT)); 
} 
  
if (isset($_GET['lfoauth'])) { 
    // Warning: If implemented with non-PHP, b64 may fail because we have  
    // stripped padding (trailing ='s), to comply with Facebook parameters.   
    // The decode needs to be non-strict in this sense. 
  
    $rdir = base64url_decode($_GET['lfoauth']); 
  
    // validate the destination to secure this proxy 
    preg_match("/^(https?:\/\/)?([^\/?]+)/i", $rdir, $domain_only);    
    $host = $domain_only[2]; 
    if (!strstr($host,'fyre.co')) { 
        echo "Error - this redirection is not allowed! ".$host; 
        exit; 
    } 
  
    // if params were included in the uri already, append with &, otherwise ? 
    $sep = strstr($rdir,'?') ? '&' : '?'; 
  
    // don't include this in the params we add to the redirect url 
    unset($_GET['lfoauth']); 
  
    // assemble a new querystring from the remaining inbound GET params 
    $rdir = $rdir.$sep.http_build_query($_GET); 
  
    // this does the actual redirection, PHP's implementation is weird 
    header('Location: '.$rdir); 
} 
?>
```

## 「投稿」プロバイダーの設定 {#section_rdk_dpl_b1b}

デフォルトでは、Facebook、LinkedInおよびTwitterの「投稿先」ボタンがLivefyreコアアプリケーションに表示されます。postToButtonsパラメーターを使用して、Livefyreアプリケーションを埋め込むときに表示するプロバイダーを設定します。

```
var convConfig = {}; // Ignoring other options for this example 
convConfig.postToButtons = ['tw', 'fb', 'li']; // Or any subset of these 
fyre.conv.load(networkConfig, [convConfig], function() {}); 
```

`postToButtons` は、次のオプションのサブセットを持つ配列です。

* tw:Twitter
* fb:Facebook
* li:LinkedIn
