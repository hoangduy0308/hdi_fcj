---
title: "Event 2"
date: 2026-06-06
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

## Bài thu hoạch: "Technical Meetup - Ngày 06 tháng 06 năm 2026"

### Thông Tin Sự Kiện

- **Thời gian:** Ngày 06 tháng 06 năm 2026
- **Vai trò:** Người tham dự
- **Hình thức:** Meetup chia sẻ kiến thức kỹ thuật

### Mục Đích Tham Gia

Tôi tham gia meetup để tìm hiểu cách các kỹ sư áp dụng dịch vụ đám mây và quy trình phát triển phần mềm vào những bài toán cụ thể. Sáu chủ đề trải rộng từ hạ tầng, bảo mật, ứng dụng thời gian thực đến AI, làm việc nhóm và phát triển nghề nghiệp, qua đó giúp tôi thấy rõ hơn mối liên hệ giữa các lĩnh vực này.

### Danh Sách Diễn Giả Và Chủ Đề

- **Bảo Huỳnh** - *Docker: A Containerization Technology*
- **Lê Hoàng Gia Đại** - *Combining AWS WAF with Machine Learning for Cyber Attack Detection on AWS*
- **Nguyễn Quốc Bảo** - *Multiplayer in the Cloud: Connecting Godot Clients with AWS WebSockets*
- **Trương Huy Phước** - *The Art of Effective Teamwork*
- **Việt Phát** - *GraphRAG: Build GraphRAG Applications Using Amazon Bedrock and Amazon Neptune*
- **Trần Trung Vinh** - *From IT Helpdesk to Senior Sysadmin*

### Nội Dung Các Phiên Chia Sẻ

#### Docker: A Containerization Technology

Bảo Huỳnh so sánh máy ảo với container và giải thích rằng container dùng chung hệ điều hành của máy chủ thay vì chạy một hệ điều hành khách hoàn chỉnh. Phiên chia sẻ giới thiệu Docker image, container, Dockerfile, image layer và các trường hợp sử dụng trong CI/CD, microservices, kiểm thử, ứng dụng cloud-native và hiện đại hóa hệ thống cũ. Giá trị thực tế của Docker nằm ở khả năng đóng gói ứng dụng một lần và chạy nhất quán trên nhiều môi trường.

#### Kết Hợp AWS WAF Và Machine Learning Để Phát Hiện Tấn Công

Lê Hoàng Gia Đại trình bày AWS WAF như lớp bảo vệ đầu tiên trước SQL injection, cross-site scripting, bot traffic và brute-force. Cơ chế dựa trên luật xử lý tốt các mẫu tấn công đã biết nhưng còn hạn chế trước zero-day attack, hybrid attack và hành vi bất thường.

Giải pháp Network Intrusion Detection System được dùng để bổ sung khả năng phát hiện theo hành vi, không thay thế AWS WAF. Nội dung gồm bộ dữ liệu CSE-CIC-IDS2018, quá trình làm sạch và cân bằng dữ liệu, mô hình LightGBM, cùng kiến trúc thu thập và xử lý dữ liệu bảo mật bằng Amazon S3, Kinesis Data Firehose, AWS Lambda và Amazon CloudWatch.

#### Multiplayer Trên Cloud Với Godot Và AWS WebSockets

Nguyễn Quốc Bảo demo trò chơi Oẳn-Tù-Tì theo lượt sử dụng Godot, Amazon API Gateway WebSocket APIs, AWS Lambda và Amazon DynamoDB. Các route `$connect`, `$disconnect` và route ứng dụng đảm nhiệm việc quản lý kết nối, ghép trận, lựa chọn của người chơi và trả kết quả.

Phiên chia sẻ cũng chỉ ra giới hạn của kiến trúc serverless này. Kết nối hết hạn, thao tác quét bảng và việc Lambda không lưu trạng thái cần được xử lý cẩn thận. Với game yêu cầu cập nhật liên tục ở tần suất cao, AWS GameLift có thể là lựa chọn phù hợp hơn.

#### The Art of Effective Teamwork

Trương Huy Phước tập trung vào những yếu tố cơ bản nhưng dễ bị bỏ qua: thống nhất mục tiêu chung, phân công đúng vai trò, giao tiếp cởi mở, lắng nghe và chịu trách nhiệm với phần việc của mình. Trello, ClickUp, Google Workspace, Slack và Discord có thể hỗ trợ phối hợp, nhưng công cụ không thể thay thế trách nhiệm rõ ràng và việc trao đổi thường xuyên.

#### GraphRAG Với Amazon Bedrock Và Amazon Neptune

Việt Phát giải thích vì sao Retrieval-Augmented Generation truyền thống có thể gặp khó khăn với câu hỏi cần lần theo quan hệ giữa nhiều đối tượng hoặc tài liệu. GraphRAG biểu diễn các quan hệ bằng đỉnh và cạnh trong đồ thị, nhờ đó quá trình truy xuất không chỉ phụ thuộc vào độ tương đồng ngữ nghĩa.

Hai hướng triển khai được giới thiệu. Hướng sử dụng dịch vụ được quản lý kết hợp Amazon Bedrock Knowledge Bases và Amazon Neptune Analytics để xử lý dữ liệu và xây dựng đồ thị. Hướng tùy chỉnh sử dụng LlamaIndex để tạo đồ thị tri thức, sau đó lưu trữ và truy vấn nhiều bước trên Amazon Neptune bằng Cypher.

#### From IT Helpdesk to Senior Sysadmin

Trần Trung Vinh chia sẻ lộ trình từ IT Helpdesk lên System Administrator, sau đó phát triển theo hướng Cloud và DevOps. Kỹ năng xử lý sự cố, giao tiếp, Linux, mạng máy tính và thực hành trong phòng lab là nền tảng ban đầu. Các bước tiếp theo gồm tự động hóa, viết runbook, giám sát hệ thống, Infrastructure as Code, CI/CD, quản lý phiên bản và kiểm thử an toàn. Phiên chia sẻ cũng nhấn mạnh giá trị của dự án thực tế và portfolio trong việc chứng minh năng lực.

### Những Bài Học Chính

- Container giúp giải quyết sự khác biệt giữa các môi trường, nhưng người sử dụng vẫn cần hiểu hạ tầng bên dưới.
- AWS WAF và hệ thống phát hiện bằng Machine Learning đảm nhiệm những vai trò khác nhau và nên được kết hợp thành nhiều lớp bảo vệ.
- API Gateway WebSocket APIs, Lambda và DynamoDB phù hợp với tính năng thời gian thực nhẹ hoặc xử lý theo lượt, không phù hợp với mọi loại game multiplayer.
- GraphRAG đáng cân nhắc khi câu hỏi phụ thuộc vào quan hệ rõ ràng và quá trình suy luận nhiều bước.
- Bên cạnh kỹ thuật, tài liệu, giao tiếp, trách nhiệm cá nhân và thói quen vận hành an toàn cũng ảnh hưởng trực tiếp đến độ tin cậy của hệ thống.

### Hướng Áp Dụng

- Sử dụng Docker để tạo môi trường phát triển và kiểm thử có thể tái lập cho các thành phần nhỏ của dự án.
- Kết hợp biện pháp phòng ngừa với logging, monitoring và phát hiện hành vi khi thiết kế giải pháp bảo mật.
- Thử nghiệm một tính năng WebSocket nhỏ bằng API Gateway, Lambda và DynamoDB trước khi xây dựng kiến trúc thời gian thực lớn hơn.
- Chỉ đánh giá GraphRAG khi dữ liệu và câu hỏi thực sự cần truy xuất dựa trên quan hệ.
- Thống nhất mục tiêu, trách nhiệm và một quy trình theo dõi công việc trước khi nhóm bắt đầu triển khai.

### Cảm Nhận Sau Sự Kiện

Meetup cho tôi thấy lựa chọn công nghệ chỉ là một phần của công việc kỹ thuật. Một giải pháp còn cần cơ chế bảo mật, quy trình vận hành và cách phối hợp phù hợp. Sau sự kiện, các nội dung tôi muốn tìm hiểu thêm là Docker, WebSocket APIs, giám sát hệ thống, Infrastructure as Code và điều kiện để GraphRAG mang lại lợi ích rõ ràng hơn RAG truyền thống.
