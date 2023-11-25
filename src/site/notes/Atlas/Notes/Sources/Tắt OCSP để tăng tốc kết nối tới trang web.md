---
{"dg-publish":true,"permalink":"/Atlas/Notes/Sources/Tắt OCSP để tăng tốc kết nối tới trang web/"}
---

up:: [[Atlas/Maps/Firefox MOC\|Firefox MOC]]
tags:: #on/bt_chiase 

# Tắt OCSP để tăng tốc kết nối tới trang web
Đầu tiên cần hiểu OCSP là gì, nó hoạt động ra sao thì Firefox cứ mỗi khi các bạn kết nối với một trang web, nó sẽ gửi cái chứng chỉ đến máy chủ OCSP (máy chủ xác thực trạng thái chứng chỉ) để kiểm tra độ tin cậy của chứng chỉ, xem nó đã hết hạn hay bị giả mạo hay không thì sẽ bị buộc thu hồi, đó gọi là OCSP.  
  
Thế nhưng việc kết nối tới máy chủ để kiểm tra như vậy có nhiều nhược điểm:  

- Thứ nhất là ảnh hưởng tới tốc độ kết nối tới trang web của Firefox, nhanh thì tốn nửa giây, chậm thì hơn, đứt cáp thì còn hơn nữa vì máy chủ đặt xa tít mù khơi
- Tự dưng đi khoe với một thằng ất ơ mình vào gần như tất cả mọi trang web, trừ HTTP ra, ảnh hưởng tới tính riêng tư
- Nếu máy chủ OCSP sập thì khỏi vào web
- Có thể dễ dàng bị hacker quay như chong chóng nếu nó khiến bạn không kết nối vào máy chủ OCSP được rồi chuyển hướng tới máy chủ của nó (MITM)

  
Và Firefox bật OCSP mặc định, Chrome đã tắt OCSP đi từ rất lâu rồi.  
  
Vậy với những nhược điểm bên trên mà ưu điểm chẳng thấy đâu tốt nhất là nên tắt, ngoài ra mình là chuột bạch kể từ ngày Firefox thêm OCSP vào từ 3.x 4.x nào đó đến nay mà chưa thấy bị hack bao giờ cả, vậy nên cứ mạnh dạn tắt thôi.  
  
**Cách thức:  
- Vào `about:config`
- Tìm `security.OCSP.enabled`
- Chuyển thành `0`

**Tắt OCSP và mở CrLite. Nhanh hơn và bảo mật hơn**
> user_pref("security.remote_settings.crlite_filters.enabled", true);
  user_pref("security.pki.crlite_mode", 2);

Đó, chỉ đơn giản vậy thôi, một bài viết dài quan trọng để giải thích cách thức hoạt động của nó, ưu nhược của nó, như vậy sẽ hiểu sâu được nguyên nhân dẫn đến kết quả.