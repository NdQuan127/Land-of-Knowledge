---
{"dg-publish":true,"permalink":"/atlas/notes/sources/multi-threaded-download-manager-tai-da-luong-bat-link-video-tai-hang-loat-noi-chung-la-xin-nhu-idm/"}
---

up:: [[Atlas/Maps/Firefox MOC\|Firefox MOC]]
tags:: #on/bt_chiase 

# ~~Multi-Threaded Download Manager - Tải đa luồng, bắt link video, tải hàng loạt nói chung là xịn như IDM~~
> **Tình hình là MDM do tác giả đã ngừng update rồi nên là thuật toán tải của thằng này có chút outdate mà lại không ai chịu phát triển nó tiếp. Tuy hiện giờ nó vẫn rất ngon nhưng để lâu dài anh em có thể chuyển sang dùng con Vịt Pede**

## Hướng dẫn cài MDM  
Thằng [**Multi-Threaded Download Manager**](https://addons.mozilla.org/en-US/firefox/addon/multithreaded-download-manager/) (**>>>>**[**Bản mod ngon hơn hỗ trợ tải đa luồng Google Drive và nhiều trang hơn**](https://voz.vn/t/tong-hop-nhung-addon-chat-cho-firefox-pc-mobile.682181/post-24638856)) này đã test thử, tính năng tải đa luồng như IDM hoạt động nhé, cơ mà mặc định giới hạn 6 luồng (đủ dùng và tốt nhất nên để 6 luồng thậm chí thấp hơn tầm 3-4 luồng sẽ xanh sạch đẹp cho server hơn) bằng với `network.http.max-persistent-connections-per-server` và `network.http.max-persistent-connections-per-proxy` trong about: config vì nó dùng API network của Firefox tải file.

Ngoài ra nó còn hỗ trợ bắt link video như IDM nhé, mà nó hoạt động trong Firefox nên không quan tâm tới Referer hay Cookies
![CCPLqbM.png](/img/user/Atlas/Utilities/Images/CCPLqbM.png)
Link test nếu muốn kiểm nghiệm: [https://www.w3schools.com/html/html5_video.asp](https://www.w3schools.com/html/html5_video.asp)  
  
Có tính năng Queue để giới hạn số lượng tải về trong cùng một thời điểm nhé:
![C49vsrH.png](/img/user/Atlas/Utilities/Images/C49vsrH.png)

> **Nên dùng kết hợp với script bắt link video của @boscofz sẽ rất tiện, script nhỏ nhẹ và tương thích mọi trang web:**

Copy đoạn code trong đường [link](https://jpst.it/3mzzh) rồi vào Violent Monkey vào dấu `+` tạo 1 new script mới rồi lưu vào rồi run scripts là được 😋

*Xem clip demo để dễ hình dung nhé*  
[https://streamable.com/mbkl7e](https://streamable.com/mbkl7e)

**Để Multithreaded Download Manager bắt link Drive thì vào options oánh dấu như sau**
![Pasted image 20230901152428.png](/img/user/Atlas/Utilities/Images/Pasted%20image%2020230901152428.png)


## Tổng kết lại tính năng so với IDM:  

- Tải đa luồng: Có
- Pause/Resume file đang tải dở: Có
- Quản lý tải về: Có
- Tải giới hạn số lượng tải cùng lúc: Có
- Bắt link video: Có (tốt hơn IDM do nó dùng cookies/referer từ Firefox)
- Tải hàng loạt: Có (tốt hơn IDM do nó dùng cookies/referer từ Firefox)

Tính năng mà IDM không có:  

- Hoạt động ngay trong trình duyệt nên nó sử dụng cookies/referer tốt hơn, ví dụ khi tải những link premium thì IDM phải thêm vào mục Account thủ công, thằng này phang luôn trong Firefox vì nó chia sẻ đăng nhập với Firefox
- Vì MDM hoạt động ngay trong Firefox nên [**nếu trang nào tải khoai quá vì một số lý do nó ghét phân luồng thì chọn `Continue in browser` tải trong Firefox là xong**](https://voz.vn/t/tong-hop-nhung-addon-chat-cho-firefox-pc-mobile.682181/post-24848706)
- Không cần ghép file như IDM làm quá tải ổ cứng, thằng này sử dụng thuật toán file ảo hiện đại, nó tạo ra một file ảo sử dụng Storage API của Firefox, ví dụ tải file 4GB thì nó tạo ra một file rỗng 4GB, sau đó tải nhồi dữ liệu vào file đó luôn nên **KHÔNG PHẢI GHÉP FILE** như IDM
- Tải những thứ mà IDM không tải được do nó hoạt động trong Firefox, cái gì Firefox thấy là nó thấy, và nó thấy là nó tải được. Ví dụ: Đố IDM tải được blob:, cơ mà nó tải được blob:
- Không thể bị phát hiện do nó dùng TLS Fingerprint của Firefox, nghĩa là Firefox chia luồng ra Firefox tải, nếu trang web muốn chặn là phải chặn cả Firefox, còn IDM thì nó có Fingerprint riêng (kể cả để HTTP Header y hệt trình duyệt trang web vẫn phát hiện được qua TLS Fingerprint. Test tại: [https://tls.browserleaks.com/json](https://tls.browserleaks.com/json) hoặc [https://tls.peet.ws/api/all](https://tls.peet.ws/api/all)) nên nói thẳng là trang web muốn chặn/giới hạn tốc độ IDM dễ như trở bàn tay, mà tác giả IDM cũng không đủ tuổi code để vượt qua TLS Fingerprint do thực tế chục năm rồi IDM vẫn còn ghép file gây nghẽn ổ cứng

## Tối ưu cho MDM thay đổi thuật toán tải chia luồng hiệu quả hơn để tránh bị máy chủ chặn
![Pasted image 20230901155311.png](/img/user/Atlas/Utilities/Images/Pasted%20image%2020230901155311.png)

