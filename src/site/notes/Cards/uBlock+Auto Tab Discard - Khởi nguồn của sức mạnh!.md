---
{"dg-publish":true,"permalink":"/cards/u-block-auto-tab-discard-khoi-nguon-cua-suc-manh/"}
---

up:: [[Cards/Nhập môn Firefox\|Nhập môn Firefox]]
tags:: #on/bt_chiase 
# uBlock+Auto Tab Discard - Khởi nguồn của sức mạnh!
## uBlock Origin
Đây là addon chặn quảng cáo đạt tới mức độ **chân - thiện - mỹ** với thuật toán Regex được tối ưu cho tốc độ và thuật toán nhúng CSS để ẩn nội dụng được chau chuốt.

Đó là lý do tại sao addon này tốt hơn nhiều lần Adblock Plus với thuật toán tệ hơn cho hiệu năng tệ hơn, với người dùng Việt Nam thì tất nhiên sau khi cài xong uBlock các bạn vào Dashboard rồi kéo xuống dưới tìm ABPVN rồi bật lên để chặn quảng cáo Việt Nam hiệu quả.  
  
Ngoài ra việc chặn quảng cáo sẽ giúp các bạn tránh khỏi những trường hợp dính virus (như đồng chí NFT_God dính virus mất sạch coin do search Google rồi ấn nhầm vào quảng cáo Google).  
  
Cũng như tăng cường sự riêng tư vì các tracker bị chặn luôn, khiến các trang web không theo dõi được bạn.

### Các bộ lọc đáng dùng không lỗi cho uBlock
> Sau đây là những filter (bộ lọc) hay cho uBlock mà không gây lỗi web, bởi nó là bộ lọc `tính năng` hoặc chỉ dành cho một `đối tượng` nhất định nào đó:

- Chặn quảng cáo với Facebook (đối tượng): `https://raw.githubusercontent.com/ethan-xd/ethan-xd.github.io/master/fb.txt`
- Xem các trang đòi trả tiền không tốn xu nào với Bypass Paywall Clean (tính năng): `https://gitlab.com/magnolia1234/bypass-paywalls-clean-filters/-/raw/main/bpc-paywall-filter.txt`
- Nhảy link rút gọn, link theo dõi người dùng với LegitimateURLShortener (tính năng): `https://gitlab.com/DandelionSprout/adfilt/-/raw/master/LegitimateURLShortener.txt`
- [**Loại bỏ các trang web trùng lặp khỏi kết quả tìm kiếm Google, Duck, Bing...**](https://github.com/quenhus/uBlock-Origin-dev-filter) (đối tượng): `https://raw.githubusercontent.com/quenhus/uBlock-Origin-dev-filter/main/dist/all_search_engines/global.txt`

> **Cách thêm filter:**

![Pasted image 20230901161211.png](/img/user/Extras/Images/Pasted%20image%2020230901161211.png)

### Sự khác biệt của uBlock Firefox vs Chrome vs Manifest V3 vs Adguard

**1. uBlock của Firefox và uBlock của Chrome  
a) Hiệu năng:**  
- Biến code thành mã máy: uBlock của Firefox nhanh hơn rất nhiều lần uBlock của Chrome (cũng như Adguard), vì uBlock của Firefox hỗ trợ WebAssembly, nghĩa là khi lọc trang web, uBlock biến code từ Javascript thành mã máy, khiến tăng tốc quá trình lọc lên rất rất nhiều lần. Để nói về hiệu năng của Web Assembly so với Javascript thì nếu bạn học lập trình bạn sẽ thấy nó có _ngôn ngữ thông dịch_ (_interpreted language) và ngôn ngữ biên dịch (compiled language),_ sự khác biệt về hiệu năng giữa Web Assembly và Javascript như so sánh trời với đất, nó gấp rất rất nhiều lần, cũng y như so trình xem HTML của Firefox/Chrome (viết bằng HTML5=HTML+Javascript) với MPV (viết bằng C nguyên chất) vậy.
- Sử dụng IndexedDB thay vì localStorage: IndexedDB có hiệu năng tốt hơn nhiều localStorage nên khi mở Firefox lên, uBlock hoạt động ngay lập tức sau 0.5 s (đối với con máy cùi bép của mình), nhưng với Chrome thì nếu bạn mở ngay trang web, khả năng lớn là quảng cáo sẽ lọt vì Chrome dùng localStorage chứa các bộ lọc của uBlock, nhiều người từng trải nghiệm uBlock trên Chrome tốn 15 phút để load xong các bộ lọc.

Tham khảo: [https://github.com/gorhill/uBlock/wiki/uBlock-Origin-works-best-on-Firefox#browser-launch](https://github.com/gorhill/uBlock/wiki/uBlock-Origin-works-best-on-Firefox#browser-launch) / [https://github.com/gorhill/uBlock/wiki/uBlock-Origin-works-best-on-Firefox#storage-compression](https://github.com/gorhill/uBlock/wiki/uBlock-Origin-works-best-on-Firefox#storage-compression)  
  
(Chi tiết: [https://github.com/gorhill/uBlock/wiki/uBlock-Origin-works-best-on-Firefox#webassembly](https://github.com/gorhill/uBlock/wiki/uBlock-Origin-works-best-on-Firefox#webassembly))  
  
**b) Tính năng:**  
- uBlock của Firefox hỗ trợ bóc tách CNAME của tên miền, giúp tìm ra những tên miền con cùng là một bố mẹ đẻ ra rồi chặt luôn một thể, nên kết quả là uBlock nghiễm nhiên chặn nhiều quảng cáo hơn mà không tốn công sức: [https://github.com/gorhill/uBlock/wiki/uBlock-Origin-works-best-on-Firefox#cname-uncloaking](https://github.com/gorhill/uBlock/wiki/uBlock-Origin-works-best-on-Firefox#cname-uncloaking)
- uBlock của Firefox hỗ trợ lọc nội dung web, giúp thoải mái cắt xén trang web, chặn những quảng cáo mà bình thường không thể chặn được.

Tham khảo: [https://github.com/gorhill/uBlock/wiki/uBlock-Origin-works-best-on-Firefox#html-filtering](https://github.com/gorhill/uBlock/wiki/uBlock-Origin-works-best-on-Firefox#html-filtering) / [Cách sửa mọi thứ trong trang web, phá tan nát trang web, chặn những quảng cáo gần như khó nhất với Header Editor](https://voz.vn/t/tong-hop-nhung-addon-chat-cho-firefox-pc-mobile.682181/post-25364481) / [https://voz.vn/t/tong-hop-nhung-addon-chat-cho-firefox-pc-mobile.682181/post-25473236](https://voz.vn/t/tong-hop-nhung-addon-chat-cho-firefox-pc-mobile.682181/post-25473236)  
  
**2. uBlock (Adblock) Manifest V2 vs uBlock (Adblock) Manifest V3 - Áp dụng cho mọi tiện ích chặn quảng cáo viết bằng Manifest V3**  

- **AdBlock Manifest V3** sẽ không thể tự động cập nhập bộ lọc, trong khi thế giới web các trang web thay đổi cứ vài giây một lần, thêm sửa quảng cáo, không tự động cập nhập được nghĩa là thành phế
- **AdBlock Manifest V3** sẽ không thể có nhiều hơn 30.000 rule (dòng chặn, chi tiết: [MV3: overcoming the 30000 rules limit](https://old.reddit.com/r/uBlockOrigin/comments/xlw1wi/mv3_overcoming_the_30000_rules_limit/)), trong khi số lượng trang web tăng không ngừng mỗi ngày, ngoài ra adblock còn được dùng để chặn các trang có nội dung malware nữa nên thậm chí để an toàn thì một người dùng cần dùng tới hàng triệu rule, ví dụ như chỉ để chặn các tên miền mới tạo ra trong vòng 31 ngày đã ngốn nguyên 3 triệu rule: [**Cách chặn các tên miền mới tạo (thường là lừa bịp, virus) bằng uBlock**](https://voz.vn/t/tong-hop-nhung-addon-chat-cho-firefox-pc-mobile.682181/post-24961417)
- **AdBlock Manifest V 3** sẽ ngưng hoạt động sau khi trang tải xong một thời gian ([**5 phút**](https://old.reddit.com/r/learnjavascript/comments/10jmkc4/how_to_prevent_service_worker_from_going_inactive/)), nghĩa là sẽ vô dụng với các trang web động sử dụng AJAX như Youtube/Facebook vì một lúc sau khi tải xong sẽ không còn chặn quảng cáo nữa, khiến quảng cáo hiện ra
- Còn đây là [**thông tin do chính gorhill cung cấp**](https://old.reddit.com/r/uBlockOrigin/comments/1067als/eli5_ublock_lite_vs_ublock_origin/j3h00xj/).  

> uBO Lite:  
> 
> - Filter lists update only when the extension updates (no fetching up to date lists from servers)
> - Many filters are [dropped at conversion time](https://github.com/gorhill/uBlock/blob/master/dist/mv3/log.txt) due to MV3's limited filter syntax
> - No [crafting your own filters](https://github.com/gorhill/uBlock/wiki/Dashboard:-My-filters) (thus no [element picker](https://github.com/gorhill/uBlock/wiki/Element-picker))
> - No [strict-blocked](https://github.com/gorhill/uBlock/wiki/Strict-blocking) pages
> - No [per-site switches](https://github.com/gorhill/uBlock/wiki/Per-site-switches)
> - No [dynamic filtering](https://github.com/gorhill/uBlock/wiki/Blocking-mode)
> - No [importing external lists](https://github.com/gorhill/uBlock/wiki/Dashboard:-Filter-lists#3rd-party-filter-lists)

**3. uBlock và Adguard**  
Gần như giống nhau, thích dùng gì thì dùng, nhưng uBlock hơn ở hiệu năng do sử dụng Web Assembly, đã được xác nhận đóng dấu trên trang liệt kê các ứng dụng sử dụng Web Assembly (WASM) trên kèm benchmark hiệu năng: [https://madewithwebassembly.com/showcase/ublock-origin/](https://madewithwebassembly.com/showcase/ublock-origin/)  

> uBlock Origin is a very popular add-on, and uses WebAssembly for multiple parts of it's codebase. The most notable being, uBlock Origin uses Wasm for hostname lookup for it's data structures that contain the list of origins it intends to block. This is a great use of WebAssembly, as it offered them better performance, compared to a JavaScript implementation, in the web browser for doing computationally intensive processing tasks over a large set of data. This can be tested in your own browser, by checking out the [benchmark](https://raw.githack.com/gorhill/uBlock/master/docs/tests/hnset-benchmark.html).


## Auto Tab Discard - Tự động unload tab không dùng tới để giảm RAM và CPU
- [I] Firefox hay Chrome đi chăng nữa thì từ khi lên multi-process (đa tiến trình) khi dùng sẽ mở lên rất nhiều process kiểu firefox. Exe hay chrome. Exe, điều này không tốt cả về mặt hiệu năng lẫn bảo mật, mà tính năng unload tab có sẵn trong Firefox rất tệ. Nên việc cài một addon dạng unload tab như Auto Tab Discard để tắt những tab không dùng đi bạn sẽ **tiết kiệm được rất nhiều RAM và CPU** do các trang web chạy ngầm gây ra, ngoài ra khi nội dung web bị loại bỏ khỏi bộ nhớ thì kể cả lỗ hổng bảo mật mang tên Spectre and Meltdown cũng bó tay chịu trói.
### Cách unload tab super ultra vip pro 😀
- Vào `about:memory` rồi chọn GC để Firefox giải phóng bớt RAM thừa đi
- Vào Task Manager thi thoảng thấy có cái process `firefox.exe` nào chiếm RAM thì End Process đi, chú ý không động vào cái firefox.exe cha, chỉ mấy thằng con thôi.
- Vào `about:unloads` rồi nhấp liên hồi vào nút Unload nếu như muốn tự tay unload tab
- Ngoài ra khi dùng Auto Tab Discard, vào `about:config` xóa sạch trong `extensions.webextensions.restrictedDomains` để nó unload tất không khoan nhượng bố con thằng nào cả, mặc định nó bỏ sót rất nhiều trang của Mozilla.

Ngoài ra khi cài xong thì ấn vào biểu tượng của Auto Tab Discard, chỉnh phần "when the number of inactive tabs exceeds" 1 cho nó tắt tab đi thường xuyên hơn, chứ mặc định là 6 là dành cho những ai luôn mở >6 tab, rất nhiều người dùng trình duyệt mở 3-4 tab thôi nên cho thành 1 để nó unload nhiều hơn. Còn đây là ảnh Firefox của mình mở 5568 tab:
![Pasted image 20230901161251.png](/img/user/Extras/Images/Pasted%20image%2020230901161251.png)]] 
