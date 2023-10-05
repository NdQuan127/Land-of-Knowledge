---
{"dg-publish":true,"permalink":"/sources/nglayout-initialpaint-delay-khien-firefox-render-trang-it-di-giam-tong-tieu-thu-cpu/"}
---

up:: [[Atlas/Firefox MOC\|Firefox MOC]]
tags:: #on/bt_chiase 

# nglayout.initialpaint.delay khiến Firefox render trang ít đi giảm tổng tiêu thụ CPU
Ngày xưa hồi mà các bài báo Việt Nam đăng ồ ạt về tối ưu Firefox ấy, thì cái `nglayout.initialpaint.delay` là một trong những tối ưu sai rất sai khi họ khuyên người dùng hạ xuống thấp hơn 250, thực ra để giá trị này cải thiện hiệu năng thì nên tăng lên vì Firefox giờ rất thông minh rồi, tăng lên 1000000000000 thì khi trang tải xong Firefox cũng render một chạm cả trang luôn, cơ mà mình toàn để 2000 (nghĩa là nhắc Firefox cứ làm sao thì làm, sau 2s phải hiển thị trang web dựa trên những gì đã tải được) vì nhỡ sao trang web nó bị chậm có vài file css, js tải mãi không xong thì đợi dài cổ ![: D]( https://statics.voz.tech/styles/next/xenforo/smilies/popo/biggrin.png?v=01 "Big grin    : D")  
  
Tăng giá trị `nglayout.initialpaint.delay` sẽ cực kỳ hiệu quả khi dùng addon như Dark Reader, [**chi tiết**](https://voz.vn/t/tong-hop-nhung-addon-chat-cho-firefox-pc-mobile.682181/post-22949373).  
  
**Cách thức:**  
- Mở `about:config`, tìm và sửa lại:  

|   |   |   |
|---|---|---|
|nglayout.initialpaint.delay|2000||

|   |   |
|---|---|
|nglayout.initialpaint.delay_in_oopif|2000|