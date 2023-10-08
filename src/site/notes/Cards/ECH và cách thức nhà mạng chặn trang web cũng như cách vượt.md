---
{"dg-publish":true,"permalink":"/cards/ech-va-cach-thuc-nha-mang-chan-trang-web-cung-nhu-cach-vuot/"}
---

up:: [[Atlas/Firefox MOC\|Firefox MOC]]
tags:: #on/firefox 

# ECH và cách thức nhà mạng chặn trang web cũng như cách vượt
## DPI là gì?
- Deep Packet Inspection - DPI (tạm dịch: phân tích sâu các gói)  là 1 loại filter mạng. Nói chi tiết hơn thì DPI có thể được sử dụng để phát hiện, định vị, phân loại, định tuyến lại hoặc chặn bất kỳ gói nào có tải trọng dữ liệu hoặc mã cụ thể, vốn không thể thực hiện được bằng cách lọc gói thông thường.
- Nôm na dễ hiểu thì là nó có thể chặn quyền truy cập vào một số trang web nhất định. Đây cũng là cách mà rất nhiều Internet Service Providers ưa thích sử dụng.
- Ví dụ điển hình là các trang web như Pỏn hub, Ếch video, Medium,... bị chặn theo cách này.

## Cách vượt DPI
Thật ra để vượt DPI thì có rất nhiều thủ thuật, nhưng nhìn chung thì có các cách phổ biển sau:
- **Sử dụng DNS mã hóa:** *TẤT CẢ* công cụ vượt đều phải có cái này, vì băm giỏi tới đâu mà không mã hóa DNS thì chỉ có cái nịt. ![:D](https://statics.voz.tech/styles/next/xenforo/smilies/popo/biggrin.png?v=01 "Big grin    :D")
- **Băm nhỏ gói tin ClientHello:** Ví dụ như vào Pỏnhub.com chẳng hạn thì gói tin thứ nhất gửi Pỏn, gói thử hai gửi hub.com thì nhà mạng không dò ra được là Bonhup.com, đây là cách căn bản nhất của Chunk Rust và GoodbyeDPI
- **Xóa SNI trong ClientHello:** Đây là một tính năng của GoodbyeDPI mà Chunk Rust không có, và khả năng lớn đây là tính năng bán ra tiền bởi một khi đã xóa SNI thì nhà mạng BÓ TAY CHỊU TRÓI, tuy nhiên có thể gây lỗi và rủi ro bảo mật lớn.
- **Sử dụng ECH:** Đây là một nhánh của xóa SNI vì nó không xóa SNI mà mã hóa đi, kết quả là vừa có thể vào được trang web bị chặn, vừa không phải xóa SNI nên đạt hiệu quả ổn định nhất. Tuy nhiên có nhược điểm là nhiều khi cần trang web hỗ trợ TLS 1.3 và nhà mạng có thể chặn ECH hoàn toàn y như băm ClientHello bằng việc chặn béng TLS 1.3.
- **Giả mạo Host header cho HTTP:** Ví dụ Pỏnhub.com sẽ bị biến thành PỎNHUB.CoM. Vì nhà mạng không dùng Regex cho router vì tốn cực nhiều tài nguyên nên sẽ cho qua.
> Chi tiết hơn anh em có thể xem cách hoạt động của [GoodbyeDPI](https://github.com/ValdikSS/GoodbyeDPI#active-dpi](https://github.com/ValdikSS/GoodbyeDPI#active-dpi)

> Cách vượt DPI hợp lý nhất hiện tại là [[Cards/ProxySwitchy - Fake IP cực đỉnh, vô Pỏnhub, medium,... ko cần fake vpn\|ProxySwitchy - Fake IP cực đỉnh, vô Pỏnhub, medium,... ko cần fake vpn]]


## Lạm bàn 1 chút về GoodbyeDPI

Hiện tại, GoodbyeDPI chỉ nên dùng để vào những trang không quan trọng, những trang không đăng nhập chứ việc nó xén bớt SNI khiến giảm bảo mật kết nối SSL. Những trang như ngân hàng thì tuyệt đối không, và có vài trang ngân hàng cũng lỗi khi dùng GoodbyeDPI.  
  
Đáng tiếc là tác giả của GoodbyeDPI hiện tại mất tích đâu mất rồi nên Github chả thấy update gì từ 3/2022 rồi. Nên lời hứa của ổng sẽ thêm tính năng ngoại lệ kiểu chỉ cho những trang cần thiết như Bonhup, Medium, Ếch Vít... sẽ chỉ như "Tháng Tư là lời nói dối của em" thôi.  
  
Nếu GoodbyeDPI có tính năng trên sẽ đáng dùng, bởi khi đó nó không lọc tất cả gói tin và loại bỏ SNI cho tất cả gói tin như hiện tại.