---
{"dg-publish":true,"permalink":"/encounters/huong-dan-tu-fix-bug-firefox/"}
---

up:: [[Atlas/Firefox MOC\|Firefox MOC]]
tags:: #on/firefox 

# Hướng dẫn tự fix bug Firefox

> [!note]
> Đây là một bài viết mà sau khi đọc xong bạn có một cái nhìn toàn tổng về profile của Firefox, giúp bạn xoay sở trong những tình huống khó nhất. 
## Đầu tiên là tìm bug và fix nó

- **Nếu tự dưng trang web lỗi mà:** 
	- Có bật Resist Fingerprint
	- Có cài Decentaleyes hoặc LocalCDN
=> Thì cứ đè đầu mấy thằng này ra mà xử lý trước.

- **Nếu không cài 2 thằng trên thì:**
	- Vào `about:profile` -> Tạo 1 profile mới -> Mở profile đấy lên kiểm tra xem web còn lỗi không ?

- **Nếu mà không bị lỗi ở profile mới mà profile đang dùng bị có 2 nguyên nhân:**
	- Addon gây ra: Vào `about:profiles` và Restart with addon disabled, được thì do addon thử tắt từng cái đi
	- `about:config` gây ra: `about:support` Open Profile Folder, "tắt Firefox đi" (phải làm), tìm file prefs.js rồi đổi tên nó thành prefs2.js rồi thử lại, nếu bị do chỉnh sửa `about:config` gần đây.

>  Đây là 2 bước debug Firefox cực chuẩn, ai cũng có thể tự debug ra chính xác nguyên nhân ![:D](https://data.voz.vn/styles/next/xenforo/smilies/popo/biggrin.png?v=01 "Big grin    :D")

## Nếu Firefox bị hỏng nặng thì sao?

> [!info] Answer
>   Vậy thì hãy tạo 1 profile mới sao cho vẫn giữ được 90% dữ liệu.

- *Mục tiêu:*  
	- Giữ được bookmark, history
	- Giữ được mật khẩu
	- Giữ được đăng nhập
	- Giữ được Search Engine (bộ công cụ tìm kiếm)
	- Giữ được `about:config`
	- Giữ được addon đã cài (tuy nhiên mất hết tùy chỉnh của addon)

- Cách thức (chú ý khi mình bảo **Tắt Firefox**, bước này vô cùng quan trọng để đảm bảo profile khi copy qua lại được toàn vẹn bởi khi Firefox đang bật là lúc không an toàn khi copy **bởi Firefox liên tục đọc ghi trong khi bật, rủi ro hỏng là có thể**):
	- `about:support`
	- Open Profile Folder
	- **Tắt Firefox**
	- Copy những file sau **(nếu không thấy cứ bỏ qua)**:
		- `places.sqlite` (bookmark+history)
		- `cookies.sqlite` (đăng nhập)
		- `cert9.db` + `key4.db` + `logins.json` (mật khẩu)
		- `extension-preferences.json` + `extensions.json` + `extension-settings.json` + thư mục `extensions` (addon)
		- `search.json.mozlz4` (bộ công cụ tìm kiếm)
		- `prefs.js` (`about:config`)
		- Ngoài ra nếu muốn giữ tùy chỉnh addon *(không dám chắc 100%)*: Copy thư mục `storage` *(tốt nhất nếu không bận thì các thím nên tự tuỳ chỉnh lại addon bằng cách vào profile bị hỏng rồi vô từng addon như violent monkey, ublock,... rồi export data ra rồi lại import lại thì sẽ đỡ lỗi hơn)*
		- Nếu muốn giữ giao diện: Copy thư mục `chrome`

> Tạo profile mới bằng cách vào `about:profiles` -> Create a new profile -> Chọn thư mục -> Launch profile -> `about:support` -> Open Profile Folder -> Tắt Firefox -> Paste vào.  
  
> **Đừng quên `Set as Default Profile` cho cái profile mới tạo để từ nay nó là profile chính.**  
  
Vậy thôi, nó đơn giản nhưng mà không biết lại sợ không dám thử, nhưng biết rồi thấy ez vê lù thôi, khi nào profile có hiện tượng lạ hẵng làm còn không thì không quan tâm tới bài này, nhưng nó vẫn hữu ích trong trường hợp kiểu copy mật khẩu máy này qua máy khác, profile này qua khác, nghĩa là khi biết file nào làm nhiệm vụ nào thì khi đó dễ xoay sở như trên đề cập. ![:D](https://data.voz.vn/styles/next/xenforo/smilies/popo/biggrin.png?v=01 "Big grin    :D")