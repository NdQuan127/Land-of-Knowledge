---
{"dg-publish":true,"permalink":"/sources/cai-uosc-cho-mpv-de-lay-tinh-nang-chuyen-chat-luong-video-playlist-subtitle/"}
---

up:: [[+ Encounters/Kết nối Firefox với ứng dụng ngoài để mở,tải video,playlist bằng MPV,yt-dlp\|Kết nối Firefox với ứng dụng ngoài để mở,tải video,playlist bằng MPV,yt-dlp]]
tags:: #on/firefox 

# Cài uosc cho MPV để lấy tính năng (chuyển chất lượng video, playlist, subtitle..)

- Tạo folder portable_config trong cùng một thư mục với mpv.exe nếu chưa tạo
- Tạo folder tên scripts và tên script-opts trong thư mục portable_config
- Tải **uosc.zip** tại đây vào đúng folder portable_config: [https://github.com/tomasklaen/uosc/releases](https://github.com/tomasklaen/uosc/releases)
- Giải nén Extract Here (sao cho folder scripts trong file nén chèn vào folder scripts trong thư mục portable_config và thư mục fonts nằm chung với thư mục scripts)
- (Không cần thiết lắm) Tải file config của uosc tại đây vào folder script-opts: [https://raw.githubusercontent.com/tomasklaen/uosc/main/script-opts/uosc.conf](https://raw.githubusercontent.com/tomasklaen/uosc/main/script-opts/uosc.conf)
- (CỰC KỲ QUAN TRỌNG) Tạo một file tên `mpv.conf` trong thư mục `portable_config` rồi copy toàn bộ đoạn dưới này vào rồi Save:
```
#uosc
# required so that the 2 UIs don't fight each other
osc=no
# uosc provides its own seeking/volume indicators, so you also don't need this
osd-bar=no
# uosc will draw its own window controls if you disable window border
border=no
```

- *Giảm kích thước thanh timeline:* Mở `uosc.conf`, chỉnh `timeline_size_max_fullscreen=16`, `timeline_size_max=16`

