---
{"dg-publish":true,"permalink":"/Atlas/Notes/Sources/Sidebery - Quản lý tab dọc với tính tuỳ biến cao/","tags":["on/bt_chiase"]}
---

[**Sidebery**](https://addons.mozilla.org/en-US/firefox/addon/sidebery/): Addon hỗ trợ chơi tab dọc có tính tùy biến rất cao và bắt mắt.
## Tính năng
- Quản lý tab theo nhóm như Tab Group của Chrome
![Pasted image 20230901155731.png](/img/user/Atlas/Utilities/Images/Pasted%20image%2020230901155731.png)

- Tạo bản ghi lịch sử Tab để khôi phục khi cần thiết
![Pasted image 20230901155824.png](/img/user/Atlas/Utilities/Images/Pasted%20image%2020230901155824.png) 

- Nhiều tuỳ biến thay đổi giao diện từ cơ bản đến nâng cao
![Pasted image 20230901155940.png](/img/user/Atlas/Utilities/Images/Pasted%20image%2020230901155940.png)

## Ẩn/hiện thanh tab ngang cho gọn vì Sidebery bao tab dọc (dùng userChrome.css)
>[!Warning]
>Nếu dùng floorp thì chỉ cần vô Settings chọn Optimise browser for Vertical Tab Bar là được

Copy chỗ này vào file userChrome.css:
```javaScript
/* Source file https://github.com/MrOtherGuy/firefox-csshacks/tree/master/chrome/autohide_tabstoolbar.css made available under Mozilla Public License v. 2.0
See the above repository for updates as well as full license text. */

/* Hide tabs unless cursor is on top of toolbar */

:root:not([customizing]) #navigator-toolbox{
  position: relative;
  z-index: 1;
}

#navigator-toolbox:not(:hover) > #titlebar{
  -moz-window-dragging: no-drag !important;
  pointer-events: none
}

:root:not([customizing]) #navigator-toolbox:hover,
:root:not([customizing]) #titlebar{
  margin-bottom: calc(0px - 2 * var(--tab-block-margin) - var(--tab-min-height));
}
#TabsToolbar:not([customizing]){ visibility: hidden; transition: visibility 0ms linear 200ms }

#navigator-toolbox,
#titlebar{ transition: margin-bottom 48ms ease-out 200ms }

#navigator-toolbox:hover{ transition-delay: 0s }
#navigator-toolbox:hover > #titlebar{
  margin-bottom: 0px;
  transition-delay: 0s;
}

#navigator-toolbox:hover #TabsToolbar{
  visibility: visible;
  transition-delay: 18ms
}
/* These rules make sure that height of tabs toolbar doesn't exceed tab-min-height */
#tabbrowser-tabs:not([secondarytext-unsupported]) .tab-label-container{
  max-height: var(--tab-min-height);
}
.tab-label{ line-height: 20px !important; }
:root[uidensity="compact"] .tab-label{ line-height: 18px !important; }
```

*Tab ngang sẽ bị ẩn tạm thời đi, di chuột lên là hiện tuy nhiên mục đích ở đây là chơi 100% tab dọc.*

> **Hướng dẫn cách sử dụng userChrome.css**

Bật userChrome.css bằng cách vào about: config tìm `toolkit.legacyUserProfileCustomizations.stylesheets` chỉnh thành true 

Vào `about:support` rồi Open Containing Folder, tạo folder `chrome`, tạo file `userChrome.css` bên trong folder vừa tạo.

**Đây là kết quả khi ẩn cả tab ngang và tab dọc (tab dọc anh em có thể ẩn hiện nó bằng phím F1 để cho tiện)**
![Pasted image 20230901160906.png](/img/user/Atlas/Utilities/Images/Pasted%20image%2020230901160906.png)

## Auto Hide Sidebar như Edge
>[!Note]
>Vào about:support -> `Open Profile Folder` -> Vô folder `Chrome` -> Vô tiếp folder `CSS` -> Paset code dưới vào 
>Link tải: [colorful-minimalist/hacks/sideberyModsLeftSlide.css at main · Redundakitties/colorful-minimalist · GitHub](https://github.com/Redundakitties/colorful-minimalist/blob/main/hacks/sideberyModsLeftSlide.css)

Đọc thêm bài này để có thể kiếm được vài cái hay ho để tùy biến Firefox: [[Atlas/Notes/Sources/Giới thiệu và một số cách sử dụng userChrome.js\|Giới thiệu và một số cách sử dụng userChrome.js]]

>[!Warning]
>Muốn xóa cái này cho đỡ ngứa mắt ![Pasted image 20240228211824.png](/img/user/Atlas/Utilities/Images/Pasted%20image%2020240228211824.png) thì vô `userChrome.css` dán đoạn code này vô
>

```css
#sidebar-header {

  display: none!important;

}
```
