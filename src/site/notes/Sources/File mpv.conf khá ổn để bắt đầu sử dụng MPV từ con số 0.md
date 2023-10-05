---
{"dg-publish":true,"permalink":"/sources/file-mpv-conf-kha-on-de-bat-dau-su-dung-mpv-tu-con-so-0/"}
---

up:: [[+ Encounters/Kết nối Firefox với ứng dụng ngoài để mở,tải video,playlist bằng MPV,yt-dlp\|Kết nối Firefox với ứng dụng ngoài để mở,tải video,playlist bằng MPV,yt-dlp]]
tags:: #on/firefox 

# File mpv.conf khá ổn để bắt đầu sử dụng MPV từ con số 0

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

> Với lavfast vào cuối file vì lavfast cải thiện hiệu năng khi xem 720 H264 rất nhiều lần:
```javaScript
[lavcfast]
profile-cond=p["video-format"] == "h264" or p["video-format"] == "mpegvideo" or p["video-format"] == "mpegvideo1" or p["video-format"] == "mpegvideo2"
profile-restore=copy-equal
vd-lavc-fast=yes
```