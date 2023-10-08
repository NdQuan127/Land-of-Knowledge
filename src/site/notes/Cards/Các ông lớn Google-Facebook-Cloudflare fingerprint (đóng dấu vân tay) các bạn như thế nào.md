---
{"dg-publish":true,"permalink":"/cards/cac-ong-lon-google-facebook-cloudflare-fingerprint-dong-dau-van-tay-cac-ban-nhu-the-nao/"}
---

up:: [[Atlas/Firefox MOC\|Firefox MOC]]
tags:: #on/firefox 

# Các ông lớn Google-Facebook-Cloudflare fingerprint (đóng dấu vân tay) các bạn như thế nào
## Trước hết, bạn phải hiểu fingerprint là gì đã?
- Browser Fingerprint là 1 dạng vân tay kỹ thuật số. Nó là tập hợp các thông tin và chỉ số liên quan đến thiết bị của người dùng, từ phần cứng, hệ điều hành đến trình duyệt và cấu hình của thiết bị. Mỗi người dùng internet đều có tập hợp thông tin trình duyệt, bao gồm hệ điều hành, plugin hoạt động, vị trí, múi giờ, ngôn ngữ, độ phân giải màn hình,...khác nhau. Vì vậy, giống như dấu vân tay thật của chúng ta, dấu vân tay trình duyệt của mỗi người là độc nhất.
- Ví dụ như nếu dùng một cái quá khác với 9 tỉ người dùng khác như `99.99.99.0/24`, thì mình là người duy nhất trên đời dùng nó, sẽ bị các trang như Google, Facebook nó đóng dấu vân tay, khi đó đi đâu cứ gặp dịch vụ của Google chạy nền như Google Analytics, Google Ads, comment Facebook, nút Like... thì nó biết ngay mình là ai kể cả có fake IP thành người ngoài hành tinh.  
  
## Cách xác định Fingerprint

>Trang web xác định fingerprint là dựa trên nhiều yếu tố:  
- ECS lạ (nếu có)
- Kích cỡ màn hình (đó là lý do tại sao Librewolf hay Tor ép người dùng phải để cửa sổ trình duyệt ở 1080x720)
- TLS Fingerprint
- GPU vẽ ra canvas, mỗi GPU vẽ ra một canvas với thông số khác nhau, đây là vân tay cực chuẩn (nên Tor hay Librewolf giả mạo nó)
- User-Agent
- IP
- Quảng cáo mà người dùng chặn

Rất nhiều yếu tố khác mà những ông lớn như Google, Facebook áp dụng, **từ đó nó xây dựng được lịch sử duyệt web, thói quen người dùng để tạo quảng cáo đúng ngay sở thích bệnh hoạn của người dùng.**