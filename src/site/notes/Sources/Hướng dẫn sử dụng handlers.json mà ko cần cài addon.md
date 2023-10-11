---
{"dg-publish":true,"permalink":"/sources/huong-dan-su-dung-handlers-json-ma-ko-can-cai-addon/"}
---

up:: [[Sources/Kết nối Firefox với ứng dụng ngoài để mở,tải video,playlist bằng MPV,yt-dlp\|Kết nối Firefox với ứng dụng ngoài để mở,tải video,playlist bằng MPV,yt-dlp]]
tags:: #on/firefox 

# Hướng dẫn sử dụng handlers.json mà ko cần cài addon

## Chỉnh sửa handlers.json Firefox
- Từ Firefox gõ `about:support`
- Open Profile Folder
- Mở file `handlers.json` lên, sẽ thấy đoạn kiểu `"schemes":{{...}, {...}, {...}}`, thêm `, "mpv":{"action":2,"handlers":[{"name":"MPV","path":"D:\\mpv\\mpv.exe"}]` vào cuối cùng của cái đoạn đó, mà sẽ thành như này: `"schemes":{{...}, {...}, {...}, "mpv":{"action":2,"handlers":[{"name":"MPV","path":"D:\\mpv\\mpv.exe"}]}`
- Ví dụ file của mình (nếu muốn có thể lấy file này luôn): `{"defaultHandlersVersion":{},"mimeTypes":{},"schemes":{"tg":{"action":4}, "mpv":{"action":2,"handlers":[{"name":"MPV","path":"D:\\mpv\\mpv.exe"}]}},"isDownloadsImprovementsAlreadyMigrated":true,"isSVGXMLAlreadyMigrated":true}`
- Tắt Firefox
- Save lại rồi khởi động lại Firefox

> **Chú ý: Nếu vị trí của MPV ở chỗ khác thì tự chỉnh nhé.**

> Anh em nếu thấy `handler.json.corrupt` thì nhớ xoá đi để tránh xung đột
## Userscript Handlers

Cập nhập Handlers dành cho MPV, hỗ trợ thêm rất nhiều tính năng khi so sánh với *phiên bản trước đó*, cách sử dụng cũng nhẹ nhàng hơn ![:D](https://statics.voz.tech/styles/next/xenforo/smilies/popo/biggrin.png?v=01 "Big grin    :D") 

- Tính năng:  
	- Kéo thả link qua bên tay phải để mở qua MPV, kéo qua tay trái để mở qua streamlink, kéo xuống dưới để tải với yt-dlp
	- Hỗ trợ thêm streamlink và yt-dlp
	- Nhẹ và đơn giản hơn so với code cũ gấp tỉ lần, rất dễ cho việc phát triển thêm từ phía các bạn chứ không chỉ mình
	- Có thể tùy ý thêm tính năng nếu các bạn muốn, bởi script này hỗ trợ 8 hướng

Video demo: [https://streamable.com/o3sxe1](https://streamable.com/o3sxe1)  
  
**Update:**  
- V1.0: Bản thử nghiệm đầu tiên
- V1.1: Sửa lỗi M3U8 không cho script kéo link
- V1.2: Không cập nhập gì nhiều, thêm sẵn `Hướng` cho chéo lên phải, chéo lên trái, chéo xuống phải, chéo xuống trái và [**hướng dẫn cách phát triển thêm tính năng cho script**](https://voz.vn/t/tong-hop-nhung-addon-chat-cho-firefox-pc-mobile.682181/post-27797344)
- V1.3: Sửa lỗi kèm với làm theo một số khuyến nghị từ Firemonkey (`@include` thay cho `@match` sai chuẩn)
- V1.4: Chuyển code sang chuẩn switch case cho đẹp bởi [@pTalent](https://voz.vn/u/1862337/)
- V1.5: Hỗ trợ tính năng mới (chú ý để có tính năng mới các bạn cập nhập cả `protocol_hook.lua` mới đính kèm):
    - [Chọn nhiều video bằng cách giữ chuột phải 0.4s sau đó mở hàng loạt qua MPV/Streamlink, tải hàng loạt qua YTDL](https://raw.githubusercontent.com/gunir/My/main/ezgif-5-76a8e47ef4.webp)
    - Hỗ trợ Linux, MacOS (sửa lỗi URL bị hỏng của Mac)
    - Không còn phải nhập tay thư mục MPV nữa
    - [Kéo lên để xem playlist dạng stream](https://voz.vn/t/tong-hop-nhung-addon-chat-cho-firefox-pc-mobile.682181/post-27973646)

**Cài đặt:**  
1. Cài đặt tại [**Greasyfork.org**](https://greasyfork.org/en/scripts/475574-handlers-helper)  
2. Tải file `protocol_hook.zip` tại [đây](https://drive.google.com/file/d/1vRP-l7JcWy3_lOc030uNz7DRIMwEDUGd/view?usp=sharing) vào thẳng folder `scripts` của MPV, giải nén `Extract Here`.  *(nếu dùng bản mpv ăn liền thì cũng bỏ qua đoạn này)*
3. Cài userscript EA context menu tại [đây](https://justpaste.it/7twdk) vào Violent Monkey
