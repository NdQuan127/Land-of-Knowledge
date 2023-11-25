---
up: "[[Home]]"
related:
  - "[[Add]]"
  - "[[Communicate]]"
created:
  - 24-11-2023
tags:
  - map/view
cssclasses: []
dg-publish: true
---

>[!Info] **Relate** là một nơi vui vẻ - không có bất kỳ kỳ vọng hay nghĩa vụ gì.

>[!Note] Đây là cách nó hoạt động: Khi bạn đang ở trong một ghi chú và cảm thấy rằng muốn quay lại nó - *vì một lý do mơ hồ hoặc rõ ràng nào đó* -  chỉ cần thêm tag vào trong ghi chú. Sau đó thông qua *magic of data views*, bạn có thể sử dụng auto-updating lists để tìm nó:

> [!Multi-column] 
> 
> > [!Sailboat]+ ## Boats 🚤
> > Có lẽ bạn đã viết những ghi chú này một cách vội vã. Những [[BOAT notes]] này như *những con thuyền cô đơn lênh đênh trên một đại dương trống rỗng*. Tất cả những gì bạn cần làm là kết nối chúng với các ghi chú khác.
> > 
 > > ```dataview
> > LIST
> > FROM #note/boat🚤 
> > SORT file.cday desc
> > LIMIT 10
> > ```
> > This sorts up to the most recent `10`.

> [!Multi-column] 
> 
> > [!Leaf]+ ## Develop 🍃
> > Bạn có thể phát triển những ghi chú này bằng cách đưa ra nhận xét, làm rõ và phê bình. Thêm ý kiến của bạn và nếu cần thì hãy trích dẫn nguồn.
> > 
> > ```dataview
> > LIST
> > FROM #note/develop🍃 
> > SORT file.cday desc
> > LIMIT 10
> > ```
> > This sorts up to the most recent `10`.
> > 

---


