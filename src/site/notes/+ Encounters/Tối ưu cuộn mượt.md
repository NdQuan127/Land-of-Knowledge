---
{"dg-publish":true,"permalink":"/encounters/toi-uu-cuon-muot/"}
---

up:: [[Atlas/Firefox MOC\|Firefox MOC]]
tags:: #on/firefox 

# Tối ưu cuộn mượt

> Anh em có thể thử thay đổi các thông số để phù hợp với bản thân mình

> Phía dưới đây là trường phái cuộn mượt hơn cả edge (mượt nhất)

Khoảng thời gian từ khi cuộn mượt cho tới khi kết thúc, thay đổi giá trị này tùy ý để thay đổi cảm giác mượt mà:  

|   |   |
|---|---|
|general.smoothScroll.mouseWheel.durationMaxMS|250|

|   |   |
|---|---|
|general.smoothScroll.mouseWheel.durationMinMS|200|
  
Nghĩa là để tăng độ mượt mà thì tăng `durationMaxMS`, giảm `durationMinMS` còn nếu mượt quá gây cảm giác khó chịu thì giảm và tăng.  
  
Tắt cuộn theo pixel, nghĩa là sẽ cuộn theo % của màn hình trang web 
(Nguồn: [736251 - smooth wheel precise scrolling isn't very responsive ](https://bugzilla.mozilla.org/show_bug.cgi?id=736251#c19)):  

|   |   |
|---|---|
|mousewheel.enable_pixel_scrolling|false|



|   |   |
|---|---|
|apz.overscroll.enabled|true|

|   |   |
|---|---|
|general.smoothScroll|true|

|   |   |
|---|---|
|mousewheel.default.delta_multiplier_y|275|

