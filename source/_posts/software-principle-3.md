---
title: Các định luật phần mềm – Phần 3
date: 2020-04-05 03:59:50
category: software
tags:
    - principle
    - production
---

## Định luật Kerckhoffs

Trong lĩnh vực mã hóa có một định luật được phát biểu bởi Auguste Kerkhoffs nói rằng:

>In cryptography, a system should be secure even if everything about the system, except for a small piece of information — the key — is public knowledge.
>Một hệ thống phải được an toàn ngay cả khi kẻ thù biết được tất cả mọi thứ về hệ thống trừ một thứ đó là key mã hóa.

Định luật này xuất phát từ thế kỷ 19 và nó dường là tiền đề cho mọi phát minh về mã hóa sau này. Trong thế chiến thứ 2 khi mà hoạt động tình báo trở nên vô cùng phổ biến và cuộc chiến về mã hóa đã cho ra đời hàng trăm phát minh mới về mã hóa trong thời gian này thì định luật này được xem như là cơ sở. Và hiện nay với các mã hóa hiện đại càng thể hiện sự đúng đắn của định luật này.

<!--more -->
## Định luật Reed

>The utility of large networks, particularly social networks, scales exponentially with the size of the network.
>Độ mở rộng của các mạng xã hội tỉ lệ với hàm số mũ

Được phát biểu bởi David Reed nói về mức độ phát triển của một mạng lớn, đặc biệt là mạng xã hội. Lý do tại sao lại là hàm số mũ mà ko phải hàm bình phương là vì số nhóm con của một mạng xã hội có N thành viên sẽ là 2^N − N − 1, nó tăng nhanh hơn rất nhiều so với số lượng connection chỉ là N(N-1) (Định luật Metcalfe)

## Định luật Zawinski

Định luật nói về độ mở rộng của một phần mềm

>Every program attempts to expand until it can read mail. Those programs which cannot so expand are replaced by ones which can.
>Tất cả các chương trình sẽ được mở rộng cho tới khi nó đọc được mail, những chương trình ko đạt được điều đó sẽ được thay thế bởi chương trình có thể làm được.

Nó nói lên mức độ phổ biến và sự quan trọng của mail trong hệ thống thông tin. Hầu như ngày nay tất cả các chương trình đều liên kết tới email, không có chương trình nào mà ko sử dụng địa chỉ email để đăng ký cả. Hiện nay có một dị biến nói thêm về RSS nhưng ko phổ biến. Hiện tại email vẫn là số 1 trong tất cả các hệ thống.

## Định luật Conway

Một định luật vô cùng quan trọng thể hiện sự phản ánh cấu trúc của phần mềm

>Any piece of software reflects the organizational structure that produced it
>Bất kỳ phần nào của phần mềm cũng phản ánh cấu trúc đã tạo ra nó

Đây là định luật được Conway đưa ra vào năm 1968 về cấu trúc hệ thống phần mềm. Nó cho phép bạn có thể hiểu được cách thức, cấu tạo của hệ thống khi biết được một phần của phần mềm. Nó là hệ quả của việc nhiều người cùng làm trong cùng một hệ thống. Giả sử A và B làm 2 modul 1 và 2 thì để 1 và 2 kết nối được với nhau thì A và B phải tạo ra interface để các module ấy có thể nói chuyện được với nhau. Hoặc giả sử A làm một module và nếu B muốn dùng module đó thì trong OO B thường sẽ extend module của A vì sợ làm ảnh hưởng tới code của A, tuy nhiên nếu A thêm chức năng có thể A sẽ sửa trực tiếp module chứ ko phải extend nó. Đó chính là ý mà conway muốn nói đến trong định luật này.

## Định luật Fitt

Đây là định luật về độ usability của hệ thống.

>Time = a + b log2 ( D / S + 1 )

phát biểu bằng lời như sau

>The time to acquire a target is a function of the distance to and the size of the target.
>Thời gian để đạt được một mục tiêu là hàm phụ thuộc vào khoảng cách và kích thước của mục tiêu

Nó ảnh hưởng rất lớn đến các nhà thiết kế. Kể ra thiết kế các module để reuse trong phần mềm hay là thiết kế giao diện. Ví dụ như việc đặt menu ở góc trái bên dưới là vị trí sẽ tốn thời gian nhất. Vì khoảng cách xa và diện tích bé. Dấn tới sẽ tốn thời gian để bạn có thể thao tác với menu. Ngược lại nếu bạn muốn module nào dễ thao tác, bạn có thể làm diện tích to và đặt ở trung tâm. Định luật này hầu hết các designer đều rất thông thạo.

## Định luật Hick

Định luật liên quan tới thời gian đưa ra quyết định cho bạn, được phát biểu như sau.

>The time to make a decision is a function of the possible choices he or she has.
>Thời gian đưa ra quyết định sẽ là một hàm phụ thuộc các khả năng lựa chọn mà bạn có
>Time = b log2(n + 1)

Thời gian sẽ phụ thuộc vào hàm số log cơ số 2. Tại sao lại là log cơ số 2 thì đó chính là do cơ chế não của chúng ta phân tích theo nhị phân. Thường thì chúng ta sẽ làm theo cơ chế loại bỏ. Và chính vì thế có công thức trên. Áp dụng công thức này bạn cũng có thể tính được thời gian để não nhận ra đáp án cho câu hỏi chắc nghiệm. Giả sử đề thi của bạn có 4 câu trả lời khả dĩ. Bạn mất 2 giây để đọc hiểu câu hỏi, thời gian não bạn đưa ra quyết định dựa trên một sự kiện là 0.1s. (Chú ý đây là thời gian não phản ứng. Thông thường khi có tai nạn chẳng hạn, thời gian để não đưa ra phản ứng sau khi nhận biết có sự kiện cũng khoảng 0.1s) và đưa vào công thức bạn sẽ có thời gian để bạn biết câu trả lời của câu hỏi là 2.35s. Và nó cũng có thể mở rộng ra với việc đưa ra quyết định của một nhóm bạn. Tuy nhiên hệ số sẽ khác. Bạn thử áp dụng vào thực tế khi cả nhóm bạn quyết định trưa nay đi ăn ở đâu thử xem. Cũng là một việc thú vị đấy chứ.

## Định luật Occam Razor

Định luật phát biểu rằng

>The explanation of any phenomenon should make as few assumptions as possible
>Sự giải thích cho bất kỳ hiện tượng nào nên đơn giản nhất có thể.
Định luật này nhấn mạnh rằng cách giải thích nào đơn giản nhất thường là cái đúng. Các nhà thám tử dùng định luật này để  loại bỏ dần các đối tượng tình nghi, các bác sĩ dùng định luật này để tìm ra nguyên nhân bệnh dựa trên một tập các triệu chứng.

Bạn có thể xem thêm ở [đây](http://science.howstuffworks.com/innovation/scientific-experiments/occams-razor.htm) để hiểu thêm về định luật này.

Ngoài các định luật đã nêu còn rất nhiều định luật khác nữa bạn có thể tham khảo ở [wiki](http://en.wikipedia.org/wiki/List_of_eponymous_laws). Nó bao gồm rất nhiều định luật từ vật lý , toán học, hóa học, sinh học …. khác nữa.