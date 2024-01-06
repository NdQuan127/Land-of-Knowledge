---
{"dg-publish":true,"permalink":"/+/MPV/","noteIcon":""}
---

up:: [[Atlas/Notes/Sources/Kết nối Firefox với ứng dụng ngoài để mở,tải video,playlist bằng MPV,yt-dlp\|Kết nối Firefox với ứng dụng ngoài để mở,tải video,playlist bằng MPV,yt-dlp]]
tags:: #on/firefox

# MPV

Khởi đầu mình giới thiệu cách để kết nối Firefox với MPV, mà kết quả là các bạn có thể xem video/playlist/channel của các trang như Youtube/Dailimotion/Nicovideo... thẳng trên MPV, bỏ hết quảng cáo rác rưởi cũng như hiệu năng tuyệt đỉnh mà trình xem HTML5 cùi bắp của trình duyệt web không bao giờ so bì lại.

> **Nên đọc**: Vì cái này set up khá phức tạp, nên nếu anh em cài khác mình nhiều khi sẽ khó làm theo hướng dẫn, nên đây là cấu trúc chung, 1 cái sườn để anh em làm theo, *không có đuôi file nghĩa là folder, không bôi đen là tùy ý (có cũng được không có cũng ok hoặc có chỉ để mở rộng tính năng)*:

Anh em nên đặt MPV ở ổ D - `D:mpv\`
├───**mpv.exe**  
├───**yt-dlp.exe**  
├───**yt-dlp.conf**  
├───**ffmpeg.exe**  
├───streamlink  
│ ├───bin  
│ ├───ffmpeg  
├───**portable_config**  
│ ├───**mpv.conf**  
│ ├───**input.conf**  
│ ├───**scripts**  
│ ├───script-opts  
│ ├───shaders

>không có đuôi file nghĩa là folder, không bôi đen là tùy ý (có cũng được không có cũng ok hoặc có chỉ để mở rộng tính năng)

- Tải MPV và FFMPEG tại đây, giải nén sao cho file mpv.exe nằm cùng thư mục với file ffmpeg.exe: [https://github.com/zhongfly/mpv-winbuild/releases](https://github.com/zhongfly/mpv-winbuild/releases)
- (Nếu muốn cài đặt MPV thành trình xem phim mặc định thì chạy file install.bat sau đó vào Default Programs chỉnh MPV thành mặc định)
- (Trừ khi bạn chắc chắn máy tính của bạn là đồ mới sản xuất trong 1-2 năm đổ lại đây, luôn tải bản KHÔNG CÓ v3 cho lành)
- Tải yt-dlp.exe vào cùng thư mục chứa mpv.exe: [yt-dlp nightly](https://github.com/yt-dlp/yt-dlp-nightly-builds/releases) *(do youtube đang xiết nên tác giả đã ngừng update ở bản stable mà chuyển qua nightly để tránh anh Gồ để mắt)*
