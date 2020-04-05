---
title: Các định luật phần mềm – Phần 2
date: 2020-04-05 03:59:20
category: software
tags: 
    - principle
    - production
---

## Định luật murphy

Một định luật vô cùng nổi tiếng khác mà có lẽ tất cả mọi người đều biết, nhưng không phải ai cũng hiểu rõ về nó đó chính là định luật murphy. Được phát biểu như sau:

>If anything can go wrong, it will.
>Nếu một việc có thể diễn tiến xấu, nó sẽ diễn tiến đúng như thế

<!--more -->
Định luật này còn được gọi là Định luật bánh bơ và được được nhận giải IG nobel vào năm 2003. Nó được chuyên gia tên lửa A. Murphy phát biểu vào năm 1949 . Nó nguồn gốc từ một nghiên cứu của không quân Mỹ về tác dụng của quá trình giảm tốc nhanh trên các phi công. Người tình nguyện bị buộc trong xe trượt tuyết gắn động cơ phản lực, và phản ứng của họ khi xe dừng đột ngột sẽ được ghi lại nhờ hệ thống điện cực gắn khít vào bộ ghế ngồi do đại úy Edward A. Murphy thiết kế. Tuy nhiên, Murphy đã không ghi được số liệu nào sau một thử nghiệm tưởng chừng không có sai sót. Thì ra, một điện cực bị mắc sai. Sai lầm hy hữu này khiến Murphy phải thốt lên: _“Nếu trong nhiều cách có một cách sai – sẽ có người thực hiện cách sai đó”_.

Đã bao giờ bạn đi ra đường, đến công ty và gặp cảnh tắc đường, bạn thấy như thế và quyết định rằng sẽ chọn một con đường vòng mà có khả năng nhanh hơn, tuy nhiên vẫn lo ngại rằng có thể nó cũng bị tắc, và thực tế rằng con đường mới bạn chọn cũng tắc khiến bạn có thể còn chậm hơn. Hoặc có rất nhiều lần những điều bạn lo sợ đã xảy ra. Tôi tin rằng điều đó với ai cũng có. Có nhiều người cho rằng đó là định luật chi phối mọi thứ. Vậy liệu nó có bí ẩn gì đằng sau không. Và có rất nhiều người sau khi trải qua một vài điều như thế bắt đầu tin vào số mệnh. Vậy sự thật là gì? Chúng ta sẽ nhìn định luật murphy dưới con mắt của các nhà khoa học như sau:

![](https://c2.staticflickr.com/6/5622/30470247666_2c17a9514f_o.jpg)

Sau một nghiên cứu và cố gắng định lượng phương trình murphy, joel pel đã đưa ra phương trình như trên. Trong đó:

PM là khả năng murphy mà một điều gì đó sẽ không đúng. KM là hằng số murphy, nó là một hằng số bằng 1. FM là hệ số murphy, nó là một số rất nhỏ, nhưng chúng ta có làm tròn xấp xỉ nó bằng 0.01. Các hệ sô I,C,U,F là các biến có thang đo từ 1-10 để miêu tả về sự kiện. Trong đó, I là độ quan trọng của kết quả hoặc kết quả sự kiện, C là độ phức tạp của hệ thống, U là mực độ khẩn cấp của hệ thống. F là mức độ thường xuyên sử dụng hệ thống. Từ 4 biến đó mà bất kỳ sự kiện nào cũng có thể mô tả được. Và với các giá trị đã cho bạn có thể tự tính được khả năng mà một sự việc có thể không đúng.

Trong lĩnh vực phần mềm, định luật murphy ảnh hưởng nhiều nhất trong các phase : project planning, performance management, progress management, risk assesment … và nếu bạn nghĩ rằng nó chỉ có thể xảy ra ở những bước trên thì nó sẽ sai ở một bước khác nữa. Ý nghĩa của định luật murphy chính là những hiểm họa sẽ xảy ra ngay cả khi bạn không tiên đoán được. Để kết thúc về định luật murphy chúng ta sẽ thử áp dụng công thức murphy vào một số ví dụ minh họa sau:

Giả sử bạn đang code cho một module của hệ thống, module này là một module rất quan trọng, vì nó được gọi bởi rất nhiều module khác (ví dụ như thao tác với dữ liệu bao gồm CRUD chẳng hạn, hoặc gì đó tùy bạn), và vì thế mà nó rất thường xuyên được gọi trong hệ thống của bạn. Vậy chúng ta thử đánh giá xem, khả năng module này của bạn code liệu có thể có xảy ra lỗi khi đưa vào sử dụng hay không. Độ quan trọng của hệ thống ta cho I = 9 (1 là thấp nhất, 10 cao nhất), module này giả sử tuy quan trọng nhưng ko đến nỗi quá phức tạp, ta cho là 5, và nó cần hoạt động trước khi các module khác hoạt động, ví dụ như bạn phải insert thì mới xử lý và trả kết quả về được, nên ta cho nó là 8, và cuối cùng nó rất hay được gọi nên độ thường xuyên là 9. Vậy áp dụng các công thức trên thì xác suất murphy sẽ là gần bằng 1. Nghĩa là chắc chắn sẽ có lỗi xảy ra với module của bạn khi đưa vào hoạt động, hoặc trong các điều kiện xấu. Tương tự như thế, bạn có thể tự điều chỉnh dữ liệu và sự kiện để có thể áp dụng vào các trường hợp khác.

Trong lập trình có một trường phái lập trình để chống lại định luật murphy đó chính là lập trình phòng thủ. Ai có thời gian có thể tìm hiểu thêm.

## Định luật Brook

>Adding manpower to a late software project makes it later.
>Nếu thêm người vào một dự án chậm sẽ làm nó chậm hơn

Nó được Brook là một quản trị dự án lâu năm ở IBM đúc kết ra sau rất nhiều dự án ông đã làm ở IBM, và được viết trong cuốn sách cũng vô cùng nổi tiếng The mythical man-month xuất bản năm 1975. Giờ đây định luật này nằm trong hầu hết các cuốn sách về quản trị lớn bé trên thế giới về phát triển phần mềm. Ông còn phát biểu nó dưới dạng một câu nói khác vô cùng hài hước:

>The bearing of a child takes nine months, no matter how many women are assigned.
>Không có cách nào để 9 bà mẹ có thể sinh ra một đứa trẻ trong 1 tháng.

Có 2 điểm dùng để giải thích cho định luật brook trong phát triển phần mềm đó là:

* Sẽ mất một thời gian nhất định để người thêm vào dự án có thể quen với công việc. Dự án phần mềm là một công việc phức tạp, nhất là những dự án khó về mặt business, và những người mới thường phải đầu tiên là được đào tạo để làm quen với nó. Việc đào tạo này cũng yêu cầu tài nguyên từ dự án, như yêu cầu PM hoặc những người có kinh nghiệm đào tạo. Chính việc này đến lượt nó lại làm mất năng suất làm việc của những người có kinh nghiệm nó trên vì họ tốn thời gian vào đào tạo. Ngoài ra những người mới có thể còn làm tiến độ chậm đi khi họ có khả năng tạo ra các bugs mới cho hệ thống.
* Thứ 2 là sự tăng nhanh về kênh giao tiếp giữa các thành viên. Số kênh giao tiếp khác nhau có thể tăng nhanh với số người tham gia. Nó khiến cho công việc khó có thể được đồng bộ, và có thể chồng chéo, làm chậm trễ hơn.

Tuy nhiên cũng có một số điểm có thể xem xét khi thêm người, đó là thêm vào giai đoạn sớm của dự án hoặc người thêm vào thực sự có kinh nghiệm, có khả năng.

## Định luật Linus

Được đặt tên theo Linus Torvalds người đã phát triển hệ điều hành linux, được phát biểu như sau:

>Given enough eyeballs, all bugs are shallow
>Nếu có đủ số lượng người , thì số lượng bugs sẽ giảm đi.

Linus là một trong những thiên tài trong phần mềm, ông đã phát triển nền tảng cho linux và đưa open code cho tất cả lập trình viên trên thế giới phát triển nó, chỉnh sửa và thêm vào. Tốc độ của hệ thống nhân linux ngày càng nhanh cùng với số lượng người tham gia phát triển nó. Enough eyeballs ở đây thể hiện cho số người làm việc và tham gia giải quyết vấn đề. Một phát biểu thông thường hơn của định luật linus là : Với một lượng đủ lớn các lập trình viên và các tester, hầu hết tất cả các vấn đề sẽ được xác định và sửa một cách nhanh chóng và dễ dàng.

## Định luật moore

>The power of computers per unit cost doubles every 24 month.
>Khả năng xử lý của máy tính trên mỗi đơn vị sẽ tăng gấp đôi sau mỗi 2 năm

Hay Số lượng Transitor trên mỗi đơn vị inch vuông sẽ tăng lên gấp đôi sau mỗi năm

![](https://c2.staticflickr.com/6/5484/29876275224_ec22083cc6_o.jpg)

Một định luật nổi tiếng khác mà hầu như ai cũng từng nghe đến, Định luật Moore lần đầu tiên được công bố rộng rãi trên tạp chí Electronics Magazine số ra ngày19/4/1965. Định luật Moore là một bước ngoặt lớn trong ngành công nghệ điện tử, giải thích tại sao nhà sản xuất có thể giảm giá thành trong khi vẫn tiếp tục nâng cao hiệu suất của phần cứng. Tuy nhiên, trong thời gian gần đây định luật Moore đã có nhiều biểu hiện bị thay đổi và kéo dài dần thời gian tăng đôi số transtior trên một đơn vị diện tích (một inch vuông). Tại thời điểm hiện nay (năm 2007), khoảng thời gian để tăng đôi số transistor là xấp xỉ 60 tháng. Nhiều nhà phân tích cho rằng trong tương lai không xa khi mà các áp dụng kỹ thuật đã không thể rút nhỏ kích cở của một transistor xuống hơn được (cụ thể là khi kiến trúc của transistor đã được rút xuống đến mức độ phân tử) thì định luật Moore sẽ không còn đúng nữa. Tuy nhiên với khoảng thời gian dài liên tục phát triển của mình, thì những thành tựu rực rỡ của ngành công nghiệp điện tử đã góp phần xây dựng rất nhiều thần kỳ trong thế kỷ vừa qua.

## Định luật Wirth

Năm 1995  Niklaus Wirth đưa ra định luật mang tên ông như sau:

>software is getting slower more rapidly than hardware becomes faster.
>Phần mềm đang dần nhanh hơn so với phần cứng.

Ý nghĩa của định luật wirth là các phần mềm đang dần ngày càng phức tạp, và dần dần các phần cứng trở nên không đáp ứng được với sự phức tạp của nó. Nhất là trong quá trình vật liệu ngày càng khó khăn, thời gian định luật moore ngày càng kéo dài và có thể không còn đúng nữa, thì việc phần mềm vẫn đang phát triển vô cùng chóng mặt. Đơn giản như các hệ điều hành của microsoft, cứ chu kỳ khoảng 2 năm ra một bản, và các bản sau phức tạp hơn, yêu cầu phần cứng khắt khe hơn. Trên phương diện internet có thể hiểu như tốc độ truyền tải dữ liệu hạn chế, trong khi yêu cầu gửi tin video hoặc chất lượng dữ liệu cao thì ngày càng tăng cao. Chính điều đó cũng là một thách thức với ngành công nghiệp phần cứng.