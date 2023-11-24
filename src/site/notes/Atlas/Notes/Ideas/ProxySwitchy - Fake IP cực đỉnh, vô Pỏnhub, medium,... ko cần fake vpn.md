---
{"dg-publish":true,"permalink":"/atlas/notes/ideas/proxy-switchy-fake-ip-cuc-dinh-vo-ponhub-medium-ko-can-fake-vpn/"}
---

up:: [[Atlas/Maps/Firefox MOC\|Firefox MOC]]
tags:: #on/bt_chiase 

# ProxySwitchy - Fake IP cực đỉnh, vô Pỏnhub, medium,... ko cần fake vpn
[**ProxySwitchy Omega - Fake IP cực đỉnh**](https://addons.mozilla.org/en-US/firefox/addon/switchyomega/), addon này hỗ trợ đổi qua lại các proxy chỉ với một cú nhập chuột, và quan trọng hơn là tính năng chỉ fake proxy trên tên miền, một tính năng mà mình luôn yêu cầu cho mọi addon dạng thay đổi nội dung web mà mình giới thiệu từ trước tới giờ, ví dụ như uBlock có, Noscript có, RequestPolicy có, Custom User-Agent String có.  

Cách sử dụng thì cứ tạo profile proxy bình thường rồi nhấp biểu tượng ProxySwitchy rồi đổi thôi.  
  
Còn tính năng chỉ dùng proxy trên tên miền/trang mà mình ưa thích thì tạo một cái Profile Auto-Switch nhé, rồi để Default là Direct, còn phần Switch Rules để Condition type là wildcard cho dễ dùng, phần Condition Details thì ví dụ mình muốn chỉ dùng proxy trên artstation.com chẳng hạn thì để là artstation.com, còn phần Profile thì dẫn tới profile của proxy được tạo bên trên thôi.

## Hướng dẫn cách fake IP mà không fake IP để vượt DPI những trang cần vượt
**Ưu điểm:**  
- Hoạt động trên 100% trang web thậm chí không cần ECH, không quan tâm là Medium, Bonhup hay ẾchVid...
- Giải pháp mang tính toàn tổng hơn sử dụng cách thức băm nhỏ gói tin ClientHello ra để vượt cạn
- KHÔNG HỀ fake IP, nghĩa là tốc độ sẽ nguyên 100%, không tốn 1 xu, không dựa dẫm vào một ai cả
- Không gây lỗi web như GoodbyeDPI vì nó chỉ hoạt động trên những trang cần thiết chứ không toàn bộ hệ thống

Cách thức:  
- Tải [**Demergi**](https://voz.vn/t/tong-hop-nhung-addon-chat-cho-firefox-pc-mobile.682181/post-25669585), giải nén.
- Bật lên
- (Mẹo) *Sử dụng file .vbs để ẩn cái bảng CMD đi:*
	- Tạo file .vbs bỏ chung với file demergi-win-x 64.exe là được: `CreateObject("WScript.Shell").Run "demergi-win-x64.exe",0,True`
	- Rồi tạo shortcut cái file .vbs bỏ vào folder startup (*win+R -> shell:startup*) của window là khởi động cùng window đc
- Vào phần thiết lập của ProxySwitchy Omega tạo một `Proxy Profile` tên `ChunkRust`, điền vào là `127.0.0.1` port `8080` rồi Apply
- Tạo tiếp một `Switch Profile` tên `GoodbyeDPI` rồi `Add condition` rồi chọn Type là `URL regex`, Details là `medium.com` chọn Profile là `ChunkRust` rồi Apply
- (Chú ý) Muốn thêm trang nào thì tự thêm vào phần Details
- Chọn proxy là `GoodbyeDPI` trên thanh toolbar của ProxySwitchy Omega, và thế là xong.
![Pasted image 20230911231611.png](/img/user/Atlas/Utilities/Images/Pasted%20image%2020230911231611.png)
![Pasted image 20230911231629.png](/img/user/Atlas/Utilities/Images/Pasted%20image%2020230911231629.png)
![Pasted image 20230911231749.png](/img/user/Atlas/Utilities/Images/Pasted%20image%2020230911231749.png)
Vào Medium, Bonhup hay ẾchVid... test là thấy sẽ qua tuốt😁