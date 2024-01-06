---
{"dg-publish":true,"permalink":"/Atlas/Notes/Sources/Đặt ngoại lệ antivirus để Firefox không bị hãm tốc độ/","noteIcon":""}
---

up:: [[Atlas/Maps/Firefox MOC\|Firefox MOC]]
tags:: #on/bt_chiase 

# Đặt ngoại lệ antivirus để Firefox không bị hãm tốc độ

**Giải pháp:**  
- Cho Firefox (cả folder chứa firefox.exe và folder profile) vào ngoại lệ của WD để nó không bao giờ động chạm vào Firefox nữa
- Tắt tính năng thời gian thực của WD
- Tắt hoàn toàn WD
Nguồn đây: [https://bugzilla.mozilla.org/show_bug.cgi?id=1441918](https://bugzilla.mozilla.org/show_bug.cgi?id=1441918) (có cái bình luận này [https://bugzilla.mozilla.org/show_bug.cgi?id=1441918#c61](https://bugzilla.mozilla.org/show_bug.cgi?id=1441918#c61) đáng chú ý, tắt cache trên ổ đĩa đi thì CPU hạ hẳn, cũng dễ hiểu vì WD chắc chắn scan cache của Firefox, làm theo bài này mình chỉ cách tắt cache đĩa và dùng cache RAM [https://voz.vn/t/cach-ep-firefox-luu-cache-tren-ram-ma-khong-can-ramdisk.664955/](https://voz.vn/t/cach-ep-firefox-luu-cache-tren-ram-ma-khong-can-ramdisk.664955/))

> Using Process Monitor to count MsMpEng events for 30 seconds after reloading youtube.com (Ctrl+F5) I get the following (numbers are very rough):  
>   
> Firefox (disk cache on): 1300 total events, 800 cache events, 50 files, 3MB  
> Firefox (disk cache off): 300 total events, 0 cache events, 0 files, 0MB  
> Chrome: 500 total events, 90 cache events, 10 files, 2MB  
> Edge: 400 total events, 0 cache events (800 ignored), 45 files, 7MB

  
Theo những gì ông dev của Firefox test, *chỉ có duy nhất Firefox là bị WD scan cache và bị scan nhiều gấp chục lần với 2100 lần với 800 lần bị scan cache, Chrome 590 lần với 90 lần scan cache, Edge 400 lần và không hề bị scan cache, Chrome và Edge không bị nên có thể 30% CPU khi mở tab của bạn là do đây. Nhìn chung WD nó ưu ái Edge nhất. (cạnh tranh bẩn)*  
  
Hình như phía Firefox cũng bó tay rồi, 5 năm rồi không sửa nổi 5 năm bị đì đọt trên Windows. Kiểu cảm giác là lẽ ra Firefox phải hoạt động tầm 30-50% nhanh hơn nhưng vì bị thằng Windows Defender nó ghìm lại nên không hoạt động hết công suất được cũng đau. Cũng phần nào lý giải tại sao mình thấy nhiều người chê Firefox chậm hơn Chrome trong khi mình dùng cả hai thì thấy Firefox nhẹ hơn Chrome.  
  
Hướng dẫn: [https://www.thegioididong.com/hoi-d...s-defender-chiem-qua-nhieu-tai-nguyen-1322722](https://www.thegioididong.com/hoi-dap/cach-sua-loi-windows-defender-chiem-qua-nhieu-tai-nguyen-1322722)  
Chú ý: Đoạn đặt ngoại lệ thư mục thì mở about:support trong Firefox rồi Open Profile Folder sau đó copy đường dẫn folder vào mục ngoại lệ của WD để ngoại lệ hoàn toàn vụ scan cache (cache chả bao giờ nhiễm virus vào máy được đâu nên không lo, vì nó còn chả có đuôi file).  
  
Nói chung kinh nghiệm để sống khỏe với antivirus:  
- Tắt hết tính năng thời gian thực (scan mạng, scan driver..) mà chỉ bật duy nhất tính năng tự động scan khi mở thư mục (tính năng siêu căn bản của antivirus cho những ai cẩn trọng, cứ mở folder cái nó scan toàn bộ folder) và thấy file lạ thì chuột phải vào rồi cho antivirus scan, còn an toàn hơn thì ném vô sandbox.  
  
Chỉ cần như trên là quá an toàn rồi, để nó scan lưu lượng mạng chỉ tốn tài nguyên hệ thống mà chả bao giờ ra virus.  
  
> P/s: Không ngoại lệ thì chả khác gì chấp Edge với Chrome 30% CPU.