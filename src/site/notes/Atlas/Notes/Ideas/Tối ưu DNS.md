---
{"dg-publish":true,"permalink":"/Atlas/Notes/Ideas/Tối ưu DNS/"}
---

up:: [[Atlas/Maps/Firefox MOC\|Firefox MOC]]
tags:: #on/bt_chiase 

# Tối ưu DNS
Đôi khi mạng chậm cũng có thể do Microsoft trả về CDN ở tận trời Tây, nên sử dụng NextDNS/GoogleDNS (gửi ECS) để Tây nó trả về máy chủ gần Việt Nam, đặc biệt tránh dùng 1.1.1.1 cùi bắp vì nó trả về CDN tận Mỹ cuồng râm, cứ hiểu là 1.1.1.1 chỉ dành cho người Mỹ bản địa.

Đặt DNS Firefox thành NextDNS bằng cách `about:config` (anh em cũng có thể vào settings mục DNS để chỉnh cho nhanh):  

|   |   |
|---|---|
|network.trr.uri|https://doh3.dns.nextdns.io/3b8d79|

|   |   |
|---|---|
|network.trr.custom_uri|https://doh3.dns.nextdns.io/3b8d79|

|   |   |
|---|---|
|network.trr.mode|3|

  
Anh em nên sử dụng ID này `https://doh3.dns.nextdns.io/3b8d79` (không chặn quảng cáo, tracking) hoặc ID của riêng cá nhân với thiết lập tương đương để tăng tính ổn định cho Firefox bởi uBlock bao khoản chặn quảng cáo rồi, nếu dùng ID có chặn quảng cáo thì sẽ gây lỗi web hay bị phát hiện chặn quảng cáo bởi nhiều trang web khác, **nghĩa là các bạn chỉ dùng NextDNS để lấy ECS kiếm máy chủ gần Việt Nam nhất có thể cho Firefox** **và để chặn các trang độc hại, lừa đảo**, cụ thể:  
  

|   |   |
|---|---|
|network.trr.uri|https://doh3.dns.nextdns.io/3b8d79|

|   |   |
|---|---|
|network.trr.custom_uri|https://doh3.dns.nextdns.io/3b8d79|

|   |   |
|---|---|
|network.trr.mode|2|

  
**Bật QUICv2** (Cách thức: [https://github.com/kelmenhorst/quic-censorship/blob/main/browsers.md](https://github.com/kelmenhorst/quic-censorship/blob/main/browsers.md) + [https://datatracker.ietf.org/doc/draft-duke-httpbis-quic-version-alt-svc/](https://datatracker.ietf.org/doc/draft-duke-httpbis-quic-version-alt-svc/)):  

|   |   |
|---|---|
|network.http.http3.alt-svc-mapping-for-testing|doh3.dns.nextdns.io; h3=":443"; quicv="709a50c4,1", dns.google; h3=":443"; quicv="709a50c4,1"|

  
## Tối ưu ẩn danh bằng cách bật ECH (Encrypted ClientHello) để nhà mạng không nhìn thấy, vào web bị chặn DPI 
*(Chú ý ở thời điểm hiện tại ECH đang là bản nháp, khi bật lên mạng sẽ bị trễ đi một chút)*

|   |   |   |
|---|---|---|
|network.dns.force_use_https_rr|true||

|   |   |
|---|---|
|network.dns.force_waiting_https_rr|true|

  
**Ép dùng bản ghi HTTPS và đợi bản ghi HTTPS để ECH hoạt động** 

*ECH:*  

|   |   |   |
|---|---|---|
|network.dns.echconfig.enabled|true||

|   |   |   |
|---|---|---|
|network.dns.echconfig.fallback_to_origin_when_all_failed|false||

|   |   |   |
|---|---|---|
|network.dns.http3_echconfig.enabled|true||

|   |   |   |
|---|---|---|
|security.tls.ech.disable_grease_on_fallback|false||

|   |   |
|---|---|
|security.tls.ech.grease_http3|true|

|   |   |
|---|---|
|security.tls.ech.grease_probability|100|

*Nếu không vào được một số trang thử tắt IPv6:*  

|   |   |
|---|---|
|network.dns.disableIPv6|true|

*Nâng cấp kết nối lên HTTPS để tránh bị chặn qua header:*

|   |   |
|---|---|
|dom.security.https_first|true|

*TRR phải dùng của NextDNS hoặc Cloudflare:*  

|   |   |   |
|---|---|---|
|network.dns.skipTRR-when-parental-control-enabled|false||

|   |   |   |
|---|---|---|
|network.trr.async_connInfo|true||

|   |   |   |
|---|---|---|
|network.trr.confirmation_telemetry_enabled|false||

|   |   |   |
|---|---|---|
|network.trr.default_provider_uri|https://doh3.dns.nextdns.io/||

|   |   |   |
|---|---|---|
|network.trr.disable-ECS|false||

|   |   |
|---|---|
|network.trr.mode|3|


> **Sự hữu ích khi dùng DNS có ECS**

- Ping lần đầu vào DNS thì nó cache lại được, vì đây là ping lấy IP máy chủ, lần tiếp theo thì sẽ là 0ms
- Tuy nhiên khoảng thời gian trả dữ liệu lại từ máy chủ thì **thứ duy nhất làm giảm ping là máy chủ gần vị trí mình đang đặt đít,** và đó là lý do tại sao ECS cần thiết nên NextDNS và GoogleDNS+ECS/Quad9 (bản [https://dns11.quad9.net/dns-query](https://dns11.quad9.net/dns-query)) tốt hơn
- Còn lý do tại sao nên dùng NextDNS đó là ECH nữa, hiện tại chỉ NextDNS và 1.1.1.1 hỗ trợ bản ghi TYPE65 giúp trình duyệt web lên được ECH, giúp vượt vũ môn vào Bonhup, Ếch Vít, Medium...
- Ngoài ra NextDNS hỗ trợ chặn web độc hại/lừa đảo (giúp người thân thoát dính họa sát thân vào trang các cược cược tung cái nhà, hay bị nhà tôi ba đời lừa mua thuốc trị bách bệnh...), web mới tạo (đa phần là virus) giúp giảm tối thiểu khả năng sẽ chết vì virus vì thường nếu nó chặn tên miền mới nó chặn luôn tên miền thằng hacker nó dùng để gửi thông tin mà spyware lấy được, chặn thì nó không lấy được gì

## HTTP3 & QICV2
**Tối ưu HTTP 3:**

|   |   |
|---|---|
|network.http.http3.send_background_tabs_deprioritization|true|

|   |   |
|---|---|
|network.http.http3.version_negotiation.enabled|true|

|   |   |
|---|---|
|security.tls.ech.grease_http3|true|

**Ép NextDNS chạy HTTP3 và QUICv2 bằng chỉnh altsvc:**  

|   |   |
|---|---|
|network.http.http3.alt-svc-mapping-for-testing|doh3.dns.nextdns.io;h3=":443"; quicv="6b3343cf,1" |

**Trr:**

|   |   |
|---|---|
|network.dns.skipTRR-when-parental-control-enabled|false|

|   |   |
|---|---|
|network.trr.async_connInfo|true|

|   |   |
|---|---|
|network.trr.confirmation_telemetry_enabled|false|

|   |   |
|---|---|
|network.trr.custom_uri|https://doh3.dns.nextdns.io/3b8d79|

|   |   |
|---|---|
|network.trr.disable-ECS|false|

|   |   |
|---|---|
|network.trr.mode|3|

|   |   |
|---|---|
|network.trr.uri|https://doh3.dns.nextdns.io/3b8d79|

*Chỉnh không giới hạn dns cache queries:*

|   |   |
|---|---|
|network.dnsCacheEntries|-1|
