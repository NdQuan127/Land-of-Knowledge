---
{"dg-publish":true,"permalink":"/atlas/notes/ideas/u-block-origin-chan-quang-cao-tang-cuong-bao-mat-rieng-tu/"}
---

up:: [[Atlas/Maps/Firefox MOC\|Firefox MOC]]
tags:: #on/bt_chiase 
# uBlock Origin - Chặn quảng cáo, tăng cường bảo mật, riêng tư
## Giới thiệu uBlock Origin
Đây là addon chặn quảng cáo đạt tới mức độ **chân - thiện - mỹ** với thuật toán Regex được tối ưu cho tốc độ và thuật toán nhúng CSS để ẩn nội dụng được chau chuốt.

Đó là lý do tại sao addon này tốt hơn nhiều lần Adblock Plus với thuật toán tệ hơn cho hiệu năng tệ hơn, với người dùng Việt Nam thì tất nhiên sau khi cài xong uBlock các bạn vào Dashboard rồi kéo xuống dưới tìm ABPVN rồi bật lên để chặn quảng cáo Việt Nam hiệu quả.  
  
Ngoài ra việc chặn quảng cáo sẽ giúp các bạn tránh khỏi những trường hợp dính virus (như đồng chí NFT_God dính virus mất sạch coin do search Google rồi ấn nhầm vào quảng cáo Google).  
  
Cũng như tăng cường sự riêng tư vì các tracker bị chặn luôn, khiến các trang web không theo dõi được bạn.

## Các bộ lọc đáng dùng không lỗi cho uBlock
> Sau đây là những filter (bộ lọc) hay cho uBlock mà không gây lỗi web, bởi nó là bộ lọc `tính năng` hoặc chỉ dành cho một `đối tượng` nhất định nào đó:

- Chặn quảng cáo với Facebook (đối tượng): `https://raw.githubusercontent.com/ethan-xd/ethan-xd.github.io/master/fb.txt`
~~- Xem các trang đòi trả tiền không tốn xu nào với Bypass Paywall Clean (tính năng): `https://gitlab.com/magnolia1234/bypass-paywalls-clean-filters/-/raw/main/bpc-paywall-filter.txt`~~
- Nhảy link rút gọn,link theo dõi người dùng với LegitimateURLShortener (tính năng):`https://gitlab.com/DandelionSprout/adfilt/-/raw/master/LegitimateURLShortener.txt`
- [**Loại bỏ các trang web trùng lặp khỏi kết quả tìm kiếm Google, Duck, Bing...**](https://github.com/quenhus/uBlock-Origin-dev-filter) (đối tượng): `https://raw.githubusercontent.com/quenhus/uBlock-Origin-dev-filter/main/dist/all_search_engines/global.txt`
- (Chặn) [PrivacyEnhanced](https://github.com/stephenhawk8054/PrivacyExtended) cùng Adguard Privacy hay EasyPrivacy do [@Fioren](https://voz.vn/u/1680514/) giới thiệu
- (Tính năng) [Không Cần Đăng Nhập](https://github.com/DandelionSprout/adfilt/blob/master/BrowseWebsitesWithoutLoggingIn.txt) - Ẩn hết các hộp thoại bắt đăng nhập như Quora
- (Tính năng) [Anti-Paywall Cleaner](https://github.com/liamengland1/miscfilters/blob/master/antipaywall.txt) - Dùng thay thế Bypass Paywall Clean
- (Tính năng) [Bộ lọc trị web ngờ u ngu của tác giả Betterfox](https://github.com/yokoffing/filterlists/blob/main/annoyance_list.txt) - Dùng để sửa lại mấy trang web bị hỏng... do quản trị viên không có não
- (Đối tượng) [Dọn sạch rác rưởi Youtube](https://github.com/yokoffing/filterlists/blob/main/youtube_clear_view.txt) - Xóa những thứ gây mất tập trung khi xem Youtube, bình luận khi xem stream, chặn các trang lừa đảo phổ biến kiểu Elon Musk, Tesla... 

> **Cách thêm filter:**

![Pasted image 20230901161211.png](/img/user/Atlas/Utilities/Images/Pasted%20image%2020230901161211.png)

