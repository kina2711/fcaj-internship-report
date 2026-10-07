---
title: "Event 2"
date: 2026-01-01
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# Bài thu hoạch: "Fireside chat with Dr. Werner: Navigating the future of cloud & AI in Vietnam"

**Tên sự kiện:** Fireside chat with Dr. Werner: Navigating the future of cloud & AI in Vietnam

**Thời gian:** 02/10/2026

**Địa điểm:** Bitexco Finance Tower, 2 Đ. Hải Triều, Sài Gòn, Hồ Chí Minh, Việt Nam

**Vai trò:** Người tham dự

### Mục tiêu sự kiện
* Trả lời câu hỏi mở đầu buổi trò chuyện: thời đại AI đang thay đổi công việc của người làm kỹ thuật thế nào, và người xây dựng sản phẩm nên làm gì.
* Nghe Dr. Werner Vogels kể lại ba chuyện từ những năm đầu ở Amazon: sự cố cơ sở dữ liệu ngày 12/12 dẫn tới Dynamo rồi DynamoDB, ba năm xây văn hóa kỹ thuật (đo lường, loại bỏ điểm lỗi đơn lẻ, hiệu quả chi phí), và lý do AWS ra đời với mô hình dùng bao nhiêu trả bấy nhiêu.
* Nắm được năm phẩm chất ông nêu cho người kỹ sư tương lai: học suốt đời, tư duy hệ thống, tinh thần làm chủ, hiểu biết rộng, và quan trọng nhất là giao tiếp.
* Hiểu AI rút ngắn quãng đường từ ý tưởng đến bản chạy thử ra sao, và vì sao Amazon vẫn dùng quy trình Working Backwards để quyết định sẽ xây gì.

### Diễn giả
* **Dr. Werner Vogels**: Chief Technology Officer and Vice President of Amazon
* **My Nguyen**: Sr Prototyping Architect, AWS Vietnam, người dẫn buổi trò chuyện
* **Nguyen Gia Hung**: Solutions Architect Manager, AWS Vietnam

### Nội dung nổi bật

#### Từ "hiệu sách" đến những bài toán hệ phân tán ở quy mô thật
* Trước khi về Amazon, Dr. Werner nghiên cứu hệ phân tán lớn ở trường đại học. Lần đầu được mời tới nói chuyện, ông nghĩ Amazon chỉ là một hiệu sách, có một máy chủ web với một cơ sở dữ liệu là xong. Đến nơi ông mới thấy Amazon phải tự xây gần như mọi thứ, từ cơ sở dữ liệu tới hệ thống nhắn tin, vì phần mềm thương mại không chạy nổi ở quy mô của họ. Hồi đó Amazon lớn gấp mười lần mỗi năm.
* Ông kể về sự cố ngày 12/12, hạn chót gửi hàng cho kịp Giáng sinh và cũng là ngày bận nhất trong năm. Cụm cơ sở dữ liệu quan hệ lưu thông tin khách hàng, chạy theo kiểu nhiều máy dùng chung ổ đĩa, dính một lỗi phần mềm chỉ lộ ra khi tải rất cao. Hệ thống đứng cả ngày, Amazon mất hàng triệu đô la. Nhà cung cấp tới và câu đầu tiên họ nói là "lẽ ra các anh phải kiểm thử kỹ hơn". Ông thừa nhận họ nói đúng: Amazon đã dùng phần mềm vượt xa giới hạn nó được thiết kế.
* Sau sự cố, ông giao cho Swami, lúc đó là thực tập sinh và nay phụ trách mảng AI ở AWS, tìm hiểu Amazon thật sự dùng cơ sở dữ liệu quan hệ thế nào. Kết quả: khoảng 70% là truy cập kiểu khóa - giá trị, khoảng 20% là bảng đơn có cấu trúc nhưng không liên quan tới bảng nào khác, chỉ khoảng 10% thật sự cần đến quan hệ. Ông lấy ví dụ giỏ hàng: không ai truy vấn "mọi giỏ hàng có Harry Potter", người ta chỉ lấy giỏ hàng theo mã khách hàng. Nếu cần truy vấn kiểu kia thì để cho hệ thống quản trị phía sau chạy chậm cũng được. Từ phân tích đó mới có Dynamo, rồi sau này là DynamoDB.

#### Ba năm xây dựng văn hóa kỹ thuật: đo lường, chịu lỗi và hiệu quả
* Năm của số liệu đo lường: không biết hệ thống đang chạy ra sao thì chẳng khác gì bay mù, mà hồi năm 2000 chưa có sẵn công cụ như bây giờ. Ông lấy ví dụ độ trễ trung vị 1,5 giây: con số đó gần như không nói lên điều gì, vì ít nhất 50% khách hàng đang gặp trải nghiệm tệ hơn. Cách làm của Amazon:
  1. Đo độ trễ ở mức 99,9% thay vì trung vị.
  2. Xây văn hóa kỹ thuật để kéo phần đuôi ấy vào dần.
  3. Dừng khi bỏ thêm công sức mà độ trễ cũng không cải thiện được bao nhiêu nữa.
* Năm loại bỏ điểm lỗi đơn lẻ: quy tắc là chạy trên ít nhất ba trung tâm dữ liệu. Mất một trung tâm thì khách hàng vẫn phải dùng được trên hai trung tâm còn lại, có thể chậm hơn hoặc thiếu bớt tính năng. Để kiểm chứng, Amazon tổ chức "game day":
  1. Báo trước cho mọi đội rằng sẽ có diễn tập.
  2. Cắt mạng vào một trung tâm dữ liệu để nó trông như đã biến mất.
  3. Xem hệ thống và con người phản ứng ra sao, ghi lại chỗ hỏng.
  4. Sửa rồi lặp lại game day cho tới khi hết vấn đề.
  Lần đầu làm, đội nào cũng nói mình sẵn sàng nhưng thực tế lại khác: nhiều thao tác vẫn cần người làm tay, chẳng hạn chuyển đổi dự phòng cơ sở dữ liệu. Người phải lên văn phòng, phải đăng nhập, nên không phản ứng nhanh được. Tức là chính con người cũng thành một điểm lỗi đơn lẻ.
* Amazon còn rút ra thêm một điều: họ biết cách chuyển sang hai trung tâm còn lại, nhưng chưa có quy trình đồng bộ những cập nhật đã ghi ở hai trung tâm đó khi trung tâm cũ chạy lại. Phải thử thật họ mới phát hiện ra. Ông nhắc câu "everything fails": cần lên kế hoạch cho lỗi, kể cả lúc thành phần hỏng quay về.
* Năm tập trung vào hiệu quả chi phí: ông thừa nhận nỗ lực này thất bại. Kỹ sư Amazon được tuyển để lo cho khách hàng, nên họ thích làm ý tưởng mới cho khách hơn là ngồi tối ưu chi phí, vốn là chuyện của công ty và cổ đông.

#### Sự ra đời của AWS và mô hình kinh tế mới
* Khoảng năm 2000, nhiều công ty mở API cho các chức năng cốt lõi để xem người ngoài làm được gì từ đó. Amazon mở API cho bốn thứ: danh mục sản phẩm, tìm kiếm, giỏ hàng và thanh toán. Người ngoài dùng chúng để làm trang so sánh giá và những giao diện hoàn toàn mới. Đã có kinh nghiệm xây hạ tầng dùng chung cho các nhóm nhỏ trong nội bộ, Amazon muốn những công ty khác cần đạt quy mô internet cũng được hưởng lợi. Khi S3 ra mắt, khẩu hiệu là "storage for the internet": họ nghĩ tới những doanh nghiệp giống Amazon, không phải điện toán doanh nghiệp truyền thống.
* Với các nhà cung cấp cơ sở dữ liệu lớn, muốn được giảm giá thì chỉ có cách ký hợp đồng 5 đến 10 năm và trả tiền trước, dù chẳng ai biết 5 năm nữa mình cần bao nhiêu cơ sở dữ liệu. Nhà cung cấp còn tới kiểm tra mức sử dụng và phạt nếu dùng vượt. Nhận tiền rồi, họ cũng không còn mấy động lực hỗ trợ, muốn được giúp thì phải trả thêm. Theo ông, quyền lúc đó nằm trong tay nhà cung cấp chứ không ở phía khách hàng.
* AWS làm ngược lại: dùng bao nhiêu trả bấy nhiêu, không ràng buộc hợp đồng, muốn rời đi lúc nào cũng được. Ông so với nhà hàng: chẳng ai chịu đặt một khoản tiền lớn lên bàn mới được vào ăn, ăn ít thì nhà hàng giữ phần còn lại. Mô hình này buộc AWS ngày nào cũng phải đem lại giá trị tốt nhất, nếu không khách sẽ bỏ đi. Nó đã thay đổi mô hình kinh tế của cả ngành, các công ty lớn quen sống bằng hợp đồng khổng lồ đều phải đổi theo.

#### Người kỹ sư thời "Renaissance": học suốt đời, tư duy hệ thống, làm chủ
* Với câu hỏi "công việc của tôi có biến mất không", ông nói có lẽ là không, nhưng ai không thay đổi sẽ bị bỏ lại. Công cụ thì lúc nào cũng đổi: hồi đi học ông học Cobol và hợp ngữ, giờ không ai viết nữa; môi trường lập trình đi từ thế hệ đầu, qua Visual Studio, tới Cursor bây giờ. Người kỹ sư phải chấp nhận học suốt đời.
* Ông dẫn lời Grace Hopper, người được xem là một trong những lập trình viên đầu tiên: câu nguy hiểm nhất trong tiếng Anh là "we've always done it like this". Đội nào tự nhận "chúng tôi là Java shop" và nghĩ sẽ chạy Java mãi thì nhiều khả năng sẽ sai.
* Tư duy hệ thống: nhìn bức tranh lớn, cả mặt tốt lẫn mặt xấu, thấy được các thành phần liên quan với nhau thế nào thay vì chỉ nhìn vào một mô-đun hay một dịch vụ nhỏ.
* Tinh thần làm chủ: dùng AI sinh code mà code có lỗi thì người làm chịu trách nhiệm, không phải công cụ. Ở các ngành bị quản lý chặt như tài chính hay y tế, cơ quan quản lý tới hỏi thì không thể đổ lỗi cho công cụ. Ông nhắc tới những tin gần đây về các tác tử AI vượt khỏi giới hạn và hàng chục nghìn trang web bị xâm phạm: lỗi không nằm ở tác tử, ai sở hữu tác tử thì người đó chịu trách nhiệm.
* Hiểu biết rộng: các công ty từng khen thưởng kỹ sư đào thật sâu vào một chuyên môn, kiểu kỹ sư "hình chữ I". Ông muốn kỹ sư "hình chữ T": vẫn giỏi sâu, ví dụ vẫn là chuyên gia cơ sở dữ liệu, nhưng dùng hiểu biết đó để giúp đồng nghiệp làm giao diện hay logic nghiệp vụ, và ngược lại hiểu dữ liệu của mình được dùng ra sao để làm tốt hơn phần của mình. Công ty cũng phải đổi những gì mình khen thưởng.
* Amazon tin vào nhóm nhỏ khoảng 10 đến 12 người, hai chiếc pizza là đủ ăn. Muốn nhanh và linh hoạt thì giữ nhóm nhỏ để ai cũng biết người khác đang làm gì.
* Ông có nhắc tới lập luận hình thức và kiểm chứng hình thức, nhất là trong bảo mật: phải chứng minh được phần mềm làm đúng điều mình bảo, ví dụ chứng minh một tác tử AI không thể thoát khỏi môi trường cách ly. Với khách hàng, việc đó lý tưởng nhất chỉ nên là một nút bấm. Có những kỹ thuật tưởng chẳng liên quan tới công việc của một kỹ sư cơ sở dữ liệu mà về lâu dài lại có ích.

#### Giao tiếp: kỹ năng bị đánh giá thấp nhất
* Ông cho rằng giao tiếp là kỹ năng bị xem nhẹ nhất, vì xưa nay ít ai bỏ công vào nó. Viết là một kỹ năng rất tốt; AI có thể hỗ trợ, nhưng đừng để AI viết thay mình.
* Khách hàng, dù ở ngoài hay trong công ty, hay đến với câu "chúng tôi cần dùng AI để xây cái này". Việc của kỹ sư là tìm ra điều thật sự quan trọng với họ và xem công nghệ họ đang nghĩ tới có hợp với bài toán không. Ông nhắc rằng AI đã có khoảng 70 năm, thuật ngữ này xuất hiện từ những năm 1950, và nhiều ứng dụng như dự báo, dịch, quét tài liệu y tế đã chạy tốt từ lâu.
* Nên hỏi "bài toán bạn chưa giải được là gì". Ví dụ, nâng cấp phiên bản Java không chỉ là thay máy ảo mà còn phải sửa code. Với khoảng 4.500 ứng dụng Java thì đó là cả núi việc lặp đi lặp lại, tự động hóa được thì tốt vì rủi ro tương đối thấp.
* Về độ sẵn sàng của web và ứng dụng di động Amazon, ông đi qua từng bước của cuộc trao đổi với bên kinh doanh:
  1. Hỏi họ hệ thống cần sẵn sàng tới mức nào. Câu trả lời lúc nào cũng là "bốn số 9".
  2. Giải thích bốn số 9 tốn bao nhiêu, vì nó đòi hỏi nhân bản qua nhiều trung tâm dữ liệu, rồi so với ba số 9 và hai số 9.
  3. Cùng họ xác định chức năng nào luôn phải chạy. Ở Amazon có năm chức năng: tìm kiếm, duyệt sản phẩm, thanh toán, giỏ hàng và đánh giá, vì đánh giá mà ngừng thì người ta không mua.
  4. Đặt mức sẵn sàng thấp hơn cho những phần quan trọng với khách nhưng không cốt lõi, như gợi ý sản phẩm, để đỡ tốn.
* Ông còn kể vài ví dụ khác về việc đào sâu vào bài toán: công ty luật cần AI gom tài liệu trước khi viết bản tóm tắt vụ việc; Amazon dùng hàng tỷ đơn hàng cũ để xây mô hình chấm điểm đơn mới, đơn đáng ngờ được chuyển cho người kiểm tra chứ không bị loại; kỹ sư bảo mật phải tra cơ sở dữ liệu khách hàng, mở thêm tệp và làm cả chục việc khác trước khi xử lý mỗi ticket.
* Ông nhắc tới một người từng làm ở Amazon, sau làm CEO và viết sách khuyên các CEO: muốn biết tương lai thì cứ xuống phòng kỹ sư mà hỏi, vì kỹ sư thường đã biết công cụ nào là đúng. Điều đó chỉ xảy ra khi kỹ sư giao tiếp tốt.
* Người dẫn nói thêm rằng phỏng vấn kỹ sư gần như chỉ có viết code trực tiếp, không có vòng nào về giao tiếp. Dr. Werner bổ sung: kỹ sư junior chỉ thành senior khi đã mang "vết sẹo" từ những năm làm junior.

#### AI, prototype và quyết định xây gì tiếp theo
* Người dẫn hỏi: AI đã rút thời gian từ ý tưởng đến bản chạy thử được từ vài tuần xuống còn rất ngắn, vậy cách đội nhóm quyết định xây gì tiếp theo thay đổi ra sao?
* Dr. Werner giới thiệu quy trình Working Backwards của Amazon, dùng cho mọi thứ để chắc rằng mình hiểu đúng vấn đề của khách hàng. Quy trình có bốn tài liệu, ông nói kỹ hai tài liệu đầu:
  1. Viết một thông cáo báo chí mô tả rõ ràng, đơn giản sản phẩm hoặc tính năng mới làm được gì cho khách hàng.
  2. Viết tài liệu khoảng 10 đến 15 câu hỏi thường gặp, trả lời thật rõ những câu còn bỏ ngỏ.
  3. Sửa đi sửa lại qua nhiều vòng cho tới khi biết chính xác mình muốn xây gì, tất cả trước khi viết dòng code đầu tiên.
  Ông cũng nói kỹ sư hay nghĩ tới phiên bản 2 khi còn đang làm phiên bản 1 rồi nhét thêm đủ thứ vào; quy trình này giữ phiên bản 1 đúng với điều đã viết.
* Với thứ thật sự mới, chưa biết có hiệu quả hay không, thì nên làm bản chạy thử rồi tự dùng một thời gian. Ông kể có nhóm nhà khoa học tự ráp một công cụ để phục vụ nghiên cứu, càng nhiều người biết tới thì nó càng giống một sản phẩm, lúc đó họ vẫn quay lại viết tài liệu theo quy trình. Ví dụ khác là Amazon Fresh, dịch vụ giao thực phẩm: lúc đầu không ai biết khách muốn gì, trang web nên ra sao, giao giờ nào; sau mới thấy khung giờ giao hàng được chọn nhiều nhất là 6 giờ sáng. Khi đã rõ mình cần gì thì phải chuyển sang môi trường có khả năng mở rộng.
* Ông ví AI như một trình biên dịch: trình biên dịch nhận code và sinh mã máy mà không ai đọc lại, còn AI nhận ngôn ngữ tự nhiên và sinh ra code. Vì vậy việc quản lý code lại càng tốn công. Doanh nghiệp tài chính hay y tế chịu quy định pháp lý nên bỏ nhiều thời gian xem lại code do máy tạo ra, vì người làm vẫn phải chịu trách nhiệm.

#### Niềm tự hào nghề nghiệp
* Nhiều việc tốt nhất kỹ sư làm ra sẽ không ai nhìn thấy. Khách bấm mua rồi nhận hàng, chẳng nghĩ gì tới dự báo hay chống gian lận phía sau. Thứ giữ người kỹ sư đi tiếp là niềm tự hào nghề nghiệp: về cách thực thi, cách vận hành hệ thống và sự xuất sắc trong vận hành.
* Người dẫn kết lại: hãy tự hào về công việc của mình và phát huy những gì tốt đẹp nhất ở con người, vì cuối cùng chúng ta xây sản phẩm cho con người.

### Những gì học được
* Lỗi chắc chắn sẽ xảy ra, nên phải thiết kế để chịu lỗi: chạy trên ít nhất ba trung tâm dữ liệu, tự động hóa chuyển đổi dự phòng, và kiểm chứng bằng game day. Mình nhận ra kế hoạch trên giấy chưa đủ: phải cắt hẳn một trung tâm dữ liệu thì Amazon mới thấy những bước vẫn phải làm tay, và thấy mình chưa có quy trình đồng bộ lại dữ liệu khi trung tâm cũ quay về.
* Đo hiệu năng phải nhìn phần đuôi như mức 99,9%, đừng chỉ nhìn trung vị, vì trung vị che mất trải nghiệm của một nửa số khách hàng.
* Chọn công nghệ nên bắt đầu từ cách dữ liệu thật sự được dùng. Phân tích 70% khóa - giá trị, 20% bảng đơn, 10% cần quan hệ dẫn tới Dynamo rồi DynamoDB, cho thấy dùng "cái búa lớn" cơ sở dữ liệu quan hệ cho mọi việc vừa tốn kém vừa dễ hỏng khi lên quy mô lớn.
* Mô hình trả theo mức dùng của AWS trao quyền chủ động cho khách hàng và buộc nhà cung cấp phải liên tục tạo ra giá trị, trái với hợp đồng trả trước 5 đến 10 năm.
* Người kỹ sư thời AI cần học suốt đời, tư duy hệ thống, làm chủ sản phẩm của mình kể cả phần code do AI sinh ra, và là kỹ sư "hình chữ T" đủ rộng để hỗ trợ đồng đội trong một nhóm hai chiếc pizza.
* Giao tiếp là kỹ năng cốt lõi: hiểu bài toán thật của khách hàng trước khi nói tới AI, và giải thích được đánh đổi giữa độ sẵn sàng với chi phí, như cách chia năm chức năng luôn phải chạy với phần gợi ý sản phẩm được phép thấp hơn.
* AI giúp làm bản chạy thử nhanh hơn, nhưng mình vẫn phải hiểu khách hàng qua thông cáo báo chí và câu hỏi thường gặp của Working Backwards, và xem kỹ lại những gì AI làm ra, vì trách nhiệm cuối cùng vẫn thuộc về người kỹ sư.

### Áp dụng vào công việc
- Mình sẽ tự đọc và chạy thử lại mọi đoạn code AI gợi ý trước khi đưa vào workshop, vì mình là người chịu trách nhiệm.
- Mình sẽ viết một đoạn mô tả kiểu Working Backwards (workshop giúp người học làm được gì) trước khi bắt tay vào làm.
- Trước khi chọn RDS hay DynamoDB cho workshop, mình sẽ liệt kê các kiểu truy vấn thật để xem có cần quan hệ hay chỉ cần khóa - giá trị.

### Trải nghiệm sự kiện
- Mình khá hồi hộp khi lần đầu được nghe Dr. Werner Vogels nói chuyện trực tiếp.
- Mình nhớ nhất chuyện sự cố ngày 12/12 và con số 70% truy cập là khóa - giá trị, vì nó giải thích vì sao có DynamoDB.
- Mình bất ngờ khi ông nói giao tiếp là kỹ năng bị đánh giá thấp nhất, vì trước giờ mình chỉ tập trung vào kỹ thuật.
- Câu "everything fails" và chuyện game day làm mình nhìn lại cách mình thiết kế bài lab.

#### Hình ảnh sự kiện
![Check-in](/images/4-eventparticipated/4.2-event2/checkin.jpg)

*Hình 1: Check-in sự kiện.*

![222222222](/images/4-eventparticipated/4.2-event2/222222222.jpeg)
*Hình 2: Dr. Werner Vogels chia sẻ trên sân khấu cạnh chị My Nguyễn - người dẫn chương trình.*

<!-- Kiểm tra: sources.md không có phần "Bản nháp / ghi chép của bạn", còn Key learning và Reflection trong record vẫn trống, nên trang này không có ý nào chỉ đến từ ghi chép của bạn. Nên xem lại: chức danh của My Nguyen và Nguyen Gia Hung được đọc từ chữ nhỏ trên slide trong ảnh, hãy so với ảnh gốc; chức danh của Dr. Werner Vogels chưa có trong nguồn nào; số người trong nhóm hai pizza lấy theo transcript là 10 đến 12 người, còn bản tóm tắt MED-001 ghi 10 đến 13 người. Lần sửa này: bỏ chữ "CTO của Amazon" ở phần Trải nghiệm vì không nguồn nào ghi chức danh đó; transcript ghi Cobol còn MED-001 ghi Pascal, nên nghe lại đoạn [19:54]; MED-001 ghi đoạn Working Backwards và Amazon Fresh [43:33-47:30] rất khó nghe, nên nghe lại trước khi nộp; nguồn không có lệnh hay cấu hình nào nên trang không thêm phần đó. -->
