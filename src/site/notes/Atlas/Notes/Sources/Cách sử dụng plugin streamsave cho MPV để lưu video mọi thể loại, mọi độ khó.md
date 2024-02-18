---
{"dg-publish":true,"permalink":"/Atlas/Notes/Sources/Cách sử dụng plugin streamsave cho MPV để lưu video mọi thể loại, mọi độ khó/"}
---

up:: [[Atlas/Notes/Sources/Kết nối Firefox với ứng dụng ngoài để mở,tải video,playlist bằng MPV,yt-dlp\|Kết nối Firefox với ứng dụng ngoài để mở,tải video,playlist bằng MPV,yt-dlp]]
tags:: #on/firefox 
# Cách sử dụng plugin streamsave cho MPV để lưu video mọi thể loại, mọi độ khó

- **Ưu điểm:**  
	- Tự động đặt tên file là tên ở title của MPV
	- Không bao giờ ghi đè vào file cũ, cho phép tạo một lô xích xông các clip ngắn dụng video-1.mp4, video-2.mp4, video-3.mp4.... cho cùng một video
	- Thay đổi thư mục lưu tùy ý dễ dàng
	- Hỗ trợ cắt một phần của video với AB-Loop để tạo mấy cái hình động hay clip gắn dạng short trên Youtub

> Link tải: [https://github.com/Sagnac/streamsave/archive/refs/heads/master.zip](https://github.com/Sagnac/streamsave/archive/refs/heads/master.zip)  

- Giải nén file `streamsave.lua` vào `scripts`
- Tạo một file tên `streamsave.conf` rồi bỏ vào `script-opts`, copy toàn bộ dưới đây:
```python
# This is an example script config file with the default user options.
# This file goes in ~~/script_opts
# If you are not going to be changing these options it is not necessary to download this file.
# For more information regarding these options please refer to the README and/or the script.

# General Options

save_directory=~~/
# current directory
dump_mode=continuous
# <ab|current|continuous|chapter|segments>
output_label=increment
# <increment|range|timestamp|overwrite|chapter>
force_extension=no
# <no|.ext>
force_title=no
# <no|title>
range_marks=no
# <yes|no>
track_packets=no
# <yes|no>

# Automation Options

autostart=no
# <yes|no>
autoend=no
# <no|HH:MM:SS>
hostchange=no
# <yes|no>
quit=no
# <no|HH:MM:SS>
piecewise=no
# <yes|no>
```

- **Cách sử dụng:** 
	- Để lưu toàn bộ video ấn `Ctrl+Z`
	- Để lấy từng đoạn trong video đầu tiên ấn `Alt+Z` vài lần cho nó chuyển qua chế độ `AB Loop`, sau đó chọn thời gian bắt đầu và ấn `l` để đánh dấu, sau đó chọn thời gian kết thúc rồi lại ấn `l` lần nữa, sau đó ấn `Ctrl+Z` để lưu lại. Vậy là có một clip dạng ngắn như Youtube Shorts.
	- Các tính năng lưu chapter, segment rất đơn giản các bạn tự tìm hiểu nhé, cứ `Alt+Z` đổi chế độ, sau đó `Ctrl+Z` lưu

- **Cách thay đổi folder chứa file đã dump**, mặc định lưu ở trong thư mục `portable_config`:  
	- Mở file `streamsave.conf` lên
	- Tìm `save_directory=~~/` rồi đổi thành `save_directory=~~/dumped/` là nó sẽ lưu vào folder `dumped` trong `portable_config`
	- Vào folder `portable_config`, tạo thư mục tên `dumped`

> Video demo: https://a.uguu.se/nlbQUqps.mp4
***
Source: https://voz.vn/t/tong-hop-nhung-addon-chat-cho-firefox-pc-mobile.682181/post-24676423