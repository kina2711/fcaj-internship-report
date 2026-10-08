---
title: "Ngày 3 - 07/10/2026"
date: 2026-01-01
weight: 3
chapter: false
pre: " <b> 1.2.3. </b> "
---

### Mục tiêu

- Làm xong trong ngày 3 bài thực hành của CloudJourney: Creating Your First AWS Account, Managing Costs with AWS Budgets và Getting Help with AWS Support
- Ghi lại đủ 5 nhiệm vụ nhận credit và danh sách những thứ dễ làm hao credit cần tránh
- Tạo đủ 4 loại ngân sách trong AWS Budgets (Cost Budget, Usage Budget, RI Budget, Savings Plans Budget), làm xong thì xóa cả 4
- Gửi 1 yêu cầu hỗ trợ qua AWS Support, chọn mức độ nghiêm trọng cho phù hợp

### Công việc đã thực hiện

- Bài thực hành CloudJourney 000001 - Creating Your First AWS Account
- Bài thực hành CloudJourney 000007 - Managing Costs with AWS Budgets
- Bài thực hành CloudJourney 000009 - Getting Help with AWS Support
- Các nhiệm vụ nhận credit và những thứ dễ làm hao credit cần tránh
- Các kiến trúc mẫu dùng 200$ credit, cách theo dõi và tối ưu chi phí, lộ trình học AWS 6 tháng
- Các loại ngân sách trong AWS Budgets và cách dọn dẹp sau khi làm xong bài
- Các gói AWS Support, các loại yêu cầu hỗ trợ và các mức độ nghiêm trọng

### Kết quả

- Bài Creating Your First AWS Account: tìm hiểu 5 nhiệm vụ nhận credit, ghi lại những thứ dễ làm hao credit cần tránh, xem 2 kiến trúc mẫu với 200$ credit và cách theo dõi chi phí
- Bài Managing Costs with AWS Budgets: tạo lần lượt 4 loại ngân sách trong AWS Budgets là Cost Budget, Usage Budget, RI Budget và Savings Plans Budget, rồi xóa hết để dọn dẹp tài nguyên
- Bài Getting Help with AWS Support: tìm hiểu các gói AWS Support, cách vào trang Support và cách đổi gói hỗ trợ
- Bài Getting Help with AWS Support: tạo 1 yêu cầu hỗ trợ và chọn mức độ nghiêm trọng phù hợp

### Khó khăn & cách xử lý

- Lúc đầu mình chưa phân biệt được ngưỡng cảnh báo Actual (tính theo chi phí thực tế) với ngưỡng Forecasted (tính theo chi phí dự báo), nên không biết chọn loại nào → Mình đọc lại phần Budgets trong tài liệu AWS Cost Management để hiểu Actual và Forecasted, rồi chọn lại ngưỡng cho phù hợp
- Mình cũng chưa hiểu Utilization với Coverage khác nhau chỗ nào khi tạo RI Budget và Savings Plans Budget → Mình xem lại phần giải thích Utilization và Coverage trong tài liệu AWS, sau đó làm lại RI Budget và Savings Plans Budget theo đúng hướng dẫn của lab

### Bài học rút ra

- Cần theo dõi chi phí thường xuyên và biết trước dịch vụ nào dễ làm hao credit
- AWS Budgets có 4 loại ngân sách: Cost Budget theo dõi chi phí, Usage Budget theo dõi mức sử dụng, RI Budget theo dõi Reserved Instance, Savings Plans Budget theo dõi Savings Plans
- Budget chỉ giám sát và gửi cảnh báo, nó không tự chặn hay tắt tài nguyên; xóa budget cũng không ảnh hưởng gì tới tài nguyên đang chạy
- Bài thực hành nào cũng nên kết thúc bằng bước dọn dẹp tài nguyên để khỏi bị tính phí
- Trong AWS Support, yêu cầu hỗ trợ được chia theo loại và theo mức độ nghiêm trọng, còn được hỗ trợ tới đâu thì tùy gói đang dùng
- Bài Creating Your First AWS Account - nhận credit và tránh hao credit:

| Nội dung | Mình đã học được |
|---|---|
| 5 nhiệm vụ nhận credit | Làm trong widget Explore AWS ở AWS Console Home, mỗi nhiệm vụ được 20$ credit:<br>1. Launch EC2 Instance, tạo instance rồi Terminate khi xong<br>2. Use Amazon Bedrock Playground, chọn model Claude 3 Haiku và chạy thử 1 prompt, nếu bị lỗi quyền thì tạo case Account and billing để xin mở quyền<br>3. Set up AWS Budgets, tạo 1 cost budget có email nhận thông báo<br>4. Create Lambda Web App, dùng blueprint Getting started with Lambda HTTP rồi xóa function<br>5. Create RDS Database, dùng Easy create với Aurora PostgreSQL Compatible rồi xóa instance và cluster, nhớ bỏ chọn Create final snapshot.<br>• Mỗi nhiệm vụ chỉ được tính credit 1 lần, làm sai thì làm lại được<br>• dễ nhất là Set up AWS Budgets, mất khoảng 10-15 phút, khó nhất là Create RDS Database, khoảng 30-40 phút cộng thêm thời gian chờ |
| Những thứ dễ làm hao credit | Nhóm nguy hiểm nhất, có thể đốt hết 200$ trong vài giờ:<br>• Amazon SageMaker với Training Jobs, Notebook Instances và Endpoints vì dễ quên tắt và tự động scale<br>• EC2 GPU như p3.2xlarge, p4d.24xlarge, g4dn.xlarge vì rất đắt và không có Free Tier<br>• Amazon Redshift vì có kích thước cluster tối thiểu, khó tối ưu.<br>• Dịch vụ dùng được nhưng phải cẩn thận: EC2 chỉ t2.micro hoặc t3.micro, RDS chỉ db.t3.micro, ElastiCache chỉ cache.t3.micro, API Gateway thì phải theo dõi số request.<br>• Cách phòng thủ: tạo Cost budget 200$ theo tháng với 4 ngưỡng cảnh báo 12.5, 25, 50, 75, xem Cost Explorer hằng ngày và bật Cost Anomaly Detection |
| Những thứ credit không chi trả | • Reserved Instances, Savings Plans, một số sản phẩm trên AWS Marketplace, Support Plans và đăng ký tên miền.<br>• Dù còn credit vẫn có thể bị tính tiền nếu dùng dịch vụ không được chi trả, vượt giới hạn Free Tier, dùng region không đủ điều kiện hoặc phát sinh phí truyền dữ liệu |
| Khi nào tài khoản Free Plan tự đóng | • Khi hết 6 tháng kể từ ngày tạo hoặc khi credit về 0, tùy điều nào đến trước.<br>• Credit không chuyển sang tài khoản khác được<br>• số credit còn lại xem ở mục Credits trong Billing Console |
| Nguyên tắc chung | Theo dõi chi phí thường xuyên, biết trước dịch vụ nào dễ làm hao credit |

- Bài Creating Your First AWS Account - 2 kiến trúc mẫu với 200$ credit:

| Kiến trúc              | Dùng cho                                           | Thành phần                                                                                       | Chi phí ước tính trong 6 tháng                                                                            |
| ---------------------- | -------------------------------------------------- | ------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------- |
| Simple Web Application | Blog cá nhân, portfolio, MVP | CloudFront, S3, ALB, EC2 t3.micro, RDS db.t3.micro Single-AZ | • Khoảng 232$, vượt 200$<br>• nếu quá cao thì lab gợi ý bỏ ALB và chạy Single AZ.<br>• ALB là phần đắt nhất, khoảng 99$ |
| Serverless Application | API backend, microservices, ứng dụng hướng sự kiện | CloudFront, Amplify với S3, Lambda, Bedrock Haiku 3, DynamoDB, Cognito, CloudWatch, SNS tùy chọn | • Khoảng 60$, giả định khoảng 1000 prompt mỗi tháng<br>• ưu điểm là rẻ, tự scale, không phải quản lý server |

- Bài Creating Your First AWS Account - quy trình theo dõi và tối ưu chi phí:
1. Mức cơ bản, tuần đầu: tạo nhiều budget, ví dụ 50$/tháng cảnh báo ở 80%, 25$/tháng cảnh báo ở 50%, 10$/ngày cảnh báo ở 100%; tạo CloudWatch Alarm cho billing ở các mốc 25$, 50$, 75$; bật báo cáo chi phí hằng ngày trong Cost Explorer và theo dõi 5 dịch vụ tốn tiền nhất
2. Mức nâng cao, tuần 2-4: dùng boto3 lấy chi phí theo ngày từ Cost Explorer rồi đẩy lên CloudWatch thành metric riêng; gắn tag bắt buộc cho tài nguyên như Project, Environment, Owner, CostCenter, AutoShutdown, CreatedDate
3. Khi đã tiêu trên 150$: xem dịch vụ nào tốn nhất bằng lệnh `aws ce get-cost-and-usage --granularity MONTHLY --metrics BlendedCost --group-by Type=DIMENSION,Key=SERVICE`, rồi dừng các instance không quan trọng bằng `aws ec2 stop-instances` kết hợp `aws ec2 describe-instances` lọc theo tag `Critical=false`
- Bài Creating Your First AWS Account - lộ trình học 6 tháng: tháng 1-2 học nền tảng EC2, S3, IAM, VPC, ngân sách khoảng 50-70$; tháng 3-4 học Lambda, API Gateway, ECS, CloudWatch, khoảng 60-80$; tháng 5-6 học kiến trúc nâng cao, CI/CD, bảo mật và tối ưu chi phí, khoảng 70-90$. Chứng chỉ được gợi ý theo thứ tự Cloud Practitioner, Solutions Architect Associate rồi Solutions Architect Professional.
- Bài Managing Costs with AWS Budgets - so sánh 4 loại ngân sách trong AWS Budgets:

| Loại ngân sách       | Theo dõi          | Chỉ số phải chọn khi tạo                                                                                                            | Ghi chú                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| -------------------- | ----------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Cost Budget | Chi phí | Ngưỡng cảnh báo Actual hoặc Forecasted | • Chọn Customize rồi Cost budget<br>• Budget name `Monthly`<br>• Period chọn Daily, Monthly, Quarterly hoặc Annually<br>• Recurring Budget để lặp lại định kỳ, Expiring Budget để áp dụng một lần<br>• Fixed nếu kỳ nào cũng bằng nhau, Monthly Budget Planning nếu mỗi tháng một mức<br>• Budget scope chọn All AWS services, Aggregate costs by chọn Unblended costs.<br>• Múi giờ trong AWS Budgets luôn là UTC.<br>• Muốn tạo nhanh thì dùng Use a template với mẫu Monthly cost budget.<br>• Số tiền mình đặt: 1$ |
| Usage Budget | Mức sử dụng | Budget against chọn Usage type groups, rồi chọn EC2: ELB - Running Hours để theo dõi số giờ chạy, sau đó nhập số giờ sử dụng tối đa |  |
| RI Budget | Reserved Instance | Coverage threshold | • Chọn Customize rồi Reservation budget, đặt tên, cấu hình Coverage threshold và Budget scope, nhập email ở Alert setting rồi Create budget.<br>• Phần này chỉ để minh họa vì Reserved Instance phải trả trước |
| Savings Plans Budget | Savings Plans | Utilization threshold | • Chọn Customize rồi Savings Plans budget, đặt tên, cấu hình Utilization threshold, Budget scope để mặc định, nhập email ở Alert setting rồi Create budget.<br>• Phần này cũng chỉ để minh họa vì Savings Plans phải cam kết trước<br>• Savings Plans rẻ hơn On-Demand tới 72%, đổi lại phải cam kết một lượng USD/giờ trong 1 hoặc 3 năm |

- Quy trình tạo và dọn dẹp 4 loại ngân sách trong bài Managing Costs with AWS Budgets:
1. Tạo Cost Budget
2. Tạo Usage Budget
3. Tạo RI Budget
4. Tạo Savings Plans Budget
5. Dọn dẹp: vào Billing and Cost Management, chọn Budgets, chọn từng budget, chọn Action rồi Delete, xác nhận Delete, làm lần lượt cho cả 4 budget
- So sánh hai kiểu ngưỡng cảnh báo:

| Kiểu ngưỡng | Dựa trên | Khi nào nên dùng |
|---|---|---|
| Actual | Chi phí thực tế | • Báo khi số tiền đã phát sinh thật vượt ngưỡng.<br>• Dùng để biết chắc mình đã tiêu tới đâu, nhưng chỉ báo sau khi tiền đã bị tính |
| Forecasted | Chi phí dự báo | • Báo khi AWS dự báo chi phí cả kỳ sẽ vượt ngưỡng, lúc tiền chưa phát sinh.<br>• Dùng để kịp tắt bớt tài nguyên.<br>• Một budget có thể đặt cả hai loại |

- So sánh Utilization và Coverage khi tạo RI Budget và Savings Plans Budget:

| Chỉ số | Ý nghĩa | Khác nhau ở đâu |
|---|---|---|
| Utilization | • Mức đã dùng hết phần RI hoặc Savings Plans đã mua<br>• cảnh báo khi tỉ lệ này tụt dưới ngưỡng, nghĩa là đang mua thừa và có phần cam kết bị bỏ phí | • Trong lab, Savings Plans Budget được cấu hình bằng Utilization threshold<br>• lab gợi ý đặt cảnh báo ở mức 80-90% để còn thời gian điều chỉnh |
| Coverage | • Tỉ lệ phần sử dụng được RI hoặc Savings Plans chi trả<br>• cảnh báo khi tỉ lệ này tụt dưới ngưỡng, nghĩa là đang trả giá On-Demand cho nhiều phần hơn mong muốn | Trong lab, RI Budget được cấu hình bằng Coverage threshold |

- Bài Getting Help with AWS Support:

| Nội dung                          | Mình đã học được                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Các gói AWS Support | • Được hỗ trợ tới đâu thì tùy gói đang dùng.<br>Có 4 gói từ thấp đến cao, gói cao có đủ tính năng của gói thấp hơn:<br>• Basic miễn phí, có chat về tài khoản và thanh toán, AWS Support Forums, AWS Health Dashboard và tài liệu<br>• Business Support+ dành cho workload production, hỗ trợ kỹ thuật 24/7 qua điện thoại, chat, email, không giới hạn case, có đủ kiểm tra của Trusted Advisor và AWS Support API<br>• Enterprise Support có thêm Technical Account Manager, Concierge Support Team, Well-Architected Reviews và phản hồi dưới 15 phút khi hệ thống quan trọng ngưng hoạt động<br>• Unified Operations có thêm AWS Managed Services để AWS vận hành hạ tầng thay mình |
| Cách vào trang Support và đổi gói | Theo lab:<br>• mở AWS Management Console, tìm AWS Support, trong AWS Support Center chọn Manage Support Plan, chọn gói mới (ví dụ Business Support+) rồi Get started, chọn My account, tick ô đồng ý điều khoản, nhấn Confirm, khoảng 15 phút sau gói được đổi.<br>• Tài khoản mặc định dùng gói Basic<br>• nâng gói sẽ làm tăng chi phí hàng tháng, và phí Support Plans không được credit chi trả |
| Loại yêu cầu hỗ trợ | Có 3 loại:<br>• Account and Billing Support cho hóa đơn, thanh toán, xác minh tài khoản, thuế, gói nào cũng dùng được<br>• Service limit increase để xin tăng hạn mức mặc định của dịch vụ, gói nào cũng dùng được, nên gửi trước 2-3 ngày làm việc<br>• Technical support cho vấn đề kỹ thuật, gói Basic không tạo được, phải từ Business Support+ trở lên |
| Mức độ nghiêm trọng | Có 5 mức, tính theo thời gian phản hồi lần đầu:<br>• Hướng dẫn thông thường 24 giờ<br>• Ảnh hưởng đến hệ thống 12 giờ<br>• Ảnh hưởng đến hệ thống Production 4 giờ<br>• Hệ thống Production ngưng hoạt động 1 giờ<br>• Hệ thống quan trọng ngưng hoạt động 15 phút, mức này chỉ có ở Enterprise Support và Unified Operations.<br>• Ví dụ trong lab dùng General question cho case hóa đơn.<br>• Khi tạo yêu cầu, mình chọn mức Hướng dẫn thông thường 24 giờ |
| Quy trình tạo yêu cầu hỗ trợ | Chọn loại yêu cầu (Account and Billing Support, Service limit increase hoặc Technical support), chọn mức độ nghiêm trọng phù hợp rồi gửi |

### Tài liệu tham khảo

* <https://000001.awsstudygroup.com/>
* <https://000007.awsstudygroup.com/>
* <https://000009.awsstudygroup.com/>
* <https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-managing-costs.html>
* <https://000001.awsstudygroup.com/vi/6-ki%E1%BA%BFn-tr%C3%BAc-m%E1%BA%ABu-v%E1%BB%9Bi-200-credit/>
* <https://000001.awsstudygroup.com/vi/7-monitoring-v%C3%A0-t%E1%BB%91i-%C6%B0u-chi-ph%C3%AD/>
* <https://000001.awsstudygroup.com/vi/8-faq---gi%E1%BA%A3i-%C4%91%C3%A1p-m%E1%BB%8Di-th%E1%BA%AFc-m%E1%BA%AFc/>
* <https://000001.awsstudygroup.com/vi/9-roadmap-h%E1%BB%8Dc-aws-v%E1%BB%9Bi-free-tier/>
* <https://000007.awsstudygroup.com/vi/3-usage-budget/>
* <https://000007.awsstudygroup.com/vi/4-reservation-budget/>
* <https://000007.awsstudygroup.com/vi/5-saving-plans-budget/>
* <https://000007.awsstudygroup.com/vi/6-clean-up/>

### Hình ảnh minh chứng:

![Getting Help with AWS Support](/images/1-worklog/1.2-week2/1.2.3-day3/evd-0020.png)

*Getting Help with AWS Support*

![Managing Costs with AWS Budgets](/images/1-worklog/1.2-week2/1.2.3-day3/evd-0021.png)

*Managing Costs with AWS Budgets*

![List of Credit "Killers" to Avoid](/images/1-worklog/1.2-week2/1.2.3-day3/evd-0022.png)

*List of Credit "Killers" to Avoid*

![Detailed Guide for 5 "Money-Making" Tasks](/images/1-worklog/1.2-week2/1.2.3-day3/evd-0023.png)

*Detailed Guide for 5 "Money-Making" Tasks*
