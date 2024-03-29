---
{"dg-publish":true,"permalink":"/Atlas/Notes/Sources/1001 câu hỏi về Testflight của Apple/"}
---

up:: [[Atlas/Maps/Bí thuật MOC\|Bí thuật MOC]]
tags:: #on/bt_chiase 

# 1001 câu hỏi về Testflight của Apple

1. **Testflight là gì?** Nó là môi trường test, chạy thử app trước khi tung ra môi trường thật: App Store.
    
2. **Tại sao nó miễn phí?** Đúng ra mà nói thì tụi DEV (nhà phát triển) phải trả tiền cho người test, hơn nữa phải trả rất nhiều tiền, chứ đừng nói là thu tiền của anh em, vì môi trường test app sẽ nhiều bug, không ổn định, gây phiền hà, mất thời gian cho người dùng. Vì thế, việc miễn phí phần mềm Testflight thực ra là câu chuyện win-win, đôi bên cùng có lợi, người dùng thì được dùng miễn phí, bên DEV thì có người test (quan trọng là không bị rằng buộc gì về pháp lý khi có sự cố xảy ra với người dùng: mất thời gian, mất dữ liệu...)
    
3. **Mỗi lần mua subscription trên Testflight có bị tính tiền không?** Tuyệt đối không, Apple không cho phép lấy tiền trên môi trường Testflight, nếu DEV nào vượt qua được rào cản đó để lấy dù chỉ 1 xu của người dùng, điều đó có nghĩa DEV đó đã h@ck thành công hệ thống Apple, môi trường test của Apple sụp đổ, việc mà Apple không bao giờ cho phép, hoặc cố gắng bảo vệ.
    
4. **Nếu đã không cho phép lấy tiền trên Testflight, tại sao không bỏ luôn mục thanh toán (tính tiền đi)?** Bản thân cả DEV và Apple đều muốn test mục thanh toán này, một app dù ngon đến mấy mà mục thanh toán không tốt (không lấy được tiền, hoặc bị h@ck, hoặc tính sai tiền...) thì cũng vứt đi, vì thế hạn mục thanh toán lại là bị test nhiều nhất. Lý do tại sao Testflight không lấy một đồng nào của anh em, nhưng vẫn bắt anh em đăng ký, thanh toán như thật.
    
5. **Có nên dùng Testflight không?** Có mà lại Không. Ví dụ, anh em cần một phần mềm lên kế hoạch làm việc, mỗi ngày anh em kiếm vài trăm USD, lỡ một cuộc họp là tổn thất vài nghìn, thậm chí nhiều hơn. Anh em không có thời gian để đối phó với những bug do phần mềm test tạo ra... Thời gian là tiền bạc. Trong trường hợp đó, rõ ràng là Không, anh em sẵn sàng bỏ ra vài chục USD để có phiên bản ổn định nhất có thể. Nhưng nếu anh em đang là sinh viên, freelancer... chẳng có lý do gì không dùng Testflight cả, vừa miễn phí, vừa được trải nghiệm tính năng P̶r̶e̶m̶.̶i̶u̶m̶ của phần mềm.
    
6. **Testflight nào đáng giá nhất?** các dịch vụ như kiểu **Dropbox, Scribd, VPN...** là đáng giá nhất, vì họ muốn anh em test app trên iPhone, nhưng vì thế họ lại phải cấp cho anh em tài khoản Prenium để dùng trên app đó, nhưng nhiều anh em có được tài khoản rồi, mang ra chỗ khác dùng, không dùng trên app đó, cái đó thì họ không khống chế được. Vì thế, anh em được dùng dịch vụ Prenium miễn phí, chả khác gì dịch vụ họ đang kinh doanh thực sự cả. Ví dụ, trường hợp của **Dropbox** cái họ muốn là anh em test giúp họ *app Dropbox trên iPhone, nhưng 99% anh em ở đây không ai test giúp họ cả, mà lấy acc Dropbox ra dùng trên máy tính khác, trường hợp của Scribd cũng tương tự như thế.* 
    
7. **Thời hạn 90 ngày là gì? Thời hạn dùng app đó à?** Đây là thời hạn Apple qui định cho các App test, tối đa sau 90 ngày là phải cập nhập app test bắt buộc, nhưng thường thì các DEV họ cập nhập sớm hơn thời hạn này (fix được lỗi bự là cập nhật luôn). Nhưng thằng lười nhất thì sau 90 ngày cũng phải cập nhật app mới, không liên quan gì đến thời hạn dùng app của anh em. Thường thì nếu anh em đã đăng ký được một slot test là dùng mãi, trừ khi anh em bấm vào nút rời khỏi: **stop testing** (dừng kiểm tra).