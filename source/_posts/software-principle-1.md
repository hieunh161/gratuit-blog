---
title: software-principle-1
date: 2020-04-05 03:58:50
category: software
tags:
    - principle
    - software
---


## Mở đầu

Trong các lĩnh vực tự nhiên, các nhà khoa học đã tìm ra rất nhiều định luật, quy luật của tự nhiên và đã trở thành những kiến thức nền tảng trong xã hội. Nó giúp chúng ta hiểu rõ, giải thích được các hiện tượng một cách thấu đáo hơn. Trong lĩnh vực phần mềm, dù nó khác so với một lĩnh vực khoa học, song trong thời gian ngắn xuất hiện của mình, nó cũng đã được rất nhiều nhà nghiên cứu tìm ra được những quy luật và họ đã phát biểu thành các định luật mang tên mình. Hiểu rõ được các định luật chi phối trong ngành phần mềm không chỉ giúp chúng ta hiểu hơn công việc mà còn giúp chúng ta thay đổi xử lý các vấn đề tốt hơn.

<!-- more -->
## Định luật Postel

Định luật Postel hay còn gọi là định luật về độ ổn định của một hệ thống (Robustness law)  được đặt tên theo nhà khoa học Postel là người tiên phong trong lĩnh vực phát triển nền tảng internet. Ông phát biểu định luật này khi viết đặc tả cho giao thức TCP (transmission control protocol) nổi tiếng.

>Be conservative in what you send, liberal in what you accept
>Hãy tuân thủ chặt chẽ những gì bạn gửi đi, tự do với những gì bạn chấp nhận

Nói theo một cách khác, code viết trong các chương trình khi gửi lệnh hoặc dữ liệu tới chương trình khác, hoặc module khác của chương trình nên tuân thủ chặt chẽ các đặc tả, tuy nhiên code khi nhận dữ liệu thì phải làm sao nó có thể chấp nhận được cả các dữ liệu không tuân thủ cấu trúc, hoặc ý nghĩa không rõ ràng. Thực tế thì bạn gặp rất nhiều trường hợp liên quan tới định luật Postel như code check lỗi input và handle exception… trong phần mềm.

## Định luật Parkingson

>Work expands so as to fill the time available for its completion
>Công việc luôn tự mở rộng ra để chiếm đủ thời gian được ấn định cho nó

Định luật này được C. Northcote Parkinson, nhà văn và sử học người Anh đưa ra. Nó không chỉ dành cho lĩnh vực phần mềm nói riêng mà nó mở rộng cho tất cả các lĩnh vực khác. Ý nghĩa của nó là khi bạn dự định làm một công việc gì đó trong một khoảng thời gian lớn hơn so với thời gian nó có thể hoàn thành thì bản thân công việc sẽ mở rộng ra để chiếm nốt phần thời gian thừa của bạn. Ví dụ như công việc này bạn dự định làm trong 1 tuần, tuy nhiên thực tế thì có thể hoàn thành công việc trong 3 ngày. Vậy khi làm công việc thì nó sẽ phát sinh những việc để chiếm hết 1 tuần của bạn. Định luật này vô cùng quan trọng đối với các nhà quản lý. Hiểu rõ định luật này sẽ giúp các nhà quản lý hoạch định để tăng productivity của nhân viên, cũng như sử dụng thời gian rảnh rỗi một cách hợp lý. Và nó cũng dẫn tới một kiểu quản lý mới đó là các nhà quản lý cố gắng chia nhỏ công việc ra nhỏ nhất có thể để hạn chế tối đa ảnh hưởng của định luật Parkingson. Thường thì có thể là trong 1 ngày.  Bạn có thể tự kiểm nghiệm với bản thân mình, thường những cách mà nhân viên áp dụng định luật parkingson là họ cố gắng nghĩ ra những việc không quan trọng để lấp đầy thời gian rảnh rỗi, như sắp xếp giấy tờ, pha cà phê … hoặc những công việc có productivity bằng 0.

![](https://c2.staticflickr.com/6/5825/29876161104_69629eb9a7_b.jpg)

Định luật này còn áp dụng trong lĩnh vực quản lý tiền bạc với phát biểu sau:
>Expenditures rise to meet income.
>Các khoản chi tiêu sẽ tăng lên cho đến khi nó bằng với thu nhập.

Nghĩa là nếu bạn ko có kế hoạch tích lũy, quản lý hợp lý tiền bạc thì cho dù thu nhập bạn tăng lên bạn cũng ko có hi vọng gì vào việc có tiền thừa cả, mà sẽ có các khoản chi phí khác phát sinh cho đến khi số tiền bằng với số tiền bạn kiếm được. Với sinh viên và nhân viên trẻ thì điều này thấy rất rõ ràng.

Hiểu được định luật parkingson có thể giúp bạn biến nó thành lợi thế cho mình với các định hướng trước như dừng việc dành hàng giờ đồng hồ vào việc làm gì đấy, hãy cố gắng hoàn thành mọi việc càng sớm càng tốt và tận hưởng thời gian rỗi rãi còn lại.

## Định luật Pareto

Còn được biết với định luật vô cùng nổi tiếng 80-20, hay là quy luật thiểu số quan trọng, phân bố nhân tố, nó được phát biểu như sau:

>For many phenomena, 80% of consequences stem from 20% of the causes.
>Với rất nhiều hiện tượng, thì 80% kết quả là do 20% nguyên nhân gây ra

![](https://c2.staticflickr.com/6/5331/30470104756_93803fa4bb_o.gif)

Nó được đặt tên theo nhà kinh tế người Ý Vilffedo Pareto với công trình đầu tiên về quan sát 80% đất đai ở Ý là thuộc 20% dân số, và sau đó được các nhà nghiên cứu khác áp dụng rộng rãi trong tất cả các hiện tượng trong xã hội. Trong lĩnh vực phần mềm chúng ta có thể hiểu theo một số cách rất quan trọng như sau. 80% khối lượng công việc sẽ do 20% số người làm ra. Hay 80% bugs sẽ đến từ 20% số dòng code… hoặc là 80% khối lượng công việc khó nhất sẽ nằm trong thời gian 20% cuối cùng. Hay đơn giản là 20% sếp sẽ nhận thu nhập bằng 80% chẳng hạn. Trước kia có một lần nói chuyện với một sếp cũ thì có biết là chính sách công ty cũng sẽ là giữ 20% key còn lại thì không quan tâm lắm. Nên dù sao việc của bạn khi hiểu được quy luật này là hãy phấn đấu để trở thành 20% quan trọng nhất ở bất kỳ vị trí nào. :) quy luật này dù hiện hữu ở rất nhiều lĩnh vực nhưng vấn đề của nó là không phải lúc nào bạn cũng biết được cái nào là 20%.

## Định luật Peter

Năm 1968 trong cuốn sách “The peter principle” Dr. Laurence J. Peter  đã đưa ra định luật phát biểu rằng:
>“In a hierarchy every employee tends to rise to his level of incompetence.” 
>Trong mô hình phân cấp, các nhân viên sẽ có xu hướng vươn lên tới các vị trí mà năng lực anh ta không đáp ứng được.

Theo như định luật này thì một lúc nào đó, cuối cùng một nhân viên sẽ vươn tới được vị trí mà tất cả khả năng tốt nhất của anh ta được phát huy. Và những vị trí cao hơn thì năng lực của anh ta không còn phù hợp và đáp ứng được nữa. Hoặc nó còn có thể hiểu là dù anh ta còn khả năng nhưng anh ta không còn rèn luyện những kỹ năng để đáp ứng vị trí công việc nữa. Với những công ty phát triển nhanh đột biến thì hiện tượng này xảy ra rất nhiều. khi các sếp hi vọng các nhân viên xuất sắc ở cấp dưới có thể đảm nhiệm tốt các công việc phía trên vì khả năng của họ. Ví dụ những người có năng lực kỹ thuật tốt thường sẽ đảm nhiệm việc quản lý khi cty phát triển. Tất nhiên có nhiều người có khả năng phù hợp, nhưng cũng có những người không thể đáp ứng được. Trong quản trị nhân sự cấp cao, điều này đặc biệt quan trọng. Với quản trị nhân sự chung trong toàn công ty lớn, hiện nay họ cũng cố gắng hạn chế nhất có thể việc “ngồi nhầm chỗ” này khi đánh giá đúng được năng lực nhân viên.

## Định luật Hofstadter

Định luật này là một phần của cuốn sách An Eternal Golden Braid của Douglas Hofstadter xuất bản năm 1979. Định luật này đặc biệt đúng, ngay cả áp dụng vào thời gian tôi dành để viết bài blog này. Thời gian để viết xong nó tốn nhiều hơn những gì tôi đã mong muốn. Định luật này phát biểu rằng:

>It always takes longer than you expect, even when you take into account Hofstadter’s Law.
>Một nhiệm vụ thường tốn nhiều thời gian hơn bạn mong muốn, ngay cả khi bạn biết và hiểu định luật này.

Định luật này được giới thiệu lần đầu tiên liên quan tới vấn đề cuộc chiến cờ giữa máy tính và người khi mà các kỳ thủ hàng đầu đã liên tục đánh thắng máy ngay cả khi máy tính tính toán trước được rất nhiều nước đi của các kỳ thủ. Hofstadter đã viết : “Trong những ngày đầu của cờ máy, người ta đã estimate rằng sẽ mất 10 năm để biến cờ máy thành vô địch, không có đối thủ. Nhưng sau khi 10 năm trôi qua, có vẻ như ngày mà cờ máy thành vô địch sẽ phải mất thêm 10 năm nữa.” Và ông ấy lấy đó như là một luận cứ để hình thành nên định luật của mình.

![](https://c2.staticflickr.com/6/5773/30470105006_a3db633c28_o.jpg)

Trong lĩnh vực phần mềm bạn có thể hiểu là thông thường thời gian thực hiện xong một task, module sẽ thường dài hơn bạn đã ước lượng và mong muốn. Định luật này được đề cập và nhắc đến rất nhiều trong các programmers. Trong các cuốn về tăng hiệu suất công việc như The mythical of man-month hay extreme programming vấn đề này cũng được thảo luận rất nhiều.  Định luật này phản ánh sự phức tạp trong vấn đề estimate ngay cả với những người có kinh nghiệm.

To be continue.