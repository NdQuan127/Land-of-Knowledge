---
{"dg-publish":true,"permalink":"/cards/nhap-mon-firefox/"}
---

up:: [[Atlas/Bí thuật MOC\|Bí thuật MOC]]
tags:: #on/bt_chiase 

# Nhập môn Firefox
> Để sử dụng Firefox 1 cách pro là 1 việc rất khổ dâm, thế nên bài hướng dẫn sau có lẽ sẽ giúp anh em đỡ khổ dâm hơn phần nào 💪

## Tối ưu Firefox

> Anh em có thể dùng code sau đây để áp dụng [[+ Encounters/Tất cả tối ưu tốt nhất và an toàn nhất của thread vào Firefox chỉ tốn vài giây\|Tất cả tối ưu tốt nhất và an toàn nhất của thread vào Firefox chỉ tốn vài giây]]
- Đầu tiên anh em hãy chọn cho mình 1 bản mod ngon đã: [[Sources/Các bản mod ngon của Firefox\|Các bản mod ngon của Firefox]]
- [[Cards/uBlock+Auto Tab Discard - Khởi nguồn của sức mạnh!\|uBlock+Auto Tab Discard - Khởi nguồn của sức mạnh!]]
- Có 1 fact là thằng Windows Defender cố tình đì các browser khác để buff bẩn cho Edge và Firefox là 1 trong những thằng bị đì ác nhất. Vậy giải pháp của chúng ta là: [[Sources/Đặt ngoại lệ antivirus để Firefox không bị hãm tốc độ\|Đặt ngoại lệ antivirus để Firefox không bị hãm tốc độ]]
- [[Sources/nglayout.initialpaint.delay khiến Firefox render trang ít đi giảm tổng tiêu thụ CPU\|nglayout.initialpaint.delay khiến Firefox render trang ít đi giảm tổng tiêu thụ CPU]]
- [[Sources/Ép Firefox lưu cache trên RAM mà không cần RAMDisk\|Ép Firefox lưu cache trên RAM mà không cần RAMDisk]]
- [[Sources/Tắt sạch tác vụ chạy nền, chia sẻ trải nghiệm của Firefox (an toàn 1000%)\|Tắt sạch tác vụ chạy nền, chia sẻ trải nghiệm của Firefox (an toàn 1000%)]]
- [[Sources/Tắt OCSP để tăng tốc kết nối tới trang web\|Tắt OCSP để tăng tốc kết nối tới trang web]]
- [Bật Early Hint để tăng tốc tải trang bằng cách tải trước nội dung trang web trước khi cả trang tải xong]
```javaScript
user_pref("network.early-hints.enabled", true);  
user_pref("network.early-hints.preconnect.enabled", true); 
user_pref ("network. Early-hints. Preconnect. Max_connections", 20); 
```
- [[Sources/Bật punycode để miễn nhiễm với tên miền giả mạo\|Bật punycode để miễn nhiễm với tên miền giả mạo]]
- [Tối ưu cuộn mượt]
```javascript
user_pref("apz.overscroll.enabled", true);
user_pref("general.smoothScroll", true);
user_pref("mousewheel.default.delta_multiplier_y", 275);
```
- [[+ Encounters/Tối ưu DNS\|Tối ưu DNS]]
- *updating...*
=> Vậy là sau khi làm theo các thứ trên anh em sẽ được 1 firefox với tốc độ mà chrome gọi bằng bố 🤪
*Đây là 2 video so sánh:*
Firefox: [https://streamable.com/wtoz4k](https://streamable.com/wtoz4k)  
Chrome: [https://streamable.com/huoket](https://streamable.com/huoket)

## Addon bá đạo cho firefox
*updating...*
- [[+ Encounters/Userscript thay vì Addon\|Userscript thay vì Addon]]
- [[+ Encounters/External Application - Kết nối Firefox với ứng dụng ngoài để mở,tải video,playlist bằng MPV,yt-dlp\|External Application - Kết nối Firefox với ứng dụng ngoài để mở,tải video,playlist bằng MPV,yt-dlp]]
- [[Cards/Violentmonkey-Greasymonkey-Tampermonkey\|Violentmonkey-Greasymonkey-Tampermonkey]]
- [[Sources/Sidebery - Quản lý tab dọc với tính tuỳ biến cao\|Sidebery - Quản lý tab dọc với tính tuỳ biến cao]]
- [[Sources/Multi-Threaded Download Manager - Tải đa luồng, bắt link video, tải hàng loạt nói chung là xịn như IDM\|Multi-Threaded Download Manager - Tải đa luồng, bắt link video, tải hàng loạt nói chung là xịn như IDM]] *(outdated)*
- [[Sources/Progressive Web Application - Tạo ứng dụng web như Zalo, Tele, Discord,...\|Progressive Web Application - Tạo ứng dụng web như Zalo, Tele, Discord,...]]
- [[Sources/Search in Sidebar - Search qua sidebar mà ko cần mở tab mới\|Search in Sidebar - Search qua sidebar mà ko cần mở tab mới]]
- [[Sources/Search by Image - Tìm kiếm ảnh, dịch trong ảnh\|Search by Image - Tìm kiếm ảnh, dịch trong ảnh]]
- [[Head Editor - Đổi User - Agent Language, nôm nà là tuỳ ý thay đổi nội dung trang web\|Head Editor - Đổi User - Agent Language, nôm nà là tuỳ ý thay đổi nội dung trang web]]
- [[Cards/ProxySwitchy - Fake IP cực đỉnh, vô Pỏnhub, medium,... ko cần fake vpn\|ProxySwitchy - Fake IP cực đỉnh, vô Pỏnhub, medium,... ko cần fake vpn]]
- [[+ Encounters/Tridactyl - Lướt web bằng bàn phím giống Vimium\|Tridactyl - Lướt web bằng bàn phím giống Vimium]]
- [[+ Encounters/FileCentiPede - Tải đa luồng như IDM, bắt link video và hơn thế\|FileCentiPede - Tải đa luồng như IDM, bắt link video và hơn thế]]
- 