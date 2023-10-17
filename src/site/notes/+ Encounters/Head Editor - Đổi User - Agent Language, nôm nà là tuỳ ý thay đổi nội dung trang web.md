---
{"dg-publish":true,"permalink":"/encounters/head-editor-doi-user-agent-language-nom-na-la-tuy-y-thay-doi-noi-dung-trang-web/"}
---

up:: [[Atlas/Firefox MOC\|Firefox MOC]]
tags:: #on/bt_chiase 

# Head Editor - Đổi User - Agent Language, nôm na là tuỳ ý thay đổi nội dung trang web

- **Addon cực mạnh giúp phá và sửa trang web, tính năng:**  
	- Thêm/xóa/sửa header kiểu User-Agent, Referer.. từ đó ép các trang web dùng bản Mobile hay hiển thị theo ý thích, vượt giới hạn trình duyệt kiểu các trang chỉ cho Chrome/Edge vào
	- Thêm/xóa/sửa NỘI DUNG WEB (nâng cao) giúp chặn những loại quảng cáo, anti-adblock khó nhằn nhất

## Cách ép Youtube Mobile chạy trên Firefox

![Pasted image 20231011202144.png|undefined](/img/user/Extras/Images/Pasted%20image%2020231011202144.png)
> UA: `Mozilla/5.0 (Android 12; Mobile; rv:109.0) Gecko/113.0 Firefox/113.0`

## Disable Hovering to play of Youtube

Youtube có 1 cái tính năng giời ơi là "Hovering to Play" (di chuột lên trên thumbnail để chạy) ở trang Home, Subscription, Search và mấy chỗ này sẽ không có `a.ytd-thumbnail` để đổi link. Cái thanh gợi ý bên tay phải lúc xem video trên trình duyệt thì vẫn hoạt động.

Giải pháp là: Dùng Header Editor thêm Set-Cookie vào Response Header để trình duyệt tự lưu cookie.
```javascript
for (const a in val) {
    if (val[a].name.toLowerCase() === 'set-cookie') {
        val[a].value+='\nPREF=f7=1';
    }
}
```

![Pasted image 20231011202745.png|undefined](/img/user/Extras/Images/Pasted%20image%2020231011202745.png)