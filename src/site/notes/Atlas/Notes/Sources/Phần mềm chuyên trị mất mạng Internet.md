---
{"dg-publish":true,"permalink":"/Atlas/Notes/Sources/Phần mềm chuyên trị mất mạng Internet/"}
---

up:: [[Atlas/Maps/Bí thuật MOC\|Bí thuật MOC]]
tags:: #on/bt_keyngon 

# Phần mềm chuyên trị mất mạng Internet
> Khuyên anh em nên tải về thủ sẵn trong máy sẽ rất hữu dụng     (～￣▽￣)～

Lang thang Internet thấy phần mềm này rất hay nên phải share ngay cho nóng. Phần mềm này free, chạy dưới dạng portable (có loại cài đặt nhưng mình nghĩ không cần thiết). Phần mềm này rất tiện cho mấy anh em từ gà đến nhập môn, tự nhiên đang dùng mất mạng Internet thì chỉ cần bật lên chạy phát là có mạng Internet ngay (_nguyên nhân do máy anh em thôi nhé, chứ còn do Router/Modem hoặc do thằng Cafe Internet thì chịu_). Điểm mình thích nhất ở phần mềm này là nó thay thế được cả tá lệnh mà ngày xưa mình phải gõ bằng tay như: ipconfig /release, ipconfig /flushdns, ipconfig /renew, netsh int ip reset, netsh winsock reset, nbtstat -R, nbtstat -RR, arp -d, netsh advfirewall reset, netsh winhttp reset proxy... Ngắn gọn, nó thay anh em phát ra hàng chục lệnh reset cấu hình mạng mức hệ thống, một đập ăn luôn.

Tất nhiên cái này gặp thợ thì họ không cần phần mềm này, vì họ sẽ tự gõ lệnh, nhưng là thợ già thôi, chứ mấy ông thợ non loay hoay một lúc rồi đề nghị... cài lại win (thuốc chữa cho mọi lỗi ![😁](https://static.xx.fbcdn.net/images/emoji.php/v9/ta8/1.5/16/1f601.png))

Vì thế, anh em nhập môn thì nên lưu phần mềm này lại, mỗi lần lỗi mạng thì chạy thử rồi sau đó **KHỞI ĐỘNG LẠI** máy tính. Ít ra loại trừ được lỗi phần mềm và cấu hình sai.

Dùng phần mềm này cần lưu ý:

1. Phần mềm này chỉ chữa được các lỗi liên quan đến phần mềm. Các lỗi liên quan đến phần cứng như driver card mạng, card mạng lỗi, dây mạng lỗi... thì nó KHÔNG giúp được gì.
    
2. Phần mềm này chỉ thích hợp với anh em đang xài máy cá nhân. Với các anh em xài máy công ty, có các setting riêng do tập đoàn đặt như firewall, dns, proxy.... sẽ KHÔNG thích hợp vì nó sẽ reset tất cả về mặc định hết.
    
3. Anh em nên chạy phần mềm này với quyền admin, vì một số lệnh mà nó thay mình phát ra phải quyền admin mới ăn.  

> Link tại [**đây**](https://l.facebook.com/l.php?u=https%3A%2F%2Fjustpaste.it%2F4xjhu%3Ffbclid%3DIwAR3zt0LpJ3tb7KSyLH3ruK73pe1wp9gAP0tTKuQjny3KNfsey3qPLf5Wbxk&h=AT3VqCC1O1YHki7TADpl4oLoJQoOqXUe5uZiEu0-sTCFL31P4-u9GIpr0MdBH9FDNuM6i9gTfQ90KUBsz8CBIUt39SgNzGQLHyq9zrMU2X2Ot06jxuTLJXsIsiSvaKZih5A3m7yAxr6_6-o-h2KkM-DaJbnqx8hKPRBrlap3zIGOtg18Y6cpgl2x9cIrAEJwhSgwFkpmU3WRqmHifgOR-zAimR9Ge2xGx0Ps_JmcycEL9bZZzw&__tn__=-UK-R&c[0]=AT0f4PYJA6VjrvY2DnBCdUVHxUykZ2cwyDMvo9cBjpJsoEn4eBvRJOxZt01TlGPZKSEAFrhmLdFFarIwYvz-BN3sEmbbve6yK5W1Hp2opoyQQKDtHJhZghKaML8L_pjTT4Myy0Ssr5zYJNtLR0Gn99wgAoifAGB4fafxUSs) nhé