---
{"dg-publish":true,"permalink":"/Atlas/Notes/Ideas/Userscript cho Violentmonkey-Greasymonkey-Tampermonkey/"}
---

up:: [[Atlas/Maps/Firefox MOC\|Firefox MOC]]
tags:: #on/bt_chiase  

# Violentmonkey-Greasymonkey-Tampermonkey
Tiện ích giúp nhúng Javascript vào trang web, rất tiện khi muốn chỉnh sửa trang web theo ý mình, loại bỏ rác rưởi tracking và nhiều tính năng khác.  
  
So sánh:  

- Violentmonkey có tính tương thích cao, mã nguồn mở
- Tampermoneky có tính tương thích rất cao, tuy nhiên là **mã nguồn đóng**: [https://github.com/Tampermonkey/tampermonkey/issues/1515](https://github.com/Tampermonkey/tampermonkey/issues/1515)
- Firemonkey là trẻ trâu mới vào làng, rất nhanh và nhẹ nhưng tính tương thích kiểu lúc được lúc không, nên tạm thời cho xuống Thùng Rác
- Greasemonkey là thủy tổ của tất cả, tính tương thích tàm tạm, tính năng đã lỗi thời

# Userscript 

Mục này để chứa những  *Userscript*, lợi ích:  
- Nhẹ hều
- Làm chủ mã nguồn, phát triển thêm nếu muốn
- Rất nhiều addon chỉ đơn giản là Userscript, không đáng phải cài thành addon cho phí tài nguyên Firefox

## Facebook Unseen - Chặn seen trên Facebook
```javaScript
// ==UserScript==
// @name            Facebook Unseen
// @author          noname
// @namespace       http://www.example.url/to/your-web-site/
// @description     Put a good description in here
// @license         Creative Commons Attribution License
// @version            0.1
// @include         http*://facebook.com/*
// @include         http*://*.facebook.com/*
// @include         http*://*.messenger.com/*
// @include         http*://messenger.com/*
// @grant        unsafeWindow
// @run-at           document-start
// @released        2006-04-17
// @updated         2006-04-19
// @compatible      Greasemonkey
// ==/UserScript==

function getCookie(e) {
  const t = `; ${document.cookie}`,
    n = t.split(`; ${e}=`);
  if (2 === n.length) return n.pop().split(";").shift()
}(e => {
  let i = getCookie("c_user"),
    l = true,
    o = {
      fb_unseen: !0,
      fb_typing: !0,
      mess_unseen: !0,
      mess_typing: !0
    };
  e.postMessage({
    type: "get_settings",
    value: "all"
  }, "*"), e.addEventListener("message", function (e) {
    var {
      data: e
    } = e.data ? e : {
      data: {}
    };
    "update_setting" === e.type && (o[e.name] = e.value), "set_settings_all" === e.type && (o = {
      ...e.value
    })
  }, !1), e.WebSocketProxy = new Proxy(e.WebSocket, {
    construct: function (e, t) {
      const n = new e(...t),
        s = e => {},
        a = e => {
          n.removeEventListener("open", s), n.removeEventListener("close", a)
        };
      return n.addEventListener("open", s), n.addEventListener("close", a), n.send = new Proxy(n.send, {
        apply: function (t, n, s) {
          let a = new Uint8Array(s[0]);
          if (!a || a.length < 100 || 1500 < a.length) return t.apply(n, s);
          var r = (new TextDecoder).decode(a);
          if (!((l ? o.mess_typing : o.fb_typing) && r.includes('"type":4') && r.includes('\\"label\\":\\"3\\"') && r.includes("is_typing"))) {
            if ((l ? o.mess_unseen : o.fb_unseen) && r.includes('"type":3') && r.includes('\\"label\\":\\"21\\"') && !r.includes('\\"label\\":\\"46\\"') && r.includes("last_read_watermark_ts")) try {
              r = "", a.map(e => r += String.fromCharCode(e)), regfex = /\\\\\\"thread_id\\\\\\"\:[0-9]+,\\\\\\"last_read/g;
              let e = r.match(regfex);
              return e ? (e.forEach(e => {
                var t = e.match(/[0-9]+/g)[0],
                  t = 15 < t.length ? "1000000000000000" : i;
                r = r.replace(e, `\\\\\\"thread_id\\\\\\":${t},\\\\\\"last_read`)
              }), s[0] = new Uint8Array(r.split("").map(e => e.charCodeAt(0))), t.apply(n, s)) : t.apply(n, s)
            } catch (e) {
              return void t.apply(n, s)
            }
            return t.apply(n, s)
          }
        }
      }), n
    }
  }), i && (e.WebSocket = WebSocketProxy)
})(unsafeWindow);
```


## Recaptcha Solver

>  Vô đây bấm `raw` là cài được vào Monkey:  https://gist.github.com/origamiofficial/2557dd47fb0aaf08e3c298a236bfa14d

## Tổng hợp userscript của  @fioren
[https://greasyfork.org/vi/scripts/438684-pagetual](https://greasyfork.org/vi/scripts/438684-pagetual)  
[https://greasyfork.org/en/scripts/419215-自动无缝翻页](https://greasyfork.org/en/scripts/419215-%E8%87%AA%E5%8A%A8%E6%97%A0%E7%BC%9D%E7%BF%BB%E9%A1%B5)  
[https://github.com/TagoDR/MangaOnlineViewer/](https://github.com/TagoDR/MangaOnlineViewer/)  
[https://github.com/AdguardTeam/AdGuardExtra](https://github.com/AdguardTeam/AdGuardExtra)  
[https://greasyfork.org/en/scripts/387969-twitterᴾˡᵘˢ-view-twitter-origin-images](https://greasyfork.org/en/scripts/387969-twitter%E1%B4%BE%CB%A1%E1%B5%98%CB%A2-view-twitter-origin-images)  
[https://greasyfork.org/en/scripts/443342-telegram-photo-protection-remover](https://greasyfork.org/en/scripts/443342-telegram-photo-protection-remover)  
[https://github.com/AdguardTeam/PopupBlocker](https://github.com/AdguardTeam/PopupBlocker)  
[https://greasyfork.org/en/scripts/406535-instagram-download-button](https://greasyfork.org/en/scripts/406535-instagram-download-button)  
[https://greasyfork.org/en/scripts/438894-timerhooker-english-version](https://greasyfork.org/en/scripts/438894-timerhooker-english-version)  
[https://github.com/AdvMaple/bilibili-subtitle-download-plugin](https://github.com/AdvMaple/bilibili-subtitle-download-plugin)  
[https://github.com/IceWreck/Page-Visibility-User-Script/blob/master/pagevisibilityuserscript.js](https://github.com/IceWreck/Page-Visibility-User-Script/blob/master/pagevisibilityuserscript.js)  
[https://greasyfork.org/vi/scripts/423001-twitter-media-downloader](https://greasyfork.org/vi/scripts/423001-twitter-media-downloader)  
[https://greasyfork.org/en/scripts/381682-html5视频播放器增强脚本](https://greasyfork.org/en/scripts/381682-html5%E8%A7%86%E9%A2%91%E6%92%AD%E6%94%BE%E5%99%A8%E5%A2%9E%E5%BC%BA%E8%84%9A%E6%9C%AC)  
[https://greasyfork.org/en/scripts/16323-youtube-player-controls](https://greasyfork.org/en/scripts/16323-youtube-player-controls)  
[https://github.com/abpvn/abpvn/tree/master/script](https://github.com/abpvn/abpvn/tree/master/script)  
[https://greasyfork.org/en/scripts/24204-picviewer-ce](https://greasyfork.org/en/scripts/24204-picviewer-ce)  
[https://github.com/Neet-Nestor/Telegram-Media-Downloader](https://github.com/Neet-Nestor/Telegram-Media-Downloader)  
[https://greasyfork.org/en/scripts/23772-absolute-enable-right-click-copy](https://greasyfork.org/en/scripts/23772-absolute-enable-right-click-copy)  
[https://greasyfork.org/en/scripts/33005-direct-download-from-google-play](https://greasyfork.org/en/scripts/33005-direct-download-from-google-play)  
[https://github.com/insin/tweak-new-twitter/](https://github.com/insin/tweak-new-twitter/)  
[https://greasyfork.org/en/scripts/421603-magic-userscript-show-site-all-userjs](https://greasyfork.org/en/scripts/421603-magic-userscript-show-site-all-userjs)  
[https://greasyfork.org/en/scripts/436115-return-youtube-dislike](https://greasyfork.org/en/scripts/436115-return-youtube-dislike)  
[https://gist.github.com/origamiofficial/2557dd47fb0aaf08e3c298a236bfa14d](https://gist.github.com/origamiofficial/2557dd47fb0aaf08e3c298a236bfa14d)  
[https://greasyfork.org/vi/scripts/468182-google-colab-auto-reconnect](https://greasyfork.org/vi/scripts/468182-google-colab-auto-reconnect)  
[https://github.com/the1812/Bilibili-Evolved](https://github.com/the1812/Bilibili-Evolved)  
[https://greasyfork.org/en/scripts/8128-youtube-h-264](https://greasyfork.org/en/scripts/8128-youtube-h-264)  
[https://github.com/lelinhtinh/Userscript](https://github.com/lelinhtinh/Userscript)



## Thay đổi kích cỡ font tuỳ ý trên trang muốn chỉnh

Cách sử dụng (được cho cả Android, ấn vào biểu tượng con khỉ):  
- Vào trang web cần chỉnh font
- Chọn `Set TextZoom Auto` và đặt kích cỡ (mặc định 20)

```javaScript 
// ==UserScript==
// @name        TextZoomAuto
// @namespace   TextZoomAuto
// @match       *://*/*
// @grant       GM_getValue
// @grant       GM_setValue
// @grant       GM_addStyle
// @grant       GM_registerMenuCommand
// @version     1.1
// @author      -
// @description 10/4/2023, 5:07:06 PM
// ==/UserScript==

var defaultvalue = 20;
var name = 'TextZoomAuto';
var prefix = "autoinject" + name;
var value = GM_getValue("value" + name + document.domain, defaultvalue);
console.log(value);
var injectedStatus = false;
var hostarray = [];

function inject() {
    //if (window.self !== window.top) return; // Not in frames
    if (injectedStatus !== false) return; // Not if already injected
    GM_addStyle('* {font-size:' + value + 'px!important;}');
    injectedStatus = true;
}

function addHost() {
    hostarray.push(location.hostname);
    GM_setValue(prefix, JSON.stringify(hostarray));
    if (injectedStatus == false) inject;
}

function set() {
    var val = window.prompt("Enter " + name + document.domain + " value", defaultvalue);
    val = parseInt(val);
    if (val == undefined) {
        return false;
    }
    GM_setValue("value" + name + document.domain, val);
}

function plus() {
    var value = GM_getValue("value" + name + document.domain, defaultvalue);
    GM_setValue("value" + name + document.domain, value + 1);
}

function minus() {
    var value = GM_getValue("value" + name + document.domain, defaultvalue);
    GM_setValue("value" + name + document.domain, value - 1);
}

function removeHost() {
    var index = hostarray.indexOf(location.hostname);
    if (index > -1) {
        hostarray.splice(index, 1);
        GM_setValue(prefix, JSON.stringify(hostarray));
    }
}
// This should work in Violentmonkey and Tampermonkey, but unfortunately not Greasemonkey.
try {
    hostarray = JSON.parse(GM_getValue(prefix, "[]"));
    if (typeof (value) == 'number') {
        GM_registerMenuCommand("+", plus);
        GM_registerMenuCommand("-", minus);
    }
    GM_registerMenuCommand("Set TextZoomAuto", set);
    if (hostarray.includes(location.hostname)) {
        inject();
        injectedStatus = true;
        GM_registerMenuCommand("Stop Auto-Injecting TextZoomAuto", removeHost);
    } else {
        GM_registerMenuCommand("Inject TextZoomAuto", inject);
        GM_registerMenuCommand("Auto-Inject on " + location.hostname, addHost);
    }
} catch (err) {
    console.log("Error adding Inject menu items: " + name);
    console.log(err);
}
```


## Font Facebook - Roboto
```javaScript
// ==UserScript==
// @name          Font facebook
// @include       *messenger.com*
// @include       *facebook.com*
// @version       1.0
// ==/UserScript==

(function() {var css = ["/* cyrillic-ext */",
"@font-face {",
"  font-family: 'Roboto';",
"  font-style: normal;",
"  font-weight: 400;",
"  font-display: swap;",
"  src: url(https://fonts.gstatic.com/s/roboto/v30/KFOmCnqEu92Fr1Mu72xKOzY.woff2) format('woff2');",
"  unicode-range: U+0460-052F, U+1C80-1C88, U+20B4, U+2DE0-2DFF, U+A640-A69F, U+FE2E-FE2F;",
"}",
"/* cyrillic */",
"@font-face {",
"  font-family: 'Roboto';",
"  font-style: normal;",
"  font-weight: 400;",
"  font-display: swap;",
"  src: url(https://fonts.gstatic.com/s/roboto/v30/KFOmCnqEu92Fr1Mu5mxKOzY.woff2) format('woff2');",
"  unicode-range: U+0301, U+0400-045F, U+0490-0491, U+04B0-04B1, U+2116;",
"}",
"/* greek-ext */",
"@font-face {",
"  font-family: 'Roboto';",
"  font-style: normal;",
"  font-weight: 400;",
"  font-display: swap;",
"  src: url(https://fonts.gstatic.com/s/roboto/v30/KFOmCnqEu92Fr1Mu7mxKOzY.woff2) format('woff2');",
"  unicode-range: U+1F00-1FFF;",
"}",
"/* greek */",
"@font-face {",
"  font-family: 'Roboto';",
"  font-style: normal;",
"  font-weight: 400;",
"  font-display: swap;",
"  src: url(https://fonts.gstatic.com/s/roboto/v30/KFOmCnqEu92Fr1Mu4WxKOzY.woff2) format('woff2');",
"  unicode-range: U+0370-03FF;",
"}",
"/* vietnamese */",
"@font-face {",
"  font-family: 'Roboto';",
"  font-style: normal;",
"  font-weight: 400;",
"  font-display: swap;",
"  src: url(https://fonts.gstatic.com/s/roboto/v30/KFOmCnqEu92Fr1Mu7WxKOzY.woff2) format('woff2');",
"  unicode-range: U+0102-0103, U+0110-0111, U+0128-0129, U+0168-0169, U+01A0-01A1, U+01AF-01B0, U+1EA0-1EF9, U+20AB;",
"}",
"/* latin-ext */",
"@font-face {",
"  font-family: 'Roboto';",
"  font-style: normal;",
"  font-weight: 400;",
"  font-display: swap;",
"  src: url(https://fonts.gstatic.com/s/roboto/v30/KFOmCnqEu92Fr1Mu7GxKOzY.woff2) format('woff2');",
"  unicode-range: U+0100-024F, U+0259, U+1E00-1EFF, U+2020, U+20A0-20AB, U+20AD-20CF, U+2113, U+2C60-2C7F, U+A720-A7FF;",
"}",
"/* latin */",
"@font-face {",
"  font-family: 'Roboto';",
"  font-style: normal;",
"  font-weight: 400;",
"  font-display: swap;",
"  src: url(https://fonts.gstatic.com/s/roboto/v30/KFOmCnqEu92Fr1Mu4mxK.woff2) format('woff2');",
"  unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+2000-206F, U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD;",
"}",
"",
"body, button, input, label, select, td, textarea{",
"    font-family: 'Roboto', sans-serif !important;",
"}"
].join("\n");
if (typeof GM_addStyle != 'undefined') {
 GM_addStyle(css);
 } else if (typeof PRO_addStyle != 'undefined') {
 PRO_addStyle(css);
 } else if (typeof addStyle != 'undefined') {
 addStyle(css);
 } else {
 var node = document.createElement('style');
 node.type = 'text/css';
 node.appendChild(document.createTextNode(css));
 var heads = document.getElementsByTagName('head');
 if (heads.length > 0) { heads[0].appendChild(node);
 } else {
 // no head yet, stick it whereever
 document.documentElement.appendChild(node);
 }
}})();
```