---
title: "Event 1"
date: 2026-05-23
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

## Bài thu hoạch: "AWS Vietnam Community Day 2026 (FCAJ Community Day)"

### Thông Tin Sự Kiện

- **Ngày tổ chức:** 23 tháng 5 năm 2026
- **Thời gian:** 08:30 - 12:00
- **Địa điểm:** Tầng 26, Tòa nhà Bitexco Financial Tower, số 02 đường Hải Triều, phường Sài Gòn, Thành phố Hồ Chí Minh
- **Vai trò:** Người tham dự
- **Nội dung chính:** Generative AI, dịch vụ AWS, kiến trúc đám mây và quy trình phát triển phần mềm

### Mục Đích Tham Gia

Tôi tham gia sự kiện để tìm hiểu cách các diễn giả trong cộng đồng áp dụng AI và dịch vụ AWS vào dự án thực tế. Chương trình kết hợp nhiều góc nhìn về sử dụng AI, phân phối nội dung, bảo mật, phát triển sản phẩm và kiến trúc multi-agent.

### Danh Sách Diễn Giả Và Chủ Đề

- **Trương Anh Tịnh** - *Context Is Everything: Making AI Actually Work for You*
- **Phạm Ngô Hải Anh** - *Friendly AI Assistant with Amazon Quick*
- **Nguyễn Tuấn Thịnh** - *From Edge to Origin: CloudFront as Your Foundation*
- **Team VIB** - *36 hrs with LotusHacks: Building UTMorpho from Idea to Reality*
- **Đào Đức** - *Non-Determinism of "Deterministic" LLM Settings*
- **Lâm Cát Vy** - *Enterprise-Grade Multi-Agent System: The Case of Startup Credit Scoring*

### Nội Dung Các Phiên Chia Sẻ

#### Context Is Everything: Making AI Actually Work for You

Phiên chia sẻ tập trung vào chất lượng ngữ cảnh cung cấp cho mô hình AI. Những lỗi thường gặp gồm đưa vào quá nhiều tài liệu không liên quan, lặp lại thông tin mô hình đã biết và đặt yêu cầu thiếu ràng buộc. Quy trình "Second AI Brain", Store -> Retrieve -> Generate -> Learn, là một cách đơn giản để tổ chức thông tin trước khi sử dụng công cụ AI.

#### Friendly AI Assistant with Amazon Quick

Phần trình bày giới thiệu Amazon Quick trong việc tìm kiếm thông tin và tự động hóa công việc văn phòng lặp lại. Các ví dụ gồm chuẩn bị biên bản họp, soạn email tiếp theo và tổng hợp công việc từ nhiều nguồn dữ liệu. Bài học chính là bắt đầu bằng một tác vụ nhỏ, sau đó kiểm tra kết quả trước khi mở rộng quy trình tự động hóa.

#### From Edge to Origin: CloudFront as Your Foundation

Phiên CloudFront đề cập đến caching, nén dữ liệu, HTTP/3, chuyển đổi origin khi có sự cố và xử lý tại edge bằng CloudFront Functions hoặc Lambda@Edge. CloudFront có thể kết hợp với AWS WAF và AWS Shield trong kiến trúc bảo mật nhiều lớp. Cơ chế bảo vệ origin phụ thuộc vào từng loại tài nguyên: Origin Access Control được dùng với Amazon S3, còn VPC origins có thể giúp một số load balancer hoặc EC2 origin không phải mở truy cập trực tiếp từ Internet.

#### 36 hrs with LotusHacks: Building UTMorpho from Idea to Reality

Team VIB chia sẻ quá trình xây dựng UTMorpho trong 36 giờ tại LotusHacks. Nhóm phải chọn ý tưởng, làm việc trong giới hạn API, loại bỏ đầu ra AI không sử dụng được và hoàn thiện sản phẩm cho phần thuyết trình cuối. Trải nghiệm này cho thấy việc đồng bộ nhóm thường xuyên và thống nhất bài toán quan trọng hơn thêm nhiều tính năng thiếu liên kết khi thời gian có hạn.

#### Non-Determinism of "Deterministic" LLM Settings

Phiên trình bày giải thích vì sao thiết lập temperature bằng 0 vẫn không luôn tạo ra kết quả giống hệt nhau giữa các lần gọi. Phép tính số thực trên phần cứng song song và cách nhà cung cấp gom nhiều yêu cầu xử lý có thể tạo ra khác biệt nhỏ trong quá trình suy luận. Các cách kiểm soát được đề cập gồm sử dụng đầu ra có cấu trúc, đánh giá nhiều lần và viết kiểm thử dựa trên hành vi cần thiết thay vì so sánh nguyên văn từng câu.

#### Enterprise-Grade Multi-Agent System: The Case of Startup Credit Scoring

Phiên cuối sử dụng bài toán chấm điểm tín dụng cho startup để minh họa kiến trúc multi-agent. Các agent chuyên trách phân tích tài chính, thị trường, đội ngũ, rủi ro và tuân thủ, sau đó agent quản lý tổng hợp kết quả. Hướng triển khai được đề xuất gồm CrewAI, Amazon Bedrock AgentCore, Docker, Amazon ECR và API Gateway. Khi đánh giá kiến trúc này, cần xem xét đồng thời bảo mật, quản trị dữ liệu, vận hành, kiểm tra của con người và yêu cầu tuân thủ.

### Những Bài Học Chính

- Ngữ cảnh tốt cần thông tin liên quan, ràng buộc rõ ràng và định dạng đầu ra mong muốn.
- Tự động hóa bằng AI nên bắt đầu từ tác vụ giới hạn và có thể kiểm tra kết quả.
- CloudFront hỗ trợ hiệu năng phân phối nội dung, nhưng bảo mật vẫn phụ thuộc vào cách kết hợp các dịch vụ AWS và cấu hình quyền truy cập origin.
- Hệ thống sử dụng LLM nên kiểm tra hành vi và cấu trúc đầu ra thay vì giả định nội dung văn bản luôn giống nhau.
- Kiến trúc multi-agent chỉ phù hợp khi việc tách trách nhiệm và phối hợp mang lại lợi ích rõ ràng so với giải pháp đơn giản hơn.

### Hướng Áp Dụng

- Xác định mục tiêu, ngữ cảnh, ràng buộc và tiêu chí thành công trước khi sử dụng trợ lý AI.
- Sử dụng đầu ra có cấu trúc khi ứng dụng cần xử lý phản hồi từ LLM bằng chương trình.
- Kiểm tra riêng cấu hình cache và quyền truy cập origin của CloudFront thay vì xem CDN là toàn bộ giải pháp bảo mật.
- Bắt đầu thử nghiệm AI hoặc tự động hóa bằng một trường hợp sử dụng nhỏ, chỉ tăng độ phức tạp sau khi có thể đo lường kết quả.

### Cảm Nhận Sau Sự Kiện

Sự kiện giúp tôi thấy rõ hơn mối liên hệ giữa phát triển ứng dụng AI, phân phối nội dung trên cloud và yêu cầu vận hành hệ thống. Hai chủ đề tôi muốn tìm hiểu thêm là cách thiết kế ngữ cảnh cho công việc có AI hỗ trợ và phương pháp kiểm thử những hệ thống có đầu ra mô hình thay đổi giữa các lần chạy.
