---
title: "Ngày 2 - 06/10/2026"
date: 2026-01-01
weight: 2
chapter: false
pre: " <b> 1.2.2. </b> "
---
### Mục tiêu
- Xem hết 6 bài giảng Module 01 và video FCAJ Community Day, bài nào cũng có ghi chú riêng.
- Nói lại được định nghĩa điện toán đám mây theo AWS, 4 lợi ích chính và 3 điểm làm AWS khác biệt.
- Vẽ lại được 4 tầng hạ tầng toàn cầu của AWS (trung tâm dữ liệu, Availability Zone, Region, Edge Location) và nêu được 3 tiêu chí chọn Region.
- Phân biệt được 3 cách làm việc với AWS (Management Console, AWS CLI, AWS SDK): mỗi cách xác thực bằng gì và ai là người gọi.
- Kể ra được 8 biện pháp tối ưu chi phí, 3 phương thức thanh toán, 4 gói AWS Support và gói tối thiểu nên dùng cho môi trường chạy thật.
### Công việc đã thực hiện
- Xem bài giảng: Module 01-01 - Điện Toán Đám Mây Là Gì ?
- Xem bài giảng: Module 01-02 - Điều Gì Tạo Nên Sự Khác Biệt Của AWS ?
- Xem bài giảng: Module 01-03 - Bắt Đầu Hành Trình Lên Mây Như Thế Nào
- Xem bài giảng: Module 01-04 - Hạ Tầng Toàn Cầu Của AWS
- Xem lại video ghi hình sự kiện: 23-05-2026 | FCAJ Community Day
- Xem bài giảng: Module 01-05 - Công Cụ Quản Lý AWS Services
- Xem bài giảng: Module 01-06 - Tối Ưu Hóa Chi Phí Trên AWS và Làm Việc Với AWS Support
- **Module 01-01, điện toán đám mây là gì:** AWS định nghĩa điện toán đám mây là phân phối tài nguyên CNTT theo nhu cầu qua Internet, dùng bao nhiêu trả bấy nhiêu. Mình không cần tự mua, tự lắp máy chủ, thiết bị lưu trữ hay thiết bị mạng nữa, chỉ việc gửi yêu cầu kèm cấu hình mình muốn. Nhà cung cấp kiểm tra người gửi đã xác thực và có quyền chưa, tạo máy chủ ảo rồi trả lại cách kết nối. Bài nêu bốn lợi ích:
    - Dùng bao nhiêu trả bấy nhiêu: máy chủ chỉ cần chạy buổi sáng thì tối tắt đi.
    - Phát triển nhanh hơn nhờ có sẵn các tính năng tự động hóa và quản trị.
    - Thêm bớt tài nguyên linh hoạt: hôm nay dùng 4 CPU, mai người dùng tăng thì nâng lên 8 CPU. Với hạ tầng tại chỗ thì phải tính cấu hình trước cho 3 đến 5 năm.
    - Mở rộng ra toàn cầu nhờ mạng hạ tầng của nhà cung cấp.
- **Module 01-02, điều làm AWS khác biệt:**
    - AWS dẫn đầu Gartner Magic Quadrant 13 năm liên tiếp, tính đến hết năm 2023.
    - Về giá, AWS muốn khách hàng trả ngày càng ít hơn cho cùng một dịch vụ, và đã giảm giá hơn 120 lần. Vòng lặp lợi thế kinh tế theo quy mô gồm 6 bước: định giá theo giá trị, có thêm khách hàng, mức sử dụng tăng, thêm hạ tầng, đạt lợi thế quy mô, chi phí hạ tầng giảm, rồi quay lại giảm giá.
    - Văn hóa AWS nằm trong bộ Leadership Principles của Amazon. Giảng viên phân tích kỹ ba nguyên tắc Customer Obsession, Ownership và Deliver Results.
- **Module 01-03, bắt đầu hành trình lên mây:** AWS có nhiều khóa học nhất và sâu nhất, cả của AWS lẫn bên thứ ba, nên tự học hoàn toàn được. Giảng viên khuyên nên có bạn học cùng, vì các dịch vụ AWS liên quan chặt chẽ với nhau mà số dịch vụ lại tăng rất nhanh. Nên đăng ký tài khoản AWS càng sớm càng tốt và tự thử dịch vụ bằng Free Tier, thay vì chỉ học trong môi trường lab dựng sẵn. Slide có liệt kê Udemy, Cloud Guru và trang lộ trình học của AWS. Chương trình First Cloud Journey tập trung cho học viên tự xây workshop và dự án cá nhân để chứng minh năng lực với nhà tuyển dụng.
- **Module 01-04, hạ tầng toàn cầu:**
    - Một trung tâm dữ liệu có thể chứa tới hàng chục nghìn máy chủ, dùng thiết bị được tối ưu riêng cho AWS. Vì vậy khi so sánh các nhà cung cấp thì phải xem hiệu năng đo thực tế, còn cấu hình danh nghĩa kiểu 1 CPU, 4 GB RAM thì không nói lên được gì.
    - Chọn Region dựa trên ba tiêu chí. Một là gần người dùng để giảm độ trễ, người dùng ở Việt Nam thì chọn Singapore. Hai là Region đó đã có dịch vụ mình cần chưa. Ba là chi phí: Region ở Mỹ rẻ hơn Singapore, nên có thể đặt môi trường phát triển và kiểm thử ở Mỹ cho đỡ tốn.
- **Module 01-05, công cụ quản lý:**
    - Root user dùng để đăng nhập lần đầu, sau đó tạo IAM user để dùng hằng ngày.
    - Đăng nhập Console xong thì tìm dịch vụ bằng ô tìm kiếm, mỗi dịch vụ có trang quản lý riêng. Muốn AWS hỗ trợ thì mở menu Support, vào Support Center rồi tạo support case.
    - AWS CLI là công cụ mã nguồn mở, làm được những việc tương đương trên Console.
    - AWS SDK là bộ thư viện cho nhiều ngôn ngữ. Khi gọi API, SDK làm hộ lập trình viên 5 việc: quản lý thông tin xác thực, thử lại, sắp xếp dữ liệu, tuần tự hóa và giải tuần tự hóa.
- **Module 01-06, chi phí và AWS Support:** Bài nêu 8 biện pháp tối ưu chi phí:
    - Chọn đúng cấu hình và nơi lưu trữ, không bê nguyên cấu hình tại chỗ lên mây.
    - Dùng các phương thức thanh toán On-demand, Reserved Instance, Savings Plan và Spot.
    - Xóa tài nguyên không dùng, tự động bật tắt những tài nguyên không cần chạy 24/7.
    - Dùng dịch vụ serverless.
    - Thiết kế kiến trúc tối ưu.
    - Dùng AWS Budgets.
    - Quản lý chi phí theo phòng ban bằng cost allocation tag.
    - Theo dõi và tối ưu liên tục.
    Bài cũng giới thiệu AWS Pricing Calculator: thêm dịch vụ, nhập mức sử dụng rồi xem tổng chi phí ước tính, và có thể chia sẻ bản ước tính cho người khác. Chi phí thay đổi theo Region, dịch vụ và cấu hình.
- **FCAJ Community Day:**
    - Phiên về ngữ cảnh khi làm việc với AI: ngữ cảnh tốt gồm 4 phần là mục tiêu, hoàn cảnh, ràng buộc và tài liệu liên quan. Hai lỗi hay gặp là nhồi mọi thứ tìm được vào cùng một cuộc trò chuyện, và nhắc lại những gì AI đã biết.
    - Amazon Quick Suite nối dữ liệu công ty với các tác tử AI để làm báo cáo, phân tích và tự động hóa.
    - Gói giá cố định của Amazon CloudFront: mỗi bản phân phối trả một mức cố định hằng tháng, đã gồm WAF, chống DDoS, Route 53 và CloudWatch, nên hóa đơn không tăng đột biến. Hiện phải bật gói này thủ công trên Console.
    - Tính bất định của LLM: đặt temperature = 0 vẫn chưa chắc ra cùng kết quả, do phép tính số thực trên GPU và do nhà cung cấp gộp nhiều yêu cầu vào một lô. Muốn giảm thì có thể chạy nhiều lần rồi lấy kết quả chiếm đa số, tự vận hành mô hình, ép đầu ra có cấu trúc, và thiết kế hệ thống chấp nhận sai khác ngay từ đầu.
    - Hệ thống nhiều tác tử cho bài toán chấm điểm tín dụng startup: một tác tử quản lý điều phối 5 tác tử chuyên môn (tài chính, thị trường, đội ngũ, rủi ro, tuân thủ).
### Kết quả
- Nói lại được định nghĩa điện toán đám mây theo AWS: cung cấp tài nguyên CNTT theo nhu cầu qua Internet và trả tiền theo mức sử dụng. Kể được 4 lợi ích, kèm ví dụ so với hạ tầng tại chỗ như tắt máy chủ buổi tối hay nâng từ 4 lên 8 CPU.
- Phân biệt được 4 tầng hạ tầng. Một Availability Zone có một hoặc nhiều trung tâm dữ liệu, các AZ cách ly sự cố với nhau và nối với nhau bằng đường truyền riêng tốc độ cao. Một Region có ít nhất 3 AZ, và dữ liệu mặc định nằm ở Region nơi nó được tạo. Edge Location chạy Amazon CloudFront, AWS WAF và Amazon Route 53. Việt Nam đã có 2 điểm, ở Hà Nội và TP. Hồ Chí Minh.
- Hiểu 3 cách làm việc với AWS: Console xác thực bằng mật khẩu, AWS CLI xác thực bằng access key và secret access key, còn AWS SDK cũng dùng cặp khóa đó nhưng người gọi là ứng dụng. Cả 3 cách đều gửi API request tới AWS Services Endpoint.
- Kể được 8 biện pháp tối ưu chi phí, cách dùng AWS Pricing Calculator và 4 gói AWS Support: Basic để khám phá, Developer cho phát triển và kiểm thử, Business cho môi trường chạy thật, Enterprise cho tập đoàn lớn.
### Khó khăn & cách xử lý
- Mình chưa phân biệt được Reserved Instance với Savings Plan, vì bài chỉ nói cả hai đều được giảm giá khi cam kết dùng 1 hoặc 3 năm. → Mình đọc trang tài liệu AWS về Savings Plans. Savings Plan cam kết theo số tiền mỗi giờ nên linh hoạt hơn Reserved Instance, vốn gắn với một loại instance cụ thể.
### Bài học rút ra
- Root user chỉ dùng để đăng ký tài khoản và thiết lập bảo mật, ví dụ bật MFA, xong thì nên đăng xuất và dùng IAM user cho việc hằng ngày. Đăng nhập bằng IAM user phải nhập thêm Account ID 12 chữ số (hoặc bí danh tài khoản).
- Muốn sẵn sàng cao thì nên triển khai trên ít nhất 2 AZ. Cách này gần giống mô hình hai trung tâm dữ liệu chạy song song ở hạ tầng truyền thống, chỉ khác là mình không phải tự trả tiền đường truyền tốc độ cao. Môi trường phát triển hoặc kiểm thử thì chạy 1 AZ kèm sao lưu là đủ.
- On-demand là cơ chế mặc định và cũng đắt nhất. Reserved Instance hoặc Savings Plan được giảm giá khi cam kết 1 hoặc 3 năm, cam kết càng lâu giảm càng nhiều. Spot giảm tới 90% nhưng có thể bị thu hồi bất cứ lúc nào, nên có thể kết hợp với Savings Plan, ví dụ có 10 máy chủ thì 4 máy chạy Savings Plan, số còn lại chạy Spot. 
- Thiết kế kiến trúc ảnh hưởng tới chi phí nhiều nhất. Truy vấn hay kiến trúc kém làm hệ thống chậm, buộc phải nâng cấu hình, và khi đó chiết khấu cũng không bù lại được. 
- AWS Budgets dùng để đặt ngưỡng cảnh báo, ví dụ báo khi đã tiêu 10 USD hoặc khi chi phí dự kiến cuối tháng chạm 100 USD. Budgets còn kích hoạt được hành động, như tắt máy chủ khi vượt ngưỡng. Với cost allocation tag thì phải gắn tag lên tài nguyên và bật tính năng này mới tách được chi phí theo phòng ban hoặc ứng dụng.
- Từ gói Developer trở lên mới gửi được câu hỏi kỹ thuật cho AWS Support. Môi trường chạy thật nên dùng ít nhất gói Business. Gặp sự cố gấp thì có thể nâng gói trong thời gian ngắn, nhưng không nên làm thường xuyên.
### Tài liệu tham khảo
* <https://www.youtube.com/watch?v=2PQYqH_HkXw>
* <https://www.youtube.com/watch?v=HSzrWGqo3ME>
* <https://www.youtube.com/watch?v=HxYZAK1coOI>
* <https://www.youtube.com/watch?v=IK59Zdd1poE>
* <https://www.youtube.com/watch?v=IY61YlmXQe8>
* <https://www.youtube.com/watch?v=XjMCrcDRACQ>
* <https://www.youtube.com/watch?v=pjr5a-HYAjI>
### Hình ảnh minh chứng:
![Video YouTube "23-05-2026 | FCAJ Community Day" (kênh AWS Study Group): diễn giả Tinh Truong (Platform Engineer, GoTymeX) trình bày slide "Context Is Everything: Making AI Actually Work for You".](/images/1-worklog/1.2-week2/1.2.2-day2/evd-0011.png)
*Video YouTube "23-05-2026 | FCAJ Community Day" (kênh AWS Study Group): diễn giả Tinh Truong (Platform Engineer, GoTymeX) trình bày slide "Context Is Everything: Making AI Actually Work for You".*
![Video "Module 01-01 - Điện Toán Đám Mây Là Gì ?" (AWS Study Group), slide "Điện toán đám mây là gì ?" với định nghĩa: phân phối tài nguyên CNTT theo nhu cầu qua Internet với chính sách thanh toán theo mức sử dụng.](/images/1-worklog/1.2-week2/1.2.2-day2/evd-0012.png)
*Video "Module 01-01 - Điện Toán Đám Mây Là Gì ?" (AWS Study Group), slide "Điện toán đám mây là gì ?" với định nghĩa: phân phối tài nguyên CNTT theo nhu cầu qua Internet với chính sách thanh toán theo mức sử dụng.*
![Video "Module 01-02 - Điều Gì Tạo Nên Sự Khác Biệt Của AWS ?" (AWS Study Group), slide tiêu đề "AWS, điều gì tạo nên sự khác biệt ?".](/images/1-worklog/1.2-week2/1.2.2-day2/evd-0013.png)
*Video "Module 01-02 - Điều Gì Tạo Nên Sự Khác Biệt Của AWS ?" (AWS Study Group), slide tiêu đề "AWS, điều gì tạo nên sự khác biệt ?".*
![Video "Module 01-03 - Bắt Đầu Hành Trình Lên Mây Như Thế Nào" (AWS Study Group), slide liệt kê nhà cung cấp khóa học AWS bên thứ 3 (udemy.com, cloudguru.com) và lộ trình học AWS (aws.amazon.com/vi/training/learning-paths).](/images/1-worklog/1.2-week2/1.2.2-day2/evd-0014.png)
*Video "Module 01-03 - Bắt Đầu Hành Trình Lên Mây Như Thế Nào" (AWS Study Group), slide liệt kê nhà cung cấp khóa học AWS bên thứ 3 (udemy.com, cloudguru.com) và lộ trình học AWS (aws.amazon.com/vi/training/learning-paths).*
![Video "Module 01-04 - Hạ Tầng Toàn Cầu Của AWS" (AWS Study Group), slide "Availability Zone": AZ gồm một hoặc nhiều trung tâm dữ liệu, fault isolation, kết nối riêng tốc độ cao giữa các AZ, khuyến nghị triển khai tối thiểu trên 2 AZ.](/images/1-worklog/1.2-week2/1.2.2-day2/evd-0015.png)
*Video "Module 01-04 - Hạ Tầng Toàn Cầu Của AWS" (AWS Study Group), slide "Availability Zone": AZ gồm một hoặc nhiều trung tâm dữ liệu, fault isolation, kết nối riêng tốc độ cao giữa các AZ, khuyến nghị triển khai tối thiểu trên 2 AZ.*
![Video "Module 01-05 - Công Cụ Quản Lý AWS Services" (AWS Study Group), slide "AWS Command Line Interface (CLI)" kèm sơ đồ User truy cập AWS Services Endpoint qua Management Console (Passwords) và AWS CLI (Access key / Secret Access key).](/images/1-worklog/1.2-week2/1.2.2-day2/evd-0016.png)
*Video "Module 01-05 - Công Cụ Quản Lý AWS Services" (AWS Study Group), slide "AWS Command Line Interface (CLI)" kèm sơ đồ User truy cập AWS Services Endpoint qua Management Console (Passwords) và AWS CLI (Access key / Secret Access key).*
![Video "Module 01-06 - Tối Ưu Hóa Chi Phí Trên AWS và Làm Việc Với AWS Support" (AWS Study Group), slide "Làm việc với AWS Support" liệt kê 4 gói hỗ trợ: Basic, Developer, Business, Enterprise và việc có thể nâng cấp gói hỗ trợ trong thời gian ngắn.](/images/1-worklog/1.2-week2/1.2.2-day2/evd-0017.png)
*Video "Module 01-06 - Tối Ưu Hóa Chi Phí Trên AWS và Làm Việc Với AWS Support" (AWS Study Group), slide "Làm việc với AWS Support" liệt kê 4 gói hỗ trợ: Basic, Developer, Business, Enterprise và việc có thể nâng cấp gói hỗ trợ trong thời gian ngắn.*
