---
title: "Event 1"
date: 2026-01-01
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Bài thu hoạch: "Kickoff FCAJ Buildrathon 2026 (Season 01) - The Thinking Behind Building The Bot"

**Tên sự kiện:** Buildrathon Kickoff: Code the Future with CMC Global

**Thời gian:** Thứ Bảy, 26/09/2026, 09:00 - 12:00

**Địa điểm:** Văn phòng AWS Việt Nam, tầng 26 Bitexco Financial Tower, TP. Hồ Chí Minh

**Vai trò:** Người tham dự, thành viên đội Xóm Data tham gia FCAJ Buildrathon 2026

### Mục tiêu sự kiện

* Khởi động FCAJ Buildrathon 2026 (Season 01), sân chơi thực chiến kéo dài 6 tháng dành cho cộng đồng AI và Cloud tại Việt Nam. Các đội sẽ xây dựng sản phẩm thật trên AWS thay vì chỉ học lý thuyết, đúng với thông điệp của chương trình: *"Don't just learn Cloud & AI for knowledge - build real products, gain lifelong teammates, and make your mark in the tech world."*
* Trang bị tư duy kiến trúc và cách triển khai AI Agent trong môi trường doanh nghiệp, thông qua talkshow *"The Thinking Behind Building The Bot"*.
* Phân tích các bài toán kiểm thử thực tế và những thử thách kỹ thuật thường gặp khi đưa một con bot từ bản thử nghiệm lên vận hành thật.
* Mở rộng kết nối và định hướng nghề nghiệp cùng đội ngũ chuyên gia công nghệ và HR của CMC Global, qua phần Mock-interview cuối chương trình.

### Diễn giả và đơn vị tổ chức

* **Thien Lu** - Program Manager, First Cloud AI Journey (FCAJ)
* **Phong Pham** - Program Manager, First Cloud AI Journey (FCAJ)
* **Bui Nhat Truong** - Technical Leader, CMC Global, diễn giả talkshow *"The Thinking Behind Building The Bot"*
* **Đơn vị tổ chức và đồng hành:** AWS Study Group / First Cloud Journey phụ trách tổ chức và điều phối cộng đồng; CMC Global đồng tổ chức, phụ trách chuyên đề kỹ thuật và phần kết nối nghề nghiệp.

### Chương trình

| Thời gian | Nội dung |
| --- | --- |
| 09:00 - 09:30 | Buildrathon Kickoff |
| 09:30 - 11:15 | Talkshow "The Thinking Behind Building The Bot" |
| 11:15 - 12:00 | Mock-interview |

### Nội dung nổi bật

#### Lộ trình thử thách FCAJ Buildrathon 2026 (Season 01)

* Buildrathon là sân chơi dài hạn (6 tháng), tập trung vào bài toán thực tế kết hợp điện toán đám mây AWS với trí tuệ nhân tạo tạo sinh và AI Agent.
* Các đội được đánh giá theo từng mốc. Tiêu chí đề cao tính ứng dụng, độ ổn định của hệ thống và khả năng mở rộng khi chạy trên môi trường Production, chứ không chỉ dừng ở một bản demo chạy được.
* Đội Xóm Data có 6 nhóm đại diện tham gia. Trong 6 tháng tới, các nhóm định hướng xây dựng giải pháp trên AWS ở ba mảng:
  * **Hạ tầng và tính toán:** AWS Lambda cho các luồng xử lý serverless, kết hợp Auto Scaling và Elastic Load Balancing để hệ thống luôn sẵn sàng.
  * **Dữ liệu:** quản lý các luồng dữ liệu lớn với Amazon S3, Amazon Redshift và Amazon DynamoDB.
  * **Hệ thống thông minh:** tích hợp Generative AI, Machine Learning và AI Agent để giải quyết bài toán nghiệp vụ.

#### The Thinking Behind Building The Bot: kiến trúc AI Agent thực chiến

* **Tư duy nền tảng:** chuyển từ việc viết từng prompt rời rạc sang xây dựng một hệ thống AI Agent tự hành. Một agent như vậy cần làm được ba việc:
  * Phân rã một yêu cầu lớn thành các bước nhỏ có thể thực hiện được.
  * Quản lý bộ nhớ: bộ nhớ ngắn hạn giữ ngữ cảnh trong một phiên làm việc, bộ nhớ dài hạn lưu lại thông tin cần dùng qua nhiều phiên.
  * Điều phối công cụ: biết khi nào cần gọi API, truy vấn dữ liệu hay chạy một hàm thay vì chỉ trả lời bằng văn bản.
* **Kiến trúc tích hợp trong doanh nghiệp:** luồng dữ liệu phải an toàn từ đầu đến cuối; agent lấy tri thức từ cơ sở tri thức của doanh nghiệp và kết nối với các API nội bộ, để câu trả lời dựa trên dữ liệu thật của tổ chức.
* **Tối ưu vận hành:** khi triển khai thật luôn phải cân bằng ba yếu tố: chi phí cho mỗi lần gọi mô hình, độ trễ phản hồi và độ chính xác. Tăng một yếu tố thường làm giảm yếu tố khác, nên cần chọn điểm cân bằng phù hợp với bài toán.

#### Thử thách kỹ thuật khi lên Production

* **Kiểm soát ảo giác:** dùng guardrails và framework kiểm thử tự động để kiểm tra đầu ra, đảm bảo thông tin agent trả về đáng tin cậy.
* **Xử lý tình huống biên:** chuẩn bị phương án dự phòng cho các trường hợp mô hình ngôn ngữ lớn không gọi được công cụ, hoặc trả về kết quả sai định dạng mà hệ thống phía sau không đọc được.

#### Kết nối nghề nghiệp cùng CMC Global

* Phần Mock-interview cuối chương trình là dịp gặp và trao đổi trực tiếp với đội ngũ HR và Technical Lead của CMC Global về nhu cầu nhân lực trong các mảng Cloud, AI Engineering và Data Analytics.

### Những gì học được

#### Tư duy thiết kế

* **Kiến trúc đi trước, prompt theo sau:** một bot hay agent chạy ổn định trong doanh nghiệp phụ thuộc vào thiết kế hệ thống, không chỉ vào việc tinh chỉnh prompt. Prompt tốt mà kiến trúc yếu thì vẫn hỏng khi gặp dữ liệu thật và lượng người dùng thật.
* **Bảo mật và an toàn dữ liệu:** AI Agent có quyền gọi công cụ và đọc dữ liệu, nên phải tuân thủ chặt chẽ kiểm soát truy cập và bảo vệ dữ liệu nhạy cảm ngay từ khâu thiết kế.

#### Kiến trúc kỹ thuật

* Tối ưu kiến trúc điều phối agent trên hạ tầng AWS.
* Giám sát là phần bắt buộc: ghi log hoạt động của agent và đo hiệu năng của từng bước suy luận, để khi agent trả lời sai có thể lần lại xem lỗi nằm ở bước nào.

#### Cộng đồng

* Tinh thần "Pay It Forward" của AWS Study Group tạo động lực để các thành viên kết nối, học từ thực tế và chia sẻ kiến thức liên tục với nhau.

### Áp dụng vào công việc

* **Chuẩn hoá kiến trúc AI Agent:** tách agent thành các thành phần rõ ràng: lập kế hoạch, bộ nhớ và công cụ, rồi áp dụng cách tổ chức này vào các dự án tự động hoá và xử lý dữ liệu đang làm.
* **Chuẩn bị cho Buildrathon:** cùng nhóm lên kế hoạch thiết kế sản phẩm và chuẩn bị môi trường thử nghiệm trên AWS cho các chặng tiếp theo.
* **Kiểm thử trước khi vận hành:** đặt tiêu chí đo độ chính xác và kiểm soát rủi ro bảo mật trước khi đưa bất kỳ giải pháp AI nào vào chạy thật.

### Trải nghiệm sự kiện

Buổi Kickoff FCAJ Buildrathon 2026 Season 01 tại văn phòng AWS Việt Nam là buổi mở màn có nhiều giá trị chuyên môn.

#### Học từ chuyên gia

* Phần chia sẻ của CMC Global cho tôi góc nhìn trực tiếp về những khó khăn khi đưa AI Agent từ giai đoạn thử nghiệm lên hệ thống Production của doanh nghiệp, điều mà các bài hướng dẫn thường không nói tới.

#### Không khí sự kiện

* Sự kiện quy tụ rất đông builder và kỹ sư. Được trao đổi trực tiếp tại văn phòng AWS giúp tôi nối các mảng kiến thức từ hạ tầng Cloud, Data Engineering đến AI lại với nhau.

#### Minh chứng tham dự

* Bài đăng LinkedIn của Xóm Data về buổi Kickoff, có tên tôi trong danh sách các đội tham gia: <https://lnkd.in/p/ea265it3>

#### Hình ảnh sự kiện


![Poster sự kiện Buildrathon Kickoff](/images/4-eventparticipated/4.1-event1/poster.png)
*Hình 1: Poster sự kiện Buildrathon Kickoff: Code the Future with CMC Global.*

![Check-in tại sảnh văn phòng AWS](/images/4-eventparticipated/4.1-event1/anh-tuong-its-still-day-1.png)
*Hình 2: Check-in tại sảnh "It's Still Day 1" của văn phòng AWS, cạnh standee chuyên đề của CMC Global và AWS.*

![Ảnh chụp chung trong phòng hội thảo](/images/4-eventparticipated/4.1-event1/anh-nhom-hanoi-team.png)
*Hình 3: Ảnh chụp chung cùng diễn giả trong phòng hội thảo.*

![Phòng hội thảo trong phần talkshow](/images/4-eventparticipated/4.1-event1/anh-phong-hoi-thao.png)
*Hình 4: Phòng hội thảo trong phần talkshow "The Thinking Behind Building The Bot".*

> Buổi Kickoff cho tôi kiến thức cập nhật về AI Agent và là bước khởi đầu để tự tin bước vào hành trình 6 tháng của Buildrathon Season 01.
