---
{"dg-publish":true,"permalink":"/Atlas/Notes/Sources/Giới thiệu và một số cách sử dụng userChrome.js/","tags":["on/firefox"]}
---

# Giải thích ngắn gọn 
Inject code JavaScript, chạy trên ngữ cảnh của Firefox browser. Tức là can thiệp trực tiếp vào code logic của FIrefox.  

Để so sánh thì các script chạy trên Violentmonkey chỉ hoạt động trên ngữ cảnh của trang web, không tác động được vào browser. Các Addon thì chỉ sử dụng những API mà Firefox expose ra, nên tác động hạn chế.  

Về cơ bản các userChromeJS script sẽ không có hạn chế gì cả. Tác động được vào tất cả các phần viết bằng JavaScript của Firefox (còn các phần khác viết bằng C++ hay các ngôn ngữ khác thì không được). Ngoài ra các script này còn có toàn quyền đọc/ghi trên ổ cứng của bạn. **Cực kỳ nguy hiểm. Phải kiểm tra rất cẩn thận trước khi sử dụng.**  
  
Có 3 bộ autoconfig để load userChromeJS đáng chú ý là:
1. [firefox-scripts](https://github.com/xiaoxiaoflood/firefox-scripts) của xiaoxiaoflood  
2. [fx-autoconfig](https://github.com/MrOtherGuy/fx-autoconfig) của MrOtherGuy, cũng là tác giả của nhiều [tweak css](https://github.com/MrOtherGuy/firefox-csshacks). Có nhiều scripts dựa trên loader này nằm trên repo [uc.css.js](https://github.com/aminomancer/uc.css.js) của aminomancer.  
3. [userChrome.js](https://github.com/alice0775/userChrome.js) của alice0775, người Nhật nên đọc comment code cũng vất vả xíu.

# Một vài cách sử dụng userChrome
## Nút tắt/bật quản lý addon
- Đầu tiên là cái Loader của MrOtherGuy
	- Vào [GitHub - MrOtherGuy/fx-autoconfig: Load custom javascript in browser context](https://github.com/MrOtherGuy/fx-autoconfig)
	- Clone repo về máy
	- Vào folder tên `program`, bôi đen folder `defaults` và file `config.js`, rồi Copy
	- Trên Firefox vô `about:support` rồi nhìn ở phần `Application Binary`, mở cái folder chứa `firefox.exe` lên
	- Paste vào
	- Về lại repo clone về, vào folder tên `profile` vào Copy folder `chrome`
	- Lại vào `about:support`, ấn `Open Profile Folder`
	- Paste

-  Rồi, đơn giản lắm giờ cài script Extension Option Panel thôi:
	- `about:support`
	- Open Profile Folder
	- Vào thư mục `chrome`
	- Vào thư mục `JS`
	- Vào [https://github.com/aminomancer/uc.css.js#extension-options-panel](https://github.com/aminomancer/uc.css.js#extension-options-panel)
	- Tải thẳng vào folder `JS` bên trên
	- Save

Khởi động lại là xong (tốt nhất là dùng `about:support` -> `Clear startup cache...` để Firefox đào thải cache cũ khiến Loader không nạp được), kết quả y như sau: ![Pasted image 20240228212359.png](/img/user/Atlas/Utilities/Images/Pasted%20image%2020240228212359.png)

## MouseGesture
Lướt web bằng chuột xịn hịn nhất quả đất, có thể sử dụng được trên cả những trang mà addon có chức năng tương đương khác không dùng được.

Tải thẳng file này [**MouseGestures2_e10s.uc.js**](https://raw.githubusercontent.com/alice0775/userChrome.js/master/117/MouseGestures2_e10s.uc.js) vào thư mục `JS`. Khởi động lại Firefox/Floorp

>[!Sparkle] Source
>
>