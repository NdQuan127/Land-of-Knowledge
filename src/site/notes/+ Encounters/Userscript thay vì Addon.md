---
{"dg-publish":true,"permalink":"/encounters/userscript-thay-vi-addon/"}
---

up:: [[Cards/Firefox MOC\|Firefox MOC]]
tags:: #on/bt_chiase 

# Userscript thay vì Addon
Mục này để chứa những addon đã *BỊ biến thành Userscript, lợi ích:*  
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

## Cách sử dụng monkey để nhúng style thay vì tốn 1 addon Stylus

```javaScript
// ==UserScript==
// @name        Stylus Stylish
// @namespace   Stylus Stylish Userscript - Violentmonkey Scripts
// @include       *://*/*
// @grant       GM_addStyle
// @version     1.0
// @run-at      document-start
// @author      -
// @description -
// ==/UserScript==

GM_addStyle(`

/* Nhồi code CSS vào đây */

`)
```

## Recaptcha Solver
Vô đây bấm `raw` là cài được vào Monkey:  https://gist.github.com/origamiofficial/2557dd47fb0aaf08e3c298a236bfa14d
