---
title: "Ngày 1 - 05/10/2026"
date: 2026-01-01
weight: 1
chapter: false
pre: " <b> 1.2.1. </b> "
---

### Mục tiêu

- Nắm luật chơi của First Cloud AI Journey: nêu đủ 6 nguyên tắc, yêu cầu tốt nghiệp 5 project, mốc 6 tháng, và đối chiếu được checklist 7 việc cần xong trước Module 1.
- Học phần nền của Module 1: phân biệt được Data Center, Availability Zone, Region, Edge Location, Local Zone; nêu được 3 cách làm việc với AWS (Management Console, AWS CLI, AWS SDK) và thông tin xác thực của từng cách.
- Làm quen Kiro: nêu được khác biệt giữa chế độ Vibe và Spec, các thành phần của một Agent Hook, và các lệnh Kiro CLI cơ bản.
- Nắm cách tối ưu chi phí: kể được 8 nguyên tắc tối ưu chi phí, 4 gói AWS Support, và biết đặt cảnh báo AWS Budgets ở cả mức dự báo.
- Nắm bộ quy ước vẽ kiến trúc trên draw.io đủ để tự vẽ lại sơ đồ VPC 2 Availability Zone và xuất ra file XML mà không phải xem lại video.
- Nắm quy trình 8 bước viết workshop và cách dựng site bằng Hugo với theme Learn, chạy được ở `https://kina2711.github.io/workshop-practice/`.

### Công việc đã thực hiện

- Xem video Prologue: Know before you join First Cloud AI Journey.
- Xem video Hướng dẫn vẽ kiến trúc AWS trên draw.io.
- Xem video Module 01-01 - Introduction to AWS.
- Xem video Hướng dẫn làm workshop AWS.
- Xem video Module 01-02 Management Console.
- Xem video Module 01-03 Gen AI on AWS - Kiro.
- Xem video Module 01-04 Cost optimization on AWS.
- Quy tắc chương trình: 6 nguyên tắc, yêu cầu tốt nghiệp 5 project, mốc thời gian 6 tháng, checklist chuẩn bị trước Module 1.
- Khái niệm điện toán đám mây, mô hình dùng bao nhiêu trả bấy nhiêu, 4 nhóm lợi ích so với hạ tầng tại chỗ.
- Hạ tầng toàn cầu AWS: Data Center, Availability Zone, Region, Edge Location, Local Zone.
- Ba cách tương tác với AWS: Management Console, AWS CLI, AWS SDK và cơ chế xác thực tương ứng.
- Phát triển theo đặc tả và bộ tính năng của Kiro: Kiro IDE, Kiro CLI, Agent Hook, steering file, Kiro Powers.
- Nguyên tắc tối ưu chi phí, AWS Pricing Calculator, bốn gói AWS Support, AWS Well-Architected Framework.
- Quy ước vẽ kiến trúc trên draw.io và quy trình làm workshop bằng Hugo với theme Learn.

### Kết quả

- Phân biệt được Data Center, Availability Zone, Region, Edge Location và Local Zone; nắm khuyến nghị triển khai tối thiểu 2 Availability Zone và ý nghĩa của việc cô lập sự cố giữa các AZ.
- Hiểu khác biệt giữa root user và IAM user khi đăng nhập Management Console; đăng nhập IAM user cần Account ID 12 chữ số hoặc account alias.
- Nắm ba đường vào dịch vụ AWS: Console dùng password, CLI và SDK dùng access key cùng secret access key, cả ba đều gửi yêu cầu tới AWS Services Endpoint.
- Nắm bộ tính năng Kiro: chế độ Vibe và Spec, Agent Hook chạy theo sự kiện file, 3 steering file `product.md`, `tech.md`, `structure.md`, Timeline Checkpointing, Property-Based Testing, Kiro CLI với custom agent và MCP.
- Nắm các hướng tối ưu chi phí: chọn cấu hình sát nhu cầu, Reserved, Savings Plans và Spot, tự động tắt tài nguyên, serverless hoặc fully managed, AWS Budgets kết hợp cost allocation tags, AWS Pricing Calculator.
- Nắm bộ quy ước vẽ kiến trúc trên draw.io: khung ngoài theo tỉ lệ vàng 1.618, icon đưa về size 60, nhãn nền trắng, viền cam `FF8000` cho dịch vụ và viền xanh `0000FF` cho tính năng, lưu thành phần đã định dạng vào Library, nộp bài bằng file XML.
- Nắm các lệnh Hugo `hugo version`, `hugo`, `hugo server` và quy ước thư mục `content`, `static/images`, `public` của workshop mẫu.

### Khó khăn & cách xử lý

- Mình mở draw.io nhưng panel trái không có bộ icon AWS, gõ ALB hay IAM vào ô tìm shape cũng không ra. → Thì ra ở draw.io bản mới, bộ icon này nằm ẩn trong list shapes. Phải nhấn vào "More Shapes", sau đó tick chọn vào AWS2026 thì mới xuất hiện bộ icon AWS.

### Bài học rút ra


**Kiến thức nền Module 1**

- Không so sánh hai nền tảng cloud theo số CPU và dung lượng RAM 1-1, phải kiểm thử hiệu năng ở tầng ứng dụng vì phần cứng AWS đã được tùy biến.
- Region mặc định độc lập với nhau, ngoại lệ là các dịch vụ ở quy mô toàn cầu như DNS. Edge Location tại Việt Nam hiện có ở Hà Nội và Hồ Chí Minh.
    - Khuyến nghị triển khai tối thiểu 2 Availability Zone. Khi thi chứng chỉ thì luôn thiết kế 2 AZ.
    - Nếu vì chi phí chỉ dùng 1 AZ, làm theo thứ tự sau:
            1. Xác định trước tình huống AZ đó gặp sự cố.
            2. Chọn một trong hai cách: sao lưu hoặc đồng bộ dữ liệu sang AZ khác; hoặc sao lưu vào dịch vụ lưu trữ có cơ chế nhân bản dữ liệu qua nhiều AZ.
            3. Kết quả mong đợi: một AZ hỏng thì vẫn phục hồi được hệ thống.
    - Với khách hàng cần kế hoạch khắc phục thảm họa như ngành tài chính, hệ thống chính đặt ở một Region, ví dụ Singapore, còn hệ thống Disaster Recovery đặt ở Region khác, ví dụ Malaysia.
    - File tĩnh, video, hình ảnh hay được tải nên đưa ra Edge Location ở Hà Nội và Hồ Chí Minh qua CloudFront để người dùng không phải tải từ Singapore về mỗi lần. Ở Edge còn có WAF và Route 53.
    - Local Zone là phiên bản nhỏ hơn của AZ, đặt tại Việt Nam và kết nối trực tiếp tới Region Singapore; dùng khi cần trải nghiệm tốt hơn và cần dữ liệu nằm tại Việt Nam để đáp ứng yêu cầu tuân thủ.

**Management Console, AWS CLI, AWS SDK**

- Root user chỉ dùng để đăng ký, sau đó bật MFA và cất đi; công việc hằng ngày dùng IAM user. Access key bị lộ tương đương lộ password vào môi trường của mình.
    - Trong doanh nghiệp, thông tin root nên chia cho nhiều người giữ: một người giữ số điện thoại, một người giữ email và password, một người giữ khóa MFA phần cứng. Chia càng nhỏ càng tốt, tốt nhất là niêm phong và không dùng nữa.
- Luồng đăng nhập Console:
    1. Vào `https://aws.amazon.com/console/`. Chưa có tài khoản thì bấm New to AWS? Sign up.
    2. Ở form Sign In, mục User type, chọn Root user rồi nhập Email address và bấm Next; hoặc chọn IAM user rồi nhập Account ID 12 chữ số hoặc account alias và bấm Next.
    3. Đăng nhập thành công sẽ vào Console Home. Tìm dịch vụ bằng ô Search với phím tắt Alt+S hoặc mở All services để duyệt theo nhóm như Compute, Containers, Management & Governance.
    4. Mỗi dịch vụ là một service, bên trong có nhiều feature, ví dụ EC2 có tính năng tạo máy chủ ảo và tạo ổ đĩa ảo gắn vào máy chủ.
- Lộ trình học được khuyến nghị, theo thứ tự:
    1. Management Console trước, để có cái nhìn tổng quan và quen các thành phần cần có khi tạo một dịch vụ; một số thao tác chỉ làm được trên Console.
    2. AWS CLI khi đã quen, cấu hình access key và secret access key để viết script tự động hóa việc lặp lại.
    3. AWS SDK theo ngôn ngữ khi cần viết ứng dụng tự gọi AWS, ví dụ app Python tự tạo máy chủ ảo. SDK lo phần quản lý thông tin đăng nhập, thử lại yêu cầu, chuyển đổi và tuần tự hóa dữ liệu.
- Không đưa access key lên GitHub; bảo vệ access key như bảo vệ password.
- Khi gặp sự cố về thanh toán, tạo account, xác thực thông tin hoặc quên tắt máy chủ gây phát sinh chi phí:
    1. Bấm icon ? trên thanh trên cùng.
    2. Chọn Support rồi Support Center.
    3. Tạo support case gửi đội ngũ AWS.
    4. Trong một số trường hợp, nếu chứng minh được là quên tắt và đã tắt tài nguyên thực hành, có thể được hoàn tiền. Giảng viên chỉ nói "có thể", không cam kết.

**Tối ưu chi phí và AWS Support**

- Các nguyên tắc tối ưu chi phí:
    1. Chọn cấu hình compute, storage, network sát nhu cầu hiện tại, khi cần mới tăng; không bê nguyên cấu hình on-premises vốn hay mua dư cho 3 tới 5 năm. Phải xem cách tính giá của từng dịch vụ, ví dụ lưu trữ có cách tính theo dung lượng và có cách tính theo IOPS.
    2. Reserved và Savings Plans là trả trước, cam kết 1 hoặc 3 năm để được chiết khấu, cam kết càng lâu giảm càng nhiều. Spot là thuê tài nguyên dư với giá thấp nhưng AWS lấy lại ngay khi cần, chỉ dùng khi ứng dụng chịu được.
    3. Xóa tài nguyên không dùng và bật tự động tắt tài nguyên không cần chạy 24/7, ví dụ máy chủ chỉ bật 8 tiếng trong giờ làm việc.
    4. Serverless hoặc fully managed tính tiền theo mức dùng thực, hợp với lượng truy cập lác đác; nếu tận dụng hết hiệu suất máy chủ thì thuê nguyên máy chủ có thể rẻ hơn.
    5. Thiết kế kiến trúc tối ưu là phần chất xám chính; tham khảo reference architecture và cân nhắc được mất giữa các lựa chọn.
    6. Quản lý được mới tối ưu được: dùng AWS Budgets để biết mức dùng hiện tại và dự báo cuối tháng; gắn cost allocation tags theo phòng ban, ứng dụng, tài nguyên để biết ai dùng bao nhiêu tiền.
    7. Tối ưu liên tục, xem lại mỗi khi có tính năng mới hoặc AWS ra lựa chọn giá mới.
    8. Dùng Kiro CLI sinh checklist tối ưu chi phí cho từng dịch vụ, ví dụ prompt `Create a Cost Optimization check list for EC2`, để không bỏ sót mục nào. Mỗi prompt chỉ cho một dịch vụ, kết quả là một file checklist markdown.
- AWS Budgets: ngưỡng cảnh báo nên đặt cả ở mức dự báo, để được cảnh báo trước khi thực sự tiêu hết số tiền dự định.
    - Ví dụ trong video: đặt budget 25 hoặc 50 đô; khi thực hành bật dịch vụ A, dịch vụ B rồi quên tắt, chỉ sau một ngày hệ thống đã dự báo được cuối tháng sẽ vượt 25 đô và cảnh báo trước.
    - Lý do phải tự quản lý chi phí trên account cá nhân: không quản lý được account cá nhân thì doanh nghiệp không dám giao account doanh nghiệp, và hậu quả sai sót chi phí ở account doanh nghiệp lớn hơn nhiều.
    - Bài thực hành Get started with AWS Budgets, mã 000007, gồm 4 việc: tạo expense budget, tạo usage budget, tạo preset budget, tạo budget savings plan. Thao tác chi tiết từng bước chưa có trong note, cần làm theo trang bài 000007.
- Giá khác nhau theo region; region quy mô lớn thường rẻ hơn, nhưng Singapore là ngoại lệ do hạn chế không gian và điện, đắt hơn Thái Lan và Malaysia khoảng 10 tới 20%.
    - Trước khi đề xuất hay dự toán cho khách hàng, thiết kế xong phải tính chi phí cẩn thận bằng AWS Pricing Calculator tại `https://calculator.aws/#/`. Công cụ cho phép tạo bản ước tính, chia sẻ bản ước tính cho người khác, và kết quả thay đổi theo cấu hình lẫn region.
    - Cách mở: vào trang, bấm Create estimate để dùng không cần đăng nhập, hoặc Sign in for personalized estimates. Các bước nhập cấu hình sau đó chưa có trong note.
- Chọn gói AWS Support theo môi trường: Basic là gói mặc định, không có cam kết phản hồi nhanh; Developer cho môi trường test và dev; Business rất nên có khi chạy production; Enterprise cho doanh nghiệp lớn có hệ thống quan trọng, có kỹ sư riêng. Có thể nâng gói tạm thời trước sự kiện quan trọng rồi hạ xuống, nhưng không nên nâng hạ liên tục. Bài thực hành Support requests with AWS Support mã 000009.
- Nghiên cứu bổ sung AWS Well-Architected Framework tại `https://docs.aws.amazon.com/wellarchitected/`: framework gồm nhiều câu hỏi có hoặc không để đối chiếu kiến trúc với best practice; công cụ có sẵn trên Management Console, đi theo các bước sẽ sinh report, mỗi mục cần cải thiện kèm tài liệu đọc thêm. Tên và các bước cụ thể trên Console chưa có trong note.
- Checklist trước khi sang module tiếp theo gồm 5 mục:
    - [ ] Hoàn tất mọi bài thực hành, trong đó Create an AWS account mã 000001 có bước thiết lập MFA cho root.
    - [ ] Đã thiết lập Budget trên AWS account.
    - [ ] Đã cài Kiro IDE và Kiro CLI.
    - [ ] Hiểu mọi khái niệm, dịch vụ, tính năng của Module 1.
    - [ ] Đã nghiên cứu và đọc tài liệu AWS Well-Architected Framework.

**Kiro**

- Chọn chế độ khi bắt đầu:
    - Vibe: chat trước rồi build, hợp khi khám phá ý tưởng.
    - Spec: lên kế hoạch trước, Kiro dẫn dắt từ prompt ban đầu ra yêu cầu, thiết kế và danh sách task trước khi code; hợp với tính năng cần suy nghĩ sâu và dự án cần làm có cấu trúc.
- Agent Hook chạy theo 3 bước: sự kiện xảy ra, prompt được gửi cho agent ở nền, Kiro tự cập nhật file. Cách tạo một hook:
    1. Mở Create an agent hook, mô tả hook bằng ngôn ngữ tự nhiên, hoặc chọn gợi ý có sẵn như Update my documentation, Optimize my code, Language localization.
    2. Kiểm tra các trường Kiro sinh ra: Title, Description, Event, File path(s) to watch, Instructions for Kiro agent.
    3. Event chọn một trong 4 loại: File Created, File Saved, File Deleted, Manual Trigger.
    4. Ví dụ trong video: hook Changelog Updater, Event là File Saved, theo dõi `*.py`, `requirements.txt`, `conftest.py`, `migrate_categories.py`, `templates/*.html`; mỗi lần lưu file thì Kiro ghi vào `CHANGELOG.md` thời điểm, tên file đã đổi và tóm tắt thay đổi.
    5. Kết quả mong đợi: màn hình đổi thành Hook created, công tắc Hook enabled đang bật.
- Với project có sẵn, nên yêu cầu Kiro sinh steering file trước khi sửa. Kiro tạo trong `.kiro/steering/`: `product.md` cho phần nghiệp vụ, `tech.md` cho công nghệ và lệnh thường dùng, `structure.md` cho tổ chức project; có thể tự thêm steering như `coding-standards.md`.
- Dùng Timeline Checkpointing để thử nhiều hướng giải quyết và quay lại checkpoint bằng nút Restore khi cần; checkpoint có thể theo một file hoặc nhiều file.
- Property-Based Testing đọc yêu cầu viết theo định dạng EARS, sinh hàng trăm test case; chạy theo 3 cách: chạy tay sau khi sinh code, tự động qua Agent Hook, hoặc trong lúc thực thi task của spec.
- Lệnh Kiro CLI thấy trong video:
    - `kiro-cli` để khởi động.
    - `/agent list` để xem danh sách custom agent, `/agent swap devops-agent` để chuyển sang agent khác.
    - `/mcp` để xem các MCP server đã nạp.
    - `/tools` để xem server còn đang chờ; `kiro-cli settings mcp.initTimeout {timeout in int}` để tăng thời gian chờ nạp MCP server.
- Không kết nối quá nhiều MCP server cùng lúc vì tốn token, chiếm hết cửa sổ ngữ cảnh, chậm, kết quả kém và dễ bịa thông tin; dùng custom agent chỉ nạp đúng thứ cần, hoặc Kiro Powers chỉ kích hoạt khi cần.
- Học viên phải tạo tài khoản Kiro Free Tier, 50 credit mỗi tháng, chỉ áp dụng khi đăng nhập bằng tài khoản mạng xã hội. Bài thực hành Kiro Spec Driven Development mã 000180 là bắt buộc, gồm cài Kiro, đăng nhập Kiro IDE, build ứng dụng với Kiro SDD, thực hành Kiro SDD và giới thiệu Kiro CLI.

**Hướng dẫn làm workshop AWS**

- Quy trình làm workshop 8 bước:
    1. Làm lab một lần trước: phải tự hiểu kỹ thuật, giải pháp, kiến trúc rồi mới viết và chia sẻ được.
    2. Ghi chú những gì cần chuẩn bị hoặc bổ sung, ví dụ cấp quyền IAM Role, tạo policy, các yêu cầu tiên quyết.
    3. Lên cấu trúc bài: chia thành các phần, mỗi phần có các mục nhỏ; liệt kê nội dung, các bước và hình ảnh cần có cho từng mục. Workshop mẫu có 6 phần, bài hướng dẫn có 4 phần.
    4. Xóa tài nguyên đã tạo ở lần một.
    5. Làm lại lần hai: tự tin thì vừa làm vừa chụp hình; chưa chắc thì quay màn hình để nếu làm sai vẫn còn tư liệu chụp lại.
    6. Chỉnh sửa hình: đánh số thứ tự các bước trên hình rồi chèn vào bài.
    7. Viết nội dung hoàn chỉnh, sau đó kiểm tra lại định dạng, phông chữ, logo; thêm ghi chú quan trọng như cần chuẩn bị gì, tài nguyên nào tốn kém thì làm xong phải xóa ngay.
    8. Thêm tệp đính kèm như file code, Dockerfile, file YAML template CloudFormation.
- Cài công cụ, theo thứ tự:
    1. Visual Studio Code, sau đó vào Extensions cài Markdown All in One của Yu Zhang.
    2. Snagit để chụp và chỉnh ảnh, có bản FREE dùng thử; Active Presenter để quay màn hình.
    3. draw.io để vẽ kiến trúc, bấm Start để dùng trên trình duyệt hoặc Download để cài về máy; tải thêm bộ icon kiến trúc AWS.
    4. Hugo: trên Windows dùng một trong ba lệnh `choco install hugo-extended`, `scoop install hugo-extended`, `winget install Hugo.Hugo.Extended`, rồi chạy `hugo version` để kiểm tra.
    5. Theme hugo-theme-learn; trong `config.toml` khai báo `theme = "hugo-theme-learn"` và khối `[outputs]` với `home = [ "HTML", "RSS", "JSON"]` để có chức năng tìm kiếm.
- Lệnh Hugo: `hugo version` kiểm tra cài đặt; `hugo` build toàn bộ Markdown thành website tĩnh trong thư mục `public`, đây là thứ đem deploy; `hugo server` chạy web server local ở `localhost:1313`, chạy nhiều site cùng lúc thì cổng có thể khác. Khi chạy `hugo serve`, trang tự làm mới mỗi khi file thay đổi.
- Quy ước cấu trúc file: thư mục `content` chia theo folder, mỗi folder là một phần và tối đa 2 cấp, ví dụ 2. và 2.1.; mỗi thư mục có `_index.md` cho tiếng Anh và `_index.vi.md` cho tiếng Việt, nếu mới viết tiếng Việt thì copy `_index.vi.md` thành `_index.md` để dịch sau; ảnh để trong `static/images`, có thể chia thư mục con; `public` do Hugo tạo khi build. Bài tự kiểm tra của trang 3.1: xóa thư mục `public` rồi chạy lại xem site còn hoạt động không.
- Quy ước viết nội dung cho một trang:
    1. Front Matter gồm `title`, `date`, `weight`, `chapter`, `pre`, trong đó `weight` quyết định thứ tự. Ví dụ của workshop mẫu: `title : "Viết nội dung"`, `weight : 2`, `chapter : false`, `pre : " <b> 2. </b> "`.
    2. Tiêu đề các section trong một trang thống nhất dùng h4 `####`.
    3. Viết xong các heading thì sinh mục lục bằng Ctrl + Shift + P, gõ Create Table of Contents, chọn lựa chọn của Markdown All in One rồi Enter.
    4. Icon giới thiệu chèn bằng shortcode `figure`, ví dụ `{{</* figure src="../images/fcj.png" title="First Cloud Journey" width=150pc */>}}`.
    5. Ghi chú dùng shortcode Notice với 4 loại Note, Info, Tip, Warning. Cú pháp cụ thể của Notice chưa có trong note.
    6. Tệp đính kèm đặt trong thư mục trùng tên trang như `_index.files` và `_index.vi.files`, rồi dùng shortcode `attachments` với `title` và `pattern`, ví dụ `{{%/*attachments title="Dockerfile" pattern="Dockerfile"/*/%}}`.
    7. Bảng tạo bằng Tables Generator: chọn tab Markdown, đặt số hàng và cột ở menu Table, nhập dữ liệu, bấm Generate rồi Copy to clipboard và dán vào file.
- Tiêu chuẩn hình ảnh: chụp trên Chrome và tắt bookmark bar, giữ zoom 100%, màn hình Full HD 1920 x 1080, định dạng PNG, chữ trên ảnh size 18; khi chèn dùng `?width=90pc` cho ảnh toàn màn hình, `?width=40pc` hoặc `?width=50pc` cho ảnh crop; viết đa ngôn ngữ thì phải cập nhật `config.toml`.

**Hướng dẫn vẽ kiến trúc AWS bằng draw.io**


**1. Chuẩn bị công cụ**

1. Mở draw.io, tạo diagram mới, trong cây danh mục chọn Cloud rồi AWS, chọn template bất kỳ và bấm Create. Làm vậy thì toàn bộ bộ icon AWS nằm sẵn ở panel trái. Nếu không thấy icon AWS thì thường là do bỏ qua bước chọn Cloud rồi AWS này.
2. Chọn folder trên Google Drive để lưu; mọi sơ đồ sẽ nằm trong folder đó.
3. Giảm zoom trình duyệt xuống 80 tới 90% để vùng làm việc rộng hơn.
4. Bộ icon trong draw.io không đầy đủ, nên tải bộ AWS Architecture Icons cho PowerPoint tại `https://aws.amazon.com/vi/architecture/icons/`, giải nén và mở file pptx. PowerPoint mở ở chế độ Protected View, bấm Enable Editing nếu cần chỉnh. Mỗi slide có hàng Service Icon cho mức dịch vụ và hàng Resource Icon cho mức tài nguyên hoặc tính năng; dùng ô Search của PowerPoint để tìm rồi lưu icon cần dùng ra file ảnh.
5. Xóa sạch diagram mẫu trước khi bắt đầu vẽ: quét khối, chọn rồi nhấn Delete.

**2. Các nguyên tắc khi vẽ**


**Mức độ chi tiết**

- Nguyên tắc: trước khi vẽ phải định hình quy mô kiến trúc để chọn khung ngoài phù hợp. Vẽ nhiều mức: mức 2 tầng trước, sau đó mới vẽ thêm mức chi tiết. Không nhồi nhét quá nhiều thông tin vào một sơ đồ.
- Lý do: nhồi mọi thứ vào một hình là "tự làm khó mình", hình rối và khó đọc.
- Cách làm: CIDR, route table để ở sơ đồ kiến trúc mạng riêng; có sơ đồ tổng quan riêng và sơ đồ container riêng; sơ đồ tổng quan chỉ nên dừng ở mức ECS chẳng hạn. Trong draw.io, mỗi mức đặt ở một trang riêng, ví dụ Page-1, Page-2, Page-3.

**Khung ngoài theo tỉ lệ vàng**

- Nguyên tắc: khung AWS Cloud vẽ hình chữ nhật nằm ngang theo tỉ lệ vàng 1.618 nhiều nhất có thể.
- Lý do: dễ đưa vào slide hoặc tài liệu Word.
- Cách làm: chiều rộng bằng chiều cao nhân 1.618, ví dụ cao 500 thì rộng khoảng 809, cao 700 thì rộng khoảng 1132. Click vào khung, đặt kích thước ở tab Arrange, mục Size.
- Lỗi hay gặp: hết chỗ rồi kéo giãn tùy ý làm khung lệch tỉ lệ. Khi hết chỗ thì kéo giãn khung rồi tính lại theo tỉ lệ vàng. Trong video, khung cuối cùng ở mức 1200 x 760 sau vài lần mở rộng.

**Phân lớp đường bao Region, VPC, AZ, subnet**

- Nguyên tắc: các group lồng nhau theo thứ tự AWS Cloud, Region, VPC, Availability Zone, subnet; mỗi lớp nhỏ hơn lớp ngoài và canh cho cân đối.
- Cách làm: kéo các group từ nhóm AWS / Groups ở panel trái ra canvas, theo đúng thứ tự từ ngoài vào trong.
- Availability Zone là khái niệm vật lý nên không nằm trọn trong VPC mà lố ra một chút: vẽ ngang thì lố hai bên, vẽ dọc thì lố lên trên. Vẽ xong một AZ rồi copy ra AZ còn lại để đảm bảo đều nhau.
- Mỗi AZ có một cặp public subnet và private subnet, canh đối xứng nhất có thể.

**Vùng dịch vụ dùng chung**

- Nguyên tắc: chừa một vùng trống dưới VPC cho các dịch vụ dùng chung không nằm trong VPC.
- Cách làm: kéo Generic group vào vùng đó, đặt tên Share Services, rồi ở tab Text chuyển Position của nhãn sang bên trái. Ví dụ trong video đặt IAM và Certificate Manager ở đây.

**Vị trí các thành phần**

- Người dùng và Internet đặt bên ngoài khung AWS Cloud.
- Public load balancer đặt ngang tầm public subnet hoặc nhích lên một chút, nhưng phải gắn với public subnet vì có public subnet thì ALB mới hoạt động.
- Trong ví dụ của video: hai EC2 Web/App nằm trong hai public subnet; Primary DB nằm trong private subnet của một AZ, Standby DB nằm trong private subnet của AZ còn lại. Nếu subnet không chứa vừa icon thì mở rộng subnet.

**Hướng luồng dữ liệu và đường nối**

- Nguyên tắc: dùng mũi tên thể hiện luồng đi của yêu cầu.
- Cách làm: ví dụ từ ALB vẽ mũi tên chia tải sang hai EC2 Web/App, từ Web/App vẽ sang Primary DB; vẽ xong thì canh chỉnh lại mũi tên.
- Lỗi hay gặp: mũi tên chạy đè lên chữ của nhãn, cách xử lý xem phần nhãn bên dưới.


**Kích thước icon**

- Nguyên tắc: mọi icon đưa về size 60.
- Lý do: khi có kho hình vẽ tập trung và ai cũng theo một nguyên tắc thì dễ tìm, dễ chia sẻ và dễ sửa hình của nhau. Icon mặc định khi kéo ra thường quá to so với nhu cầu.
- Cách làm: click icon, vào tab Arrange, đặt Size bằng 60.

**Nhãn của thành phần**

- Nguyên tắc: nhãn phải có nền trắng và không có khoảng trắng thừa.
- Lý do: không có nền thì chữ bị mũi tên hoặc đường bao của group che mất; khoảng trắng thừa làm chữ rối.
- Cách làm: chọn nhãn, vào tab Text, đặt Background Color màu trắng; cắt bỏ khoảng trắng đầu và đuôi của tên.

**Màu sắc**

- Nguyên tắc: viền nhãn phân biệt theo loại.
    - Dịch vụ như EC2, RDS, IAM, Kinesis dùng Border Color cam `FF8000`.
    - Tính năng con dùng Border Color xanh dương `0000FF`, ví dụ Application Load Balancer là tính năng của Elastic Load Balancing.
- Cách làm: chọn nhãn, đặt Border Color ở tab Text.


**Icon đúng thế hệ và đúng nguồn**

- Nguyên tắc: không trộn icon đời cũ với icon đời mới trong cùng một hình.
- Cách làm: search "ec2" trong draw.io ra icon đời cũ, phải lấy EC2 từ nhóm AWS / Compute. Icon thiếu thì lấy từ file PowerPoint của AWS.
- Lỗi hay gặp: copy hình kiến trúc trên mạng rồi ghép vào bản đề xuất. Mỗi nơi một kiểu icon, hình sẽ chắp vá, không theo phong cách cố định và khách hàng nhìn vào rất khó chịu.

**Canh lề và khoảng cách**

- Nguyên tắc: các lớp group và các AZ phải cân đối, đối xứng.
- Cách làm: canh tay khi kéo, khi kéo thành phần draw.io cũng tự gợi ý căn chỉnh; vẽ một AZ rồi copy để hai bên đều nhau; dùng tab Arrange để đặt kích thước chính xác.


**Tính nhất quán khi làm nhóm**

- Nguyên tắc: khi làm việc theo nhóm phải thống nhất cách vẽ, cách định dạng và có một kho chung để ai cũng vào xem và sửa được.
- Cách làm: lưu thành phần đã định dạng vào Library, nộp sơ đồ dạng XML vào kho chung.

**3. Quy trình dựng sơ đồ từng bước**

1. Xác định yêu cầu: sơ đồ để làm gì, ở mức tổng quan hay chi tiết, quy mô lớn tới đâu. Ví dụ trong video là ứng dụng web 2 tầng: người dùng ngoài Internet vào ALB, chia tải cho 2 EC2 Web/App, kết nối tới cơ sở dữ liệu Primary và Standby, kèm IAM và Certificate Manager dùng chung. 
2. Chọn thành phần và tìm icon:
        - Group: AWS / Groups.
        - Application Load Balancer: AWS / Network & Content Delivery.
        - EC2: AWS / Compute.
        - RDS: search "rds" trên panel.
        - IAM: AWS / Security, Identity & Compliance.
        - Certificate Manager: search ra ngay.
        - User: search "user"; Internet chọn icon đám mây.
3. Dựng bố cục: kéo khung AWS Cloud, đặt kích thước theo tỉ lệ vàng; lồng Region, VPC, 2 AZ, mỗi AZ một cặp public và private subnet; chừa vùng Share Services dưới VPC. Đến đây nên tự kiểm tra: đủ AWS Cloud, Region, VPC, 2 AZ, 2 public subnet, 2 private subnet, khung đúng tỉ lệ.
4. Đặt thành phần: User và Internet ngoài khung; ALB ngang tầm public subnet; EC2 vào public subnet; DB vào private subnet; IAM, Certificate Manager vào Share Services. Mỗi icon đưa về size 60.
5. Kết nối: vẽ mũi tên ALB sang hai EC2, Web/App sang Primary DB, rồi canh lại mũi tên.
6. Ghi nhãn: đặt tên từng thành phần, nền trắng, viền cam hoặc xanh theo loại, cắt khoảng trắng thừa. Với sơ đồ chi tiết thì thêm CIDR và tên VPC.
7. Kiểm tra lần cuối theo checklist ở mục 7.

**4. Xử lý giới hạn của công cụ**

- Ô search shape rất kém, gõ ALB, ELB, IAM thường không ra; phải mở thủ công từng nhóm như đã liệt kê ở bước 2.
- Khi group lớn đè lên làm không click được object bên dưới: chọn object đang đè rồi nhấn Cmd hoặc Ctrl + Shift + B để Send to Back; mỗi lần nhấn lùi một layer, nhấn vài lần cho lùi hết.
- Thao tác khi chưa chọn object nào sẽ báo lỗi "Nothing is selected".
- Icon thêm từ file ảnh luôn rất to vì là icon gốc để đảm bảo chất lượng, phải chỉnh lại size 60 và định dạng như các icon khác.

**5. Library để tái sử dụng**

1. Tạo bằng File > New Library > Google Drive, đặt tên ví dụ My-AWS.
2. Mở bằng File > Open Library, chọn My-AWS rồi Select. Library hiện thành một mục riêng ở panel trái và file `My-AWS.xml` nằm trong Google Drive.
3. Chỉ kéo vào Library những thành phần đã định dạng xong; có thể quét khối kéo cả một cụm như VPC, subnet, Web/App, DB, muốn lưu ở mức nào thì quét khối ở mức đó.
4. Icon thiếu thì bấm dấu cộng hoặc bút chì trên Library, thêm image, kéo file ảnh đã lưu từ PowerPoint vào; sau đó kéo icon ra, chỉnh size 60, đặt tên, viền theo quy ước, kéo bản đã định dạng vào Library, xóa bản chưa định dạng rồi lưu.
5. Khi Library đủ nhiều thì không cần lục hàng trăm icon nữa; với khách hàng mới chỉ cần kéo kiến trúc cơ bản ra rồi sửa, thêm CIDR và tên VPC nếu làm sơ đồ chi tiết.

**6. Xuất file và nộp bài**

1. Xuất ảnh bằng File > Export as > PNG; bật Transparent Background thì chỉ giữ đúng các thành phần, tắt thì có nền trắng. Có thể xuất PDF; xuất Visio được nhưng không đẹp.
2. Nộp bài và chia sẻ bằng File > Export as > XML, chọn All Pages, đặt tên rồi Download ra file `.xml`.
3. Kiểm tra bằng File > Import from > Device, mở file `.xml`; sơ đồ phải hiện lại đủ các trang như bản gốc.
4. Bài tập của video: chọn một kiến trúc AWS bất kỳ trên mạng, vẽ lại đúng bộ quy ước này rồi nộp file XML để góp vào kho kiến trúc chung.

**7. Checklist kiểm tra sơ đồ cuối cùng**

- [ ] Sơ đồ đúng một mức chi tiết, không nhồi CIDR hay route table vào sơ đồ tổng quan.
- [ ] Khung AWS Cloud nằm ngang, gần tỉ lệ 1.618.
- [ ] Group lồng đúng thứ tự AWS Cloud, Region, VPC, AZ, subnet; AZ lố ra khỏi VPC; hai AZ đều nhau.
- [ ] Mỗi AZ có cặp public và private subnet đối xứng.
- [ ] Người dùng và Internet nằm ngoài AWS Cloud; dịch vụ dùng chung nằm trong Share Services.
- [ ] ALB gắn với public subnet.
- [ ] Mũi tên thể hiện đủ luồng và đã canh gọn.
- [ ] Mọi icon size 60, cùng một thế hệ icon.
- [ ] Mọi nhãn nền trắng, không khoảng trắng thừa, viền cam `FF8000` cho dịch vụ, xanh `0000FF` cho tính năng.
- [ ] Đã xuất XML với All Pages và import lại thấy đủ trang.

**Gợi ý từ Prologue của chương trình**

- Hai tiêu chí đánh giá project: tính đúng đắn, tức là thực thi được; và bản thân có thực sự tự hào đem sản phẩm đi khoe, đưa vào profile và CV hay không. Không cần dự án quá lớn, quan trọng là tiến bộ và liên tục cải tiến.
- Cách tìm và làm project:
    1. Chọn hướng nghề nghiệp, ví dụ muốn làm data engineer thì làm project xây dựng data platform trên AWS.
    2. Tìm ý tưởng ở AWS Solutions, AWS Reference Architecture, hoặc hỏi AI gợi ý dự án gây ấn tượng với nhà tuyển dụng cho vị trí mình muốn.
    3. Làm cho chạy được, rồi cải tiến dần.
    4. Chia sẻ ở meetup cuối tháng, trang cá nhân, CV.
- Deadline 6 tháng là mục tiêu để không bỏ dở giữa chừng; người học phải tự đặt deadline và kỷ luật vì đội ngũ là tình nguyện viên. Bí thì phải hỏi trên group hoặc WhatsApp sau khi đã tự tìm.
- Checklist trước Module 1 gồm 7 việc:
    - [ ] Tạo AWS account cá nhân.
    - [ ] Tạo AWS Builder Profile.
    - [ ] Tạo tài khoản WhatsApp.
    - [ ] Tạo LinkedIn Profile càng sớm càng tốt.
    - [ ] Tham gia AWS Study Group trên Facebook và LinkedIn.
    - [ ] Theo dõi trang `awsstudygroup.com`.
    - [ ] Theo dõi hai kênh YouTube của Study Group gồm kênh lý thuyết và kênh thực hành.
- Tra bài thực hành theo mã: gõ mã số bài, thêm dấu chấm và `awsstudygroup.com`. Mỗi module có bài bắt buộc; các bài trên trang chính là tùy chọn.

### Tài liệu tham khảo

* <https://www.youtube.com/watch?v=95quNuhvMT0>
* <https://www.youtube.com/watch?v=Gz56QzLQ_Yo>
* <https://www.youtube.com/watch?v=UIw8UxGZCHA>
* <https://www.youtube.com/watch?v=l8isyDe-GwY>
* <https://www.youtube.com/watch?v=mXRqgMr_97U>
* <https://www.youtube.com/watch?v=qVCF7UjYC5s>
* <https://www.youtube.com/watch?v=uAQCm4sm_1c>
* <https://aws.amazon.com/vi/architecture/icons/>
* <https://calculator.aws/#/>
* <https://docs.aws.amazon.com/wellarchitected/>

### Hình ảnh minh chứng:

![Xem video Hướng dẫn vẽ kiến trúc AWS trên draw.io: dựng sơ đồ VPC với public và private subnet ở 2 Availability Zone](/images/1-worklog/1.2-week2/1.2.1-day1/evd-0004.png)

*Xem video Hướng dẫn vẽ kiến trúc AWS trên draw.io: dựng sơ đồ VPC với public và private subnet ở 2 Availability Zone*

![Xem video Hướng dẫn làm workshop AWS: phần cài Hugo và theme Learn](/images/1-worklog/1.2-week2/1.2.1-day1/evd-0005.png)

*Xem video Hướng dẫn làm workshop AWS: phần cài Hugo và theme Learn*

![Xem video Module 01-01 - Introduction to AWS](/images/1-worklog/1.2-week2/1.2.1-day1/evd-0006.png)

*Xem video Module 01-01 - Introduction to AWS*

![Xem video Module 01-02 Management Console: đăng nhập bằng root user hoặc IAM user](/images/1-worklog/1.2-week2/1.2.1-day1/evd-0007.png)

*Xem video Module 01-02 Management Console: đăng nhập bằng root user hoặc IAM user*

![Xem video Module 01-03 Gen AI on AWS - Kiro](/images/1-worklog/1.2-week2/1.2.1-day1/evd-0008.png)

*Xem video Module 01-03 Gen AI on AWS - Kiro*

![Xem video Module 01-04 Cost optimization on AWS: checklist trước khi sang module tiếp theo](/images/1-worklog/1.2-week2/1.2.1-day1/evd-0009.png)

*Xem video Module 01-04 Cost optimization on AWS: checklist trước khi sang module tiếp theo*

![Issue bộ icon AWS bị ẩn trong draw.io](/images/1-worklog/1.2-week2/1.2.1-day1/evd-0010.png)

*Issue bộ icon AWS bị ẩn trong draw.io*
