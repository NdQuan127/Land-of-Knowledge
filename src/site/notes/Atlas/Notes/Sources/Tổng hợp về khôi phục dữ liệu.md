---
{"dg-publish":true,"permalink":"/Atlas/Notes/Sources/Tổng hợp về khôi phục dữ liệu/"}
---

up:: [[Atlas/Maps/Bí thuật MOC\|Bí thuật MOC]]
tags:: #on/bt_chiase 
# Tổng hợp về khôi phục dữ liệu

## Nguyên lý khôi phục HDD
### Nguyên lý đọc/ghi/xoá của ổ cứng
- Khi **GHI** (write) 1 file dữ liệu trên ổ cứng, hệ thống sẽ ghi thực tế file đó lên ổ cứng, sau đó quay về bản **FAT** *(tạm hiểu là bản đồ ổ đĩa)* ghi lại thông tin như kiểu file này nằm ở vị trí nào, chiếm bao nhiêu ô (block)

- Khi **ĐỌC** (read) 1 file dữ liệu, thay vì tìm kiếm trên toàn bộ ổ đĩa, hệ thống sẽ tìm đến bản **FAT** để xem file đó ở vị trí nào, sau đó đến trực tiếp vị trí đó để đọc file. Chính nhờ nguyên tắc này mà tốc độ tìm kiếm, truy vấn dữ liệu tăng lên 1 cách khủng khiếp.
> Nếu ví von file là những ngôi nhà, folder là những khu phố thì bản FAT chính là bản đồ thành phố

- Khi **XOÁ** (delete) 1 file dữ liệu, thay vì đi tìm file đó để xoá thì hệ thống sẽ chỉ quay về bản **FAT**, xoá ten file đó trên **FAT** *(bản đồ ổ đĩa)*. Có người sẽ thắc mắc tại sao không xoá đi trực tiếp file đó trên ổ cứng ? Thì vấn đề là không cần thiết, hệ thống chỉ cần xoá trên bản **FAT**, phần ổ cứng bị chiếm dụng sẽ được đánh dấu là *đất hoang*. Và lần tới, hệ thống muốn ghi file mới chỉ cần ghi đè lên phần *đất hoang* đó là được. Vì thế nếu ai tinh ý sẽ nhận ra là quá trình xoá rất nhanh khi so với quá trình ghi.

### Vậy khôi phục dữ liệu thế nào ?
> Dựa vào nguyên tắc bên trên thì file sẽ không thực sự bị xoá mà vẫn nằm trên ổ đĩa.

> **Phần mềm khôi phục sẽ làm gì ?**
> Nó sẽ bỏ qua không đọc bản FAT mà sẽ trực tiếp quét trên ổ đĩa, tìm ra file thực sự. Vì thế quá trình này khá mất thời gian. 

#### Yếu tố nào ảnh hưởng đến xác suất khôi phục
- *Vẫn tiếp tục sử dụng máy tính sau khi xoá:* Như đã phân tích bên trên khi file bị xoá, thì dữ liệu vẫn còn đó, nhưng vùng đất này đã trở thành *đất hoang* sẵn sàng cho 1 lệnh ghi đè mới. Khi có bất kỳ lệnh ghi đè nào lên vùng đất hoang này thì khả năng khôi phục gần như bằng 0. Đây chính là phương pháp các trung tâm tài chính, quân đội,... dùng để tránh việc dữ liệu có thể bị khôi phục, rò rỉ ra ngoài: **ghi đè** *(dĩ nhiên cách họ ghi đè phức tạp hơn nhiều, nhưng về cơ bản là thế.)*

- *Tránh cài trực tiếp phần mềm khôi phục lên ổ cứng cần khôi phục:* Đây là cái rất nhiều người mắc phải. Ví dụ ổ cứng cần khôi phục là ổ C, khi cài luôn phần mềm lên ổ C, thì kết quả là chính phần mềm này đã ghi đè lên dữ liệu cần khôi phục. Khiến khả năng khôi phục bé đi rất nhiều hoặc khôi phục được thì mở ra toàn rác.

#### Cần làm gì khi dữ liệu bị xoá nhầm
- Ngừng sử dụng máy tính, ngừng càng sớm, xác suất khôi phục càng cao.
- Backup ổ cứng có dữ liệu cần khôi phục *(dùng phần mềm Disk Image or Disk Clone)* để phòng trường hợp thất bài, thì nhờ cao thủ khác vẫn có cơ hội phục hồi.
- Sử dụng phần mềm từ USB cứu hộ, hoặc Portable.
- Sau khi khôi phục được thì copy file đó ra ổ khác, tốt nhất là ổ cứng ngoài.

