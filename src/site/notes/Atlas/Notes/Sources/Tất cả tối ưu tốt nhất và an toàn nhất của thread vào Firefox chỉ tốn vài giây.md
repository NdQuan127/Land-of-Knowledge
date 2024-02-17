---
{"dg-publish":true,"permalink":"/Atlas/Notes/Sources/Tất cả tối ưu tốt nhất và an toàn nhất của thread vào Firefox chỉ tốn vài giây/","tags":["#on/bt_chiase"]}
---

Tổng hợp tất cả tối ưu tốt nhất của thread trong một file `user.js`, cách sử dụng:  
- `about:support`
- Open Profile Folder
- Tải file **[`user.js`](https://github.com/FirefoxUniverse/FirefoxTweaksVN/raw/main/user.js)** vào folder trên
- Khởi động lại Firefox

**Chú ý:** Phần ép cache chạy trên RAM mình không bật mặc định, anh em muốn bật thì bỏ `//` ở phần dưới của `// Force RAM cache, uncomment // to enable` để bật nhé. Còn nếu dùng trên điện thoại thì không nên bật.

Và thế là xong, chỉ một file `user.js` chứa tất cả tinh hoa bao đời nay của người dùng Firefox và của thread, thao tác chưa tới vài giây là xong.

## Hướng dẫn dùng file user.js để sửa nhanh một loạt cấu hình about:config trên Firefox Android không cần root.

**Bước 1:** Kết nối ADB giữa thiết bị Android và PC. *(cái này anh em search google là thấy cách làm)*

**Bước 2:** Bật Remote debugging via USB trong cài đặt của Firefox Androi. Nhớ bật cả Remote debugging via USB trong mục *Tuỳ chọn nhà phát triển* trong Settings.

**Bước 3:** Trên Firefox desktop, vào `about:debugging`. Nếu mọi thứ đúng thì thiết bị Android sẽ hiện trong list. Bấm Connect.
![Pasted image 20230922234541.png](/img/user/Atlas/Utilities/Images/Pasted%20image%2020230922234541.png)

**Bước 4:** Connect thành công thì bấm phát nữa vào tên thiết bị. Sẽ hiện ra một list các tabs đang được mở. Mở một tab `about:support` trên Android nếu chưa làm.
![Pasted image 20230922234707.png](/img/user/Atlas/Utilities/Images/Pasted%20image%2020230922234707.png)

**Bước 5:** Bấm Inspect để làm việc với trang about:support. Tại đây bấm chọn tab Console.
![Pasted image 20230922234822.png](/img/user/Atlas/Utilities/Images/Pasted%20image%2020230922234822.png)

**Bước 6:** Paste đoạn code này vào rồi Enter chạy luôn. Đoạn code này overide lại những hàm user_pref mà file user.js gọi.
```javascript
var user_pref = function(pref, val){

  try {
    if(typeof val == "string"){

         Services.prefs.setStringPref(pref, val);    
    }
    else if(typeof val == "number"){

         Services.prefs.setIntPref(pref, val);    
    }
    else if(typeof val == "boolean"){

         Services.prefs.setBoolPref(pref, val);    
    }
  } catch(e){
    console.log("pref:" + pref + " val:" + val + " e:" + e);
  }
}
//paste your user.js file content here
```

**Bước 7:** Paste tiếp nội dung file user.js của bạn vào rồi Enter chạy luôn

> Và thế là xong. Disconnect các thứ ra và tận hưởng.😁



