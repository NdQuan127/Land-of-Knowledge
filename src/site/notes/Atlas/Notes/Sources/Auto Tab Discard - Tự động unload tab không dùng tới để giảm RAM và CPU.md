---
{"dg-publish":true,"permalink":"/atlas/notes/sources/auto-tab-discard-tu-dong-unload-tab-khong-dung-toi-de-giam-ram-va-cpu/"}
---

up:: [[Atlas/Maps/Firefox MOC\|Firefox MOC]]
tags:: #on/firefox 

# Auto Tab Discard - Tự động unload tab không dùng tới để giảm RAM và CPU

> Nếu anh em dùng Floorp thì không cần cài addon này, vì nó đã được native sẵn trong browser vào settings tìm là thấy.

- [I] Firefox hay Chrome đi chăng nữa thì từ khi lên multi-process (đa tiến trình) khi dùng sẽ mở lên rất nhiều process kiểu firefox. Exe hay chrome. Exe, điều này không tốt cả về mặt hiệu năng lẫn bảo mật, mà tính năng unload tab có sẵn trong Firefox rất tệ. Nên việc cài một addon dạng unload tab như Auto Tab Discard để tắt những tab không dùng đi bạn sẽ **tiết kiệm được rất nhiều RAM và CPU** do các trang web chạy ngầm gây ra, ngoài ra khi nội dung web bị loại bỏ khỏi bộ nhớ thì kể cả lỗ hổng bảo mật mang tên Spectre and Meltdown cũng bó tay chịu trói.

### Cách unload tab super ultra vip pro 😀
- Vào `about:memory` rồi chọn GC để Firefox giải phóng bớt RAM thừa đi
- Vào Task Manager thi thoảng thấy có cái process `firefox.exe` nào chiếm RAM thì End Process đi, chú ý không động vào cái firefox.exe cha, chỉ mấy thằng con thôi.
- Vào `about:unloads` rồi nhấp liên hồi vào nút Unload nếu như muốn tự tay unload tab
- Ngoài ra khi dùng Auto Tab Discard, vào `about:config` xóa sạch trong `extensions.webextensions.restrictedDomains` để nó unload tất không khoan nhượng bố con thằng nào cả, mặc định nó bỏ sót rất nhiều trang của Mozilla.

Ngoài ra khi cài xong thì ấn vào biểu tượng của Auto Tab Discard, chỉnh phần "when the number of inactive tabs exceeds" 1 cho nó tắt tab đi thường xuyên hơn, chứ mặc định là 6 là dành cho những ai luôn mở >6 tab, rất nhiều người dùng trình duyệt mở 3-4 tab thôi nên cho thành 1 để nó unload nhiều hơn. Còn đây là ảnh Firefox của mình mở 5568 tab:
![Pasted image 20230901161251.png](/img/user/Atlas/Utilities/Images/Pasted%20image%2020230901161251.png)