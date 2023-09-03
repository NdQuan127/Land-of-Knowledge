---
{"dg-publish":true,"permalink":"/encounters/external-application-ket-noi-firefox-voi-ung-dung-ngoai-de-mo-tai-video-playlist-bang-mpv-yt-dlp/"}
---


up:: [[Cards/Nhập môn Firefox\|Nhập môn Firefox]] 
tags:: #on/bt_chiase 

# External Application - Kết nối Firefox với ứng dụng ngoài để mở,tải video,playlist bằng MPV,yt-dlp
> Cái này để setup thực ra khó vãi l** nên anh em cố gắng đọc kỹ đừng bỏ sót chỗ nào 🙂

**Video thành quả:** https://app.screencast.com/YfChCkjCDfu2l
**[External Application](https://addons.mozilla.org/en-US/firefox/addon/external-application/)**: Addon giúp kết nối Firefox với các ứng dụng bên ngoài, mở rộng khả năng của Firefox ra thành gần như vô hạn, nó có thể làm được những điều sau dựa trên thời gian thử nghiệm ngắn ngủi của mình:  

- Xổ video/playlist từ các trang như Youtube, Dailymotion, Twitch, Nicovideo... ra thẳng MPV để xem, tăng tính trải nghiệm: [Demo 1](https://streamable.com/7xioq7) | [Demo 2](https://streamable.com/sajctf)
- Xổ livestream sang MPV xem bỏ qua quảng cáo hoàn toàn
- Gửi thẳng ảnh tới phần mềm sửa ảnh để chỉnh sửa
- Gửi file đến Sandbox để mở luôn trong Sandbox
- Và rất rất nhiều sự kết hợp khác...
  
Khởi đầu mình giới thiệu cách để kết nối Firefox với MPV, mà kết quả là các bạn có thể xem video/playlist/channel của các trang như Youtube/Dailimotion/Nicovideo... thẳng trên MPV, bỏ hết quảng cáo rác rưởi cũng như hiệu năng tuyệt đỉnh mà trình xem HTML5 cùi bắp của trình duyệt web không bao giờ so bì lại.

> **Nên đọc**: Vì cái này set up khá phức tạp, nên nếu anh em cài khác mình nhiều khi sẽ khó làm theo hướng dẫn, nên đây là cấu trúc chung, 1 cái sườn để anh em làm theo, *không có đuôi file nghĩa là folder**, không bôi đen là tùy ý (có cũng được không có cũng ok hoặc có chỉ để mở rộng tính năng)*:

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

**Hướng dẫn:**
- Tải MPV và FFMPEG tại đây, giải nén sao cho file mpv.exe nằm cùng thư mục với file ffmpeg.exe: [https://github.com/zhongfly/mpv-winbuild/releases](https://github.com/zhongfly/mpv-winbuild/releases)
- (Nếu muốn cài đặt MPV thành trình xem phim mặc định thì chạy file install.bat sau đó vào Default Programs chỉnh MPV thành mặc định)
- (Trừ khi bạn chắc chắn máy tính của bạn là đồ mới sản xuất trong 1-2 năm đổ lại đây, luôn tải bản KHÔNG CÓ v3 cho lành)
- Tải yt-dlp.exe vào cùng thư mục chứa mpv.exe: [https://github.com/yt-dlp/yt-dlp/releases](https://github.com/yt-dlp/yt-dlp/releases)
- Cài đặt addon External Application bên trên.
- Click vào nút addon của External Application để mở ra trang tạo kết nối ứng dụng, sau đó thêm y xì như này:
    - Name: `MPV`
    - Executable: Đường dẫn tới file mpv.exe, ví dụ của mình là `D:\mpv\mpv.exe`
    - Arguments: `--ytdl [HREF]`
    - Chọn: `Toolbar button` và `Link context`
    - Save.
- Click vào nút EA ở toolbar, *một cửa sổ hiện ra như bên dưới, làm theo hướng dẫn tải file windows. Zip rồi chạy install. Bat để cài trình kết nối Firefox với ứng dụng bên ngoài của hệ điều hành:*
![Pasted image 20230902230709.png](/img/user/Extras/Images/Pasted%20image%2020230902230709.png)
![Pasted image 20230902230727.png](/img/user/Extras/Images/Pasted%20image%2020230902230727.png)
![Pasted image 20230902230749.png](/img/user/Extras/Images/Pasted%20image%2020230902230749.png)
![Pasted image 20230902231336.png](/img/user/Extras/Images/Pasted%20image%2020230902231336.png)
*(Tích chọn Link Context nữa cho tiện, sau này mở Youtube thấy muốn xem video nào thì chuột phải vào link video rồi gửi thẳng qua MPV đỡ phải mở trang xem lên tốn thời gian)*

> Còn có cả sub luôn cho anh em khỏi chê nhé, nếu muốn có sub thì làm như sau:

**Cách hiện sub**
Ở phần Arguments của nút MPV trong External Application thì tốt nhất là nên để là `--ytdl [HREF]` là tiện nhất sau này sẽ dùng `mpv.conf` để chỉnh sẽ tiện hơn.  
  
Sau đó mở `mpv.conf` lên, thêm:
```javaScript
ytdl-raw-options-append=no-check-certificates=
ytdl-raw-options-append=sub-langs=en,en-US,eng,vi,vi-VN,vie,ja,ja-JP,jap
#ytdl-raw-options-append=sub-lang="en,en.*,vi"
ytdl-raw-options-append=write-auto-sub=
ytdl-raw-options-append=write-sub=
```
Kết quả ![: D]( https://statics.voz.tech/styles/next/xenforo/smilies/popo/biggrin.png?v=01 "Big grin    : D")
![Pasted image 20230902231908.png](/img/user/Extras/Images/Pasted%20image%2020230902231908.png)

## File `mpv.conf` khá ổn để bắt đầu sử dụng MPV từ con số 0
```javaScript
#Cach su dung: Xoa # o doan #abc=xyz o dau dong de kich hoat nhung doan config mau

###########
# General #
###########
# Custom config
#Bat len neu muon giong PiP cua trinh duyet, geometry=x50% nen chuyen thanh geometry=x25%
#ontop                                   # video player always on top
osd-on-seek=no
osd-font-size=24
#osd-duration=100
keep-open=yes
force-window=immediate
no-focus-on-open
geometry=x50%
load-unsafe-playlists=yes
user-agent='Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:109.0) Gecko/20100101 Firefox/116.0'
force-seekable=yes
hr-seek=yes
hr-seek-framedrop=yes

#########
# uosc #
#########
# required so that the 2 UIs don't fight each other
#osc=no
# uosc provides its own seeking/volume indicators, so you also don't need this
#osd-bar=no
# uosc will draw its own window controls if you disable window border
#border=no

#########
# Video #
#########
hwdec=auto-safe

#Cho he may cui bap, CPU va GPU giam cuc nhieu
#tscale=nearest
#interpolation=no
#scale=bilinear
#cscale=bilinear
#dscale=bilinear
#sws-scaler=bilinear

#Cho he may khung, CPU va GPU tang doi lay video net hon
#vo=gpu-next #Neu may khoe, card man hinh doi moi, tra gia bang CPU/GPU cao cho hinh anh dep
#scale=ewa_lanczossharp
#cscale=ewa_lanczossharp

#########
# Audio #
#########
#audio-file-auto=fuzzy                   # play external audio files with same name as video files
#audio-pitch-correction=yes              # automatically insert scaletempo when playing with higher speed
volume-max=200                          # maximum volume in %, everything above 100 results in amplification
volume=100                              # default volume, 100 = unchanged

#########
#Subtitle
#########
#Doi mau, kich co subtitle
#sub-color='#FFFF00' #subtitle color in rgb
#sub-shadow-color='#000000' #shadow color
#sub-font='Noto Sans' #set font
#sub-bold=yes
#sub-font-size=60
#sub-pos=95 #subtitle position 5 percent above the bottom of the screen
#sub-fix-timing=yes

#########
# Cache #
#########
cache-pause
cache=yes
#cache-default=80000                     # size in KB (80MB) -- Increase if you have buffering issues
#cache-backbuffer=80000                  # size in KB
#cache-initial=0                         # start playback when your cache is filled up with x kB
cache-secs=600                           # how many seconds of audio/video to prefetch if the cache is active
demuxer-thread=yes
#demuxer-max-bytes=50MiB
demuxer-max-back-bytes=50MiB
demuxer-readahead-secs=600

#########
# Network #
#########
network-timeout=100
stream-lavf-o-append=reconnect_on_http_error=4xx,5xx
stream-lavf-o-append=reconnect_delay_max=30
stream-lavf-o-append=reconnect_streamed=yes
#stream-lavf-o-append=reconnect_on_network_error=yes

#########
# YTDL #
#########
ytdl-raw-options-append=no-check-certificates=
ytdl-raw-options-append=yes-playlist=
#ytdl-raw-options-append=extractor-args=youtube:player_skip=webpage,configs,js;player_client=android,web;lang=vi,en
#Chuyen sang Youtube VN may chu Youtube tra lai CDN gan Viet Nam, co the gay loi/thay doi ?
#ytdl-raw-options-append=extractor-args=youtube:lang=vi,en,ja
ytdl-raw-options-append=sub-langs=en,en-US,eng,vi,vi-VN,vie,ja,ja-JP,jap,live_chat
ytdl-raw-options-append=write-sub=
ytdl-raw-options-append=write-auto-sub=
ytdl-raw-options-append=mark-watched=
ytdl-raw-options-append=add-metadata=
#Danh dau da xem khong can plugin markwatched.lua https://voz.vn/t/tong-hop-nhung-addon-chat-cho-firefox-pc-mobile.682181/post-25727088
#ytdl-raw-options-append=cookies-from-browser=firefox:_ĐƯỜNG_DẪN_PROFILE_FIREFOX_VÀO_ABOUT:SUPPORT_OPEN_PROFILE_
#ytdl-raw-options-append=mark-watched=

#########
# Profile #
#########
#Chi tiet: https://voz.vn/t/tong-hop-nhung-addon-chat-cho-firefox-pc-mobile.682181/post-24149834
#Luon de phan nay o cuoi file mpv.conf
[quality-youtube]
profile-cond=path:match"youtube" ~= nil or filename:match"youtube" ~= nil or filename:match"/live$" ~= nil
profile-restore=copy
ytdl-format=bestvideo[container*=dash][proto*=http_dash_segments][height<=?720][fps<=?30][vcodec!=?vp9]+bestaudio/best[height<=720]

[quality-twitter]
profile-cond=path:match"twitter" ~= nil or filename:match"twitter" ~= nil or path:match"video.twimg" ~= nil or filename:match"video.twimg" ~= nil
profile-restore=copy
#ytdl-format=bestvideo[height<=?360]+bestaudio/best[height<=360]
#ytdl-format=bestvideo[proto*=hls]+bestaudio/best
ytdl-format=hls-197/hls-783/hls-475/hls-80
#ytdl-format=hls-783/hls-475/hls-197/hls-80
#hls-783/hls-475/hls-197/hls-80

[stream-no-ytdl]
profile-cond=string.find(path, '.m3u') ~= nil or string.find(path, '.mpd') ~= nil or string.find(path, '.mp4') ~= nil or string.find(path, 'googlevideo.') ~= nil or string.find(path, '.jpg') ~= nil or string.find(path, '.png') ~= nil
profile-restore=copy-equal
ytdl=no




#EOF
```

> Tối ưu hiệu năng MPV thì thêm vào file `mpv.conf`:
```javaScript
###################
#Performance Tweaks#
###################
gpu-dumb-mode=yes
interpolation=no
scale=nearest #somehow fastest bilinear
cscale=nearest
dscale=nearest
tscale=nearest
sws-scaler=fast-bilinear
```

Với lavfast vào cuối file vì lavfast cải thiện hiệu năng khi xem 720 H264 rất nhiều lần:
```javaScript
[lavcfast]
profile-cond=p["video-format"] == "h264" or p["video-format"] == "mpegvideo" or p["video-format"] == "mpegvideo1" or p["video-format"] == "mpegvideo2"
profile-restore=copy-equal
vd-lavc-fast=yes
```

## Cài `uosc` cho MPV để lấy tính năng (chuyển chất lượng video, playlist, subtitle..
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

