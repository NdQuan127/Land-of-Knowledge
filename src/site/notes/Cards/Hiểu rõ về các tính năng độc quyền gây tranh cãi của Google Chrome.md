---
{"dg-publish":true,"permalink":"/cards/hieu-ro-ve-cac-tinh-nang-doc-quyen-gay-tranh-cai-cua-google-chrome/"}
---

up:: [[Atlas/Firefox MOC\|Firefox MOC]]
tags:: #on/firefox 

# Hiểu rõ về các tính năng độc quyền gây tranh cãi của Google Chrome

> Chrome gần đây thì thể hiện thế độc quyền thấy rõ, mà mục tiêu chính là họ muốn biến trình duyệt web thành môi trường cho quảng cáo:  

## Manifest V3 triệt hạ khả năng chặn quảng cáo của trình duyệt. 
Tham khảo: [[+ Encounters/Sự khác biệt của uBlock Firefox vs Chrome vs Manifest V3 vs Adguard\|Sự khác biệt của uBlock Firefox vs Chrome vs Manifest V3 vs Adguard]]

## Privacy Sandbox - Quảng cáo bằng cách địa lịch sử duyệt web của người dùng.

[**Google Chrome vừa chính thức bật tính năng `Privacy Sandbox` lên tất cả phiên bản Chrome mới**](https://arstechnica.com/gadgets/2023/09/googles-widely-opposed-ad-platform-the-privacy-sandbox-launches-in-chrome/), tính năng này chính là FLoC cải biên do trước định thực hiện nhưng người dùng chửi cho nát mặt nên giờ lươn lẹo đổi tên thành `Privacy Sandbox`, nghe tên rất chi là riêng tư cơ mà nó ngược lại hoàn toàn, **nó cho phép trình duyệt web lấy lịch sử duyệt web của người dùng, tóm tắt lại rồi gửi cho trang web để họ tạo quảng cáo**, ví dụ:  

- Một ông hay vào web pỏn, hay xem bóng đá, hay vào sọp bee
- Google Chrome gửi cho trang web lịch sử duyệt web cho trang web sử dụng Privacy Sandbox
- Trang web phân tích lịch sử duyệt web và tạo ra quảng cáo cực kỳ khớp với sở thích bệnh hoạn của người dùng

Đó là Privacy Sandbox, một tính năng được quảng cáo là giúp loại bỏ 3rd party cookie, cơ mà các **trình duyệt như Safari hay Firefox đều có phương pháp trị dạng cookie này** (**với Safari là tắt hoàn toàn**, còn **Firefox thì cô lập bằng Total Cookie Protection**) nên **việc Chrome vẫn còn lưu luyến với 3rd party cookie là do họ muốn Chrome hỗ trợ quảng cáo tốt hơn** (đây là mình giải thích cho hiểu tại sao hoàn toàn có thể tắt 3rd party cookie mà Chrome không làm).  
  
Câu hỏi là liệu Google có ép Firefox phải thêm tính năng này vào vì trước Firefox đã phải thêm Widevine (WebDRM, cứ vào Netflix, Spotify bằng Floorp/Ungoogled/ Cromite sẽ hiểu) rồi ? Bởi nên nhớ tiền mua sữa cho con của các kỹ sư Mozilla 500 củ đô la / 1 năm là do Google trả.
![image.png|undefined](/img/user/Extras/Images/image.png)

> Tham khảo:
[https://arstechnica.com/gadgets/202...tform-the-privacy-sandbox-launches-in-chrome/](https://arstechnica.com/gadgets/2023/09/googles-widely-opposed-ad-platform-the-privacy-sandbox-launches-in-chrome/)  
[https://www.reddit.com/r/browsers/comments/16cvuyk](https://www.reddit.com/r/browsers/comments/16cvuyk)

## Widevine triệt hạ trình duyệt web mới nối bên thứ ba

- Widevine là 1 dạng chứng chỉ bảo mật để bảo vệ nội dung số do Google phát triển. Nó ngăn chặn việc copy, tải xuống hay thậm chí là quay chụp màn hình các nội dung số trên các nền tảng. 
- Mặc dù nghe rất tốt đẹp khi Google đang *bảo vệ* quyền lợi cho các trang web. Nhưng thực ra đây chả khác gì 1 *chiêu bài độc quyền* khi mà nếu các trang web có sử dụng Widevine. Cũng có nghĩa là để xem được các trang Netflix, Spotify... thì tác giả các trình duyệt khác phải quỳ lạy, van xin Google cấp cho, mà thường thì 1-2 năm không có phản hồi, dù rằng các trình duyệt web này đều tốt hơn Chrome gốc (Cromite, Ungoogled, Floorp...).  

## Web Environment Intergrity: 
> WebDRM nghĩa là trang web sẽ được phép cho phép một số trình duyệt họ ngoại lệ, còn không chặn hết nghĩa là nếu lập trình viên web thấy Chrome phổ biến nhất sẽ chặn tất và chỉ cho người dùng Chrome vào web của họ. 

Người tính không bằng Google tính, họ đã biết trước bối cảnh một ngày các trình duyệt ăn theo như Bromite/Cromite/Ungoogled/Brave.. sẽ trở nên phổ biến và ăn thị phần của Chrome do Chrome liên tục ra các chính sách khiến người dùng xóa Chrome như MV3, Privacy Sandbox, Web Environment Intergrity... nên mới ra cái DRM này như đòn chí mạng khiến các trình duyệt trên không bao giờ sánh được với Chrome gốc, và mấu chốt ở đây muốn có DRM Widevine phải chìa tay ra xin Google - Còn Google **Cho hay Không** là do **Họ**.  
  
Thông tin chi tiết thì cả Firefox và Chrome đang dùng Widevine L3 (cấp độ 3 - không chua cay mặn ngọt), còn xịn nhất là Widevine L1 (cấp cao nhất - siêu cay) ở các thiết bị Android:  [https://github.com/ungoogled-software/ungoogled-chromium/issues/2194](https://github.com/ungoogled-software/ungoogled-chromium/issues/2194)