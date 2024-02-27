---
{"dg-publish":true,"permalink":"/Atlas/Notes/Ideas/Userscript cho Violentmonkey-Greasymonkey-Tampermonkey/","tags":["on/bt_chiase"]}
---

# Violentmonkey-Greasymonkey-Tampermonkey
Tiện ích giúp nhúng Javascript vào trang web, rất tiện khi muốn chỉnh sửa trang web theo ý mình, loại bỏ rác rưởi tracking và nhiều tính năng khác.  

So sánh:  
- Violentmonkey có tính tương thích cao, mã nguồn mở
- Tampermoneky có tính tương thích rất cao, tuy nhiên là [**mã nguồn đóng**](https://github.com/Tampermonkey/tampermonkey/issues/1515): 
- Firemonkey là trẻ trâu mới vào làng, rất nhanh và nhẹ nhưng tính tương thích kiểu lúc được lúc không, nên tạm thời cho xuống Thùng Rác
- Greasemonkey là thủy tổ của tất cả, tính tương thích tàm tạm, tính năng đã lỗi thời

> **Lưu ý:** Tampermonkey không tương thích với nhiều script nếu dùng bị lỗi thì nên chuyển sang dùng Violentmonkey
# Userscript 

Mục này để chứa những  *Userscript*, lợi ích:  
- Nhẹ hều
- Làm chủ mã nguồn, phát triển thêm nếu muốn
- Rất nhiều addon chỉ đơn giản là Userscript, không đáng phải cài thành addon cho phí tài nguyên Firefox

>[!Orbit]
>Mod @Fioren bên voz đã tạo 1 repository tự động tải và mã hóa các userscript trên bằng [Google Closure Compiler](https://github.com/google/closure-compiler) để giảm dung lượng userscript nhằm giảm ram, cpu khi lướt web các userscript trên. Link [đây](https://github.com/FiorenMas/Userscripts)
### Tiện ích lướt web
[Pagetual](https://greasyfork.org/vi/scripts/438684-pagetual), [AutoPager](https://greasyfork.org/zh-CN/scripts/419215-%E8%87%AA%E5%8A%A8%E6%97%A0%E7%BC%9D%E7%BF%BB%E9%A1%B5), [Super-preloader](https://github.com/machsix/Super-preloader): Cho phép cuộn trang liên tục không cần nhấn next trang
[Web Access Accelerator](https://greasyfork.org/en/scripts/455853-%E7%BD%91%E9%A1%B5%E8%AE%BF%E9%97%AE%E5%8A%A0%E9%80%9F%E5%99%A8): Tải trước tất cả các link trong trang , tăng tốc load web 
[InstantPage Super Lite](https://greasyfork.org/en/scripts/483622-instantpage-super-lite): Tải trước link chuẩn bị nhấn, nhẹ hơn thằng trên
[Selection and Copying Restorer (Universal)](https://greasyfork.org/en/scripts/427575-selection-and-copying-restorer-universal): Mở khóa web chặn nhấn chuột phải, chống copy  
[TimerHooker](https://greasyfork.org/en/scripts/372673-%E8%AE%A1%E6%97%B6%E5%99%A8%E6%8E%8C%E6%8E%A7%E8%80%85-%E8%A7%86%E9%A2%91%E5%B9%BF%E5%91%8A%E8%B7%B3%E8%BF%87-%E8%A7%86%E9%A2%91%E5%B9%BF%E5%91%8A%E5%8A%A0%E9%80%9F%E5%99%A8): Tăng tốc thời gian đếm ngược các trang yêu cầu chờ  
[PreventPageVisibilityAuto](https://greasyfork.org/en/scripts/479726-preventpagevisibilityauto): Ngăn chặn việc bị phát hiện khi đổi sang tab khác.  
[Smoothscroll](https://greasyfork.org/en/scripts/7018-smoothscroll): Cuộn mượt dành cho chrome  -video) Xem video max khung cửa sổ trình duyệt  
[Reject serviceWorker Auto](https://greasyfork.org/en/scripts/482724-reject-serviceworker-auto): Chặn website cài service worker  
[PageExpand](https://greasyfork.org/en/scripts/6294-pageexpand): Tải tài nguyên của 1 web  
[Font Rendering (Customized)](https://greasyfork.org/en/scripts/416688-%E5%AD%97%E4%BD%93%E6%B8%B2%E6%9F%93-%E8%87%AA%E7%94%A8%E8%84%9A%E6%9C%AC): Font đẹp hơn trên chrome  
[Visited Lite](https://greasyfork.org/en/scripts/15173-visited-lite): Đổi màu các trang web đã xem  
[Anti Anti-debugger](https://greasyfork.org/en/scripts/440060-anti-anti-debugger): Mở khóa các trang web chặn ấn F12

### Chặn ads, tracking, popup, shortlink...
[Bypass All Shortlinks](https://greasyfork.org/en/scripts/431691-bypass-all-shortlinks): Vượt qua các shortlink | [Bản đã xóa quảng cáo trong script](https://voz.vn/goto/post?id=29305754)  
[AdGuard Extra](https://github.com/AdguardTeam/AdGuardExtra): Xóa qc của adguard  
[Popup Blocker by AdGuard](https://github.com/AdguardTeam/PopupBlocker): Chặn popup  
[Clean Tracking URLs](https://greasyfork.org/en/scripts/456881-%E8%B7%9F%E8%B8%AA%E9%93%BE%E6%8E%A5%E5%87%80%E5%8C%96)  
[ABPVN Script](https://github.com/abpvn/abpvn/tree/master/script)  
[Privacy Redirector](https://greasyfork.org/en/scripts/436359-privacy-redirector): Chuyển tiếp sang các thay thế các trang MXH để chống bị theo dõi

### Userscript cho Youtube
[Youtube Ad Cleaner(Include Non-Skippable Ads- works)](https://greasyfork.org/en/scripts/386925-youtube-ad-cleaner-include-non-skippable-ads-works) , [YouTube Ads Skip](https://greasyfork.org/en/scripts/479557-youtube-ads-skip) , [YouTube AD Blocker](https://greasyfork.org/en/scripts/459541-youtube%E5%8E%BB%E5%B9%BF%E5%91%8A-youtube-ad-blocker/): Chặn quảng cáo
[Nova youtube](https://greasyfork.org/en/scripts/433360-nova-youtube): Gồm các tiện ích như sponsorblock, hiện nút dislike
[YouTube JS Engine Tamer](https://greasyfork.org/en/scripts/473972-youtube-js-engine-tamer): Fix lỗi youtube bóp chậm lag
[YouTube Minimal on PC](https://greasyfork.org/en/scripts/457579-youtube-minimal-on-pc): Chuyển sang giao diện youtube mobile
[Disable YouTube AutoPause](https://greasyfork.org/vi/scripts/457219-disable-youtube-autopause) , [Disable YouTube Music AutoPause](https://greasyfork.org/en/scripts/464888-disable-youtube-music-autopause) Xóa thông báo tạm dừng video khi xem thời gian dài

### Userscript cho Mắc xoăn
[FB - Clean my feeds](https://greasyfork.org/en/scripts/431970-fb-clean-my-feeds) , [F.B. Purity](https://www.fbpurity.com/install.htm) , [Social Fixer for Facebook](https://socialfixer.com/): Chặn quảng cáo, rác trên facebook
[Instagram Download Button](https://greasyfork.org/en/scripts/406535-instagram-download-button): Tải video, ảnh trên instagram

### Userscript cho các trang web khác
[MPV-M3U8 Video Detector and Downloader](https://github.com/FirefoxUniverse/FirefoxTweaksVN/blob/main/userscript/m3u8.user.js): Tải xuống video dạng m3u8  
[Bing Increase Word Limit](https://greasyfork.org/en/scripts/483319-bing-increase-word-limit): Bỏ giới hạn kí tự trong bing chat  
[Better Google](https://github.com/aligo/better-google): Hiển thị kết quả tìm kiếm google tốt hơn  
[ChatGPT Infinity ∞](https://greasyfork.org/en/scripts/465051-chatgpt-infinity) Chat gpt sẽ trả lời dài nhất có thể  
[Netflix Plus](https://greasyfork.org/en/scripts/478739-netflix-plus) Tool netflix  
[Undiscord](https://greasyfork.org/en/scripts/406540-undiscord) Xóa tin nhắn discord hàng loạt  
[Voz BeVietnam Font](https://greasyfork.org/en/scripts/476158-voz-bevietnam-font) Voz font cũ


