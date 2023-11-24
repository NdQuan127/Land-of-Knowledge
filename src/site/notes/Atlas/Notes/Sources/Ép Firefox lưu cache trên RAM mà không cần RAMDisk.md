---
{"dg-publish":true,"permalink":"/atlas/notes/sources/ep-firefox-luu-cache-tren-ram-ma-khong-can-ram-disk/"}
---

up:: [[Atlas/Maps/Firefox MOC\|Firefox MOC]]
tags:: #on/bt_chiase 

Mở đầu là cách chuyển cache (bộ nhớ đệm) của Firefox lên RAM hết. Như cái bạn biết khi các bạn vào Facebook, Youtube hay gì gì thì trình duyệt sẽ tải các file .js, .css, .json, ảnh... vào thư mục cache, điều này không thực sự tốt cho ổ cứng SSD, cũng như RAM thời nay rẻ như bèo, nên chuyển hết cache lên RAM thì sẽ đạt hiệu năng cao hơn.  
  
Mà Firefox thì hay hơn Chrome rất nhiều vì có thể bê nguyên cache lên RAM mà KHÔNG cần phải cài RAMDisk, để làm được như vậy các bạn làm như sau, rất ngắn thôi vì là thread khởi đầu series:  
  
Trên thanh địa chỉ gõ: `about:config`. Rồi chọn I Understand gì gì đó, sau đó ở khung tìm kiếm gõ cache rồi tìm **browser.cache.disk.enable** chuyển giá trị thành **false**, tiện đó kiểm tra xem **browser.cache.memory.enable** đã là **true** chưa, nếu chưa **true** thì chuyển thành **true**.  
  
Tiếp theo ấn chuột phải vào giữa about: config, Add -> Integer và tạo một khoá tên **browser.cache.memory.capacity** (nếu có sẵn, các bạn search **browser.cache.memory.capacity** rồi nháy đúp vào rồi thay giá trị thay vì tạo mới như mình nhé) và gắn cho nó một con số nào đấy như:  

- An toàn: 1048576 (giá trị này tính bằng KB, nghĩa là 1GB)
- Firefox 32bit: nếu dùng Firefox bản 32bit thì đặt là 524288 (512MB) thôi vì ứng dụng 32bit có giới hạn số RAM (xấp xỉ 4GB) mà cứ vượt ngưỡng là sẽ treo ứng dụng (vì ở đây còn phải tính tới số RAM mà trang web đòi hỏi để render trang nữa, có những trang web siêu nặng như Youtube hay Facebook chỉ mở một tab là đi tong 1GB RAM nếu không dùng uBlock chặn quảng cáo)
- Firefox 64bit + nhà đẻ ra RAM: Nếu có nhiều RAM tầm 16GB+ đặt 2-4GB (2097152-4194304)

  
Và tìm tiếp **browser.cache.memory.max_entry_size** chuyển thành 512000 (mặc định là 5120 quá ít, vô dụng) để nó tính số lượng file cache được lưu vô RAM nhé.  
  
Vậy là xong rồi, vào đại một trang web nào đó rồi mở about:cache lên sẽ thấy tất cả cache được chuyển qua RAM hết, vậy là từ nay SSD sẽ không bị đọc ghi bởi Firefox nữa, cũng như tốc độ tải cache cũng sẽ tăng đặc biệt nếu bạn dùng HDD mà có nhiều RAM.  
  
**Chú ý là tối ưu cho cache lên RAM sẽ hiệu quả nhất nếu bạn tạo thói quen không tắt Firefox thường xuyên, dữ liệu trên RAM tuy nhanh hơn cả SSD nhưng khi tắt Firefox sẽ mất hết, hiện tại Firefox đã tối ưu cho việc mở hàng tháng trời không cần tắt nên tắt đi bật lại không khiến Firefox nhanh hơn mà chỉ phí thời gian bật lên lại.**  
  
> **Vì một hệ sinh thái Firefox xanh sạch đẹp.**

### Mở rộng

> RCWN vậy, gọi nôm na là **tính năng chạy đua giữa cache và tốc độ mạng**, nhiều **khi dùng HDD cùi thì việc máy có hàng tỉ cache sẽ truy xuất rất làm chậm**, khi **tắt RCWN đi và tắt cache trên ổ đĩa thì Firefox sẽ chỉ chú tâm vào RAM** thôi.

Cách thức thực hiện thì gõ `about:config` rồi Enter, sau đó tìm và chỉnh:  

|   |   |
|---|---|
|network.http.rcwn.enabled|false|

Vậy là từ nay Firefox sẽ chỉ chung thủy sắt son với RAM thôi chứ không có ý định ngoại tình với mạng.