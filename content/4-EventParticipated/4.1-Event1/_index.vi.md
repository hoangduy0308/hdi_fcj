---
title: "Event 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Bài thu hoạch "AWS Vietnam Community Day 2026 (FCAJ Community Day)"

### Mục Đích Của Sự Kiện

- Gắn kết cộng đồng FCAJ và chia sẻ các trải nghiệm thực tế về trí tuệ nhân tạo (Generative AI) và điện toán đám mây (Cloud) cho các thành viên First Cloud AI Journey.
- Tìm hiểu sâu về kỹ nghệ ngữ cảnh (Context Engineering) để sử dụng hiệu quả các công cụ AI trong học tập và công việc hàng ngày.
- Cập nhật các dịch vụ AWS mới như Amazon Quick Suite và các tính năng tối ưu chi phí, bảo mật của Amazon CloudFront.
- Phân tích nguyên nhân sâu xa của tính chất phi định tính (non-determinism) trong LLM và thiết kế hệ thống multi-agent chạy ổn định ở môi trường production.

### Danh Sách Diễn Giả

- **Trương Anh Tịnh** - Platform Engineer, GoTyme Bank
- **Phạm Ngô Hải Anh** - AWS Community Builder, G-AsiaPacific Vietnam
- **Nguyễn Tuấn Thịnh** - DevOps Engineer, First Cloud AI Journey
- **Team VIB** - Lập trình viên/Hackathon Winners
- **Đào Đức** - Solution Architect, Cloud Kinetics
- **Lâm Cát Vy** - Senior Business Systems Analyst, VPBank

### Nội Dung Nổi Bật

#### Context Is Everything: Making AI Actually Work for You

- Khẳng định mô hình AI đã rất mạnh, rào cản lớn nhất nằm ở cách người dùng cung cấp ngữ cảnh (context).
- Ba sai lầm phổ biến khi dùng AI: nhồi nhét tài liệu thô (gây loãng tín hiệu và tốn token), lặp lại những điều hiển nhiên, và viết prompt chung chung không ràng buộc.
- Mô hình "Second AI Brain" (Bộ não thứ hai): Lưu trữ (Store) -> Truy xuất (Retrieve) -> Sinh nội dung (Generate) -> Học tập (Learn).
- Định hướng cho thành viên tự xây dựng các dự án AI nhỏ hữu ích: Trợ lý học tập, Chat với PDF, Trợ lý duyệt code.

#### Friendly AI Assistant with Amazon Quick

- Giải quyết các khó khăn thực tế của nhân viên văn phòng: mất nhiều thời gian tổng hợp thông tin từ nhiều nguồn và làm các tác vụ lặp đi lặp lại.
- Giới thiệu Amazon Quick Suite giúp phân tích dữ liệu bằng ngôn ngữ tự nhiên: Quick Chat (phân tích sâu), Quick Flows (tạo workflow tự động hóa), Quick Spaces (chia sẻ tri thức nhóm), Quick Sight (dựng dashboard bằng lời nói).
- Demo thực tế: Tự động viết biên bản họp (MoM), gửi email cho các bên liên quan và tự lên lịch họp mà không cần code.

#### From Edge to Origin: CloudFront as Your Foundation

- Giải quyết bài toán bảo mật và chi phí cho các doanh nghiệp nhỏ/startup: tránh hóa đơn AWS tăng vọt do dính tấn công DDoS hoặc traffic tăng đột biến.
- Tối ưu hóa chi phí với chính sách miễn phí truyền dữ liệu từ các AWS origins đến CloudFront, gói fixed-price ổn định hàng tháng.
- Các tính năng bảo mật tích hợp: AWS WAF, Shield, Mutual TLS (mTLS), origin cloaking (ẩn IP của ALB/S3 thông qua VPC Origin/OAC).
- Cải thiện hiệu năng và độ tin cậy: multi-layer caching, HTTP/3 (QUIC/UDP), nén HTTP, origin failover tự động và edge logic (CloudFront Functions, Lambda@Edge).

#### 36 hrs with LotusHacks – Building UTMorpho from Idea to Reality

- Chia sẻ thực tế từ 36 giờ code liên tục tại Hackathon lớn nhất Việt Nam.
- Những thách thức thực tế khi phát triển sản phẩm UTMorpho: cạn ý tưởng ở giờ đầu tiên, AI sinh quá nhiều output rác, cạn kiệt token API, và áp lực kiệt sức sát giờ thuyết trình.
- Bài học từ trải nghiệm: sự khó chịu từ khó khăn thực tế giúp tạo ra ý tưởng tốt nhất; làm việc nhóm và đồng bộ hóa quan trọng hơn năng lực cá nhân; hackathon là bài kiểm tra sức bền khi đối mặt với thất bại.

#### Non-Determinism of "Deterministic" LLM Settings

- Bác bỏ giả thuyết Temperature = 0 giúp đảm bảo đầu ra giống hệt nhau (deterministic).
- Nguyên nhân gốc rễ: phép tính số thực dấu phẩy động trên GPU song song không có tính kết hợp, và API providers gộp chung các yêu cầu (inference batching) làm thay đổi tính toán.
- Các phương pháp giảm thiểu: chạy prompt nhiều lần kết hợp bỏ phiếu đa số (majority voting), sử dụng đầu ra có cấu trúc (JSON mode, function calling), sử dụng `temperature = 0.1` để tránh bị lặp từ (greedy decoding loop).

#### Enterprise-Grade Multi-Agent System: The Case of Startup Credit Scoring

- Phân tích rào cản của startup khi tiếp cận nguồn vốn ngân hàng (thiếu lịch sử tín dụng 3 năm, thiếu tài sản thế chấp).
- Mô hình Multi-Agent (Hội đồng tín dụng ảo) giải quyết vấn đề: các agent chuyên môn hóa (Financial Analyst, Market Analyst, Team Evaluator, Risk Assessor, Compliance) phối hợp dưới sự điều phối của Manager để đưa ra quyết định toàn diện.
- Hiệu quả thực tế sau áp dụng: Xử lý nhanh hơn 95% (từ 2-3 tuần xuống 2-4 giờ), giảm 95% chi phí duyệt hồ sơ, tăng gấp đôi tỷ lệ phê duyệt đúng.
- Kiến trúc triển khai thực tế trên AWS: CrewAI -> Bedrock AgentCore -> Docker -> ECR -> API Gateway, đi kèm 6 trụ cột Enterprise (security, data, network, operations, human, compliance) ngay từ ngày đầu.

### Những Gì Học Được

#### Tư Duy Làm Việc Với AI

- Context engineering quan trọng hơn viết prompt hay. Cho AI ăn đúng lượng dữ liệu chất lượng thay vì nhồi nhét tài liệu thô.
- Đầu ra của LLM luôn mang tính xác suất kể cả khi cài đặt temperature = 0. Phải thiết kế hệ thống chấp nhận sai số và variance.

#### Kiến Trúc Kỹ Thuật

- CloudFront không đơn thuần là CDN tăng tốc web, nó là lớp bảo mật đầu tiên, giúp ẩn origin và tối ưu hóa chi phí vận hành hạ tầng nếu cấu hình đúng.
- Sử dụng hệ thống multi-agent phối hợp và kiểm tra chéo giúp tăng độ chính xác và tính giải thích được cho các bài toán nghiệp vụ phức tạp.

#### Thiết Kế Sản Phẩm & Định Hướng Nghề Nghiệp

- Ý tưởng sản phẩm tốt nhất thường đến từ sự khó chịu và khó khăn trong công việc thực tế, không phải từ các buổi brainstorm lý thuyết suông.
- Bắt đầu nhỏ bằng cách xây dựng những công cụ phục vụ chính nhu cầu của mình (PDF chat, trợ lý học tập) trước khi nghĩ đến hệ thống lớn.

### Ứng Dụng Vào Công Việc

- Chuẩn bị sẵn Khung Ngữ Cảnh (Goal, Context, Constraints, Success Criteria) trước khi mở chatbot AI để tiết kiệm thời gian phản hồi.
- Thử nghiệm Amazon Quick Sight để tự động hóa việc xây dựng các báo cáo công việc từ dữ liệu thô bằng ngôn ngữ tự nhiên.
- Rà soát lại cấu hình CloudFront của dự án hiện tại, kích hoạt nén tự động và bảo mật origin bằng OAC.
- Thiết kế lại các test case cho các chức năng dùng LLM, chấp nhận variance và chuyển sang sử dụng structured output / JSON mode.

### Trải nghiệm trong event

Tham gia sự kiện AWS Vietnam Community Day 2026 (FCAJ Community Day) là một trải nghiệm rất bổ ích, giúp tôi có cái nhìn toàn diện về cách hiện thực hóa các ứng dụng AI và xây dựng nền tảng đám mây an toàn, tối ưu chi phí. Một số trải nghiệm nổi bật:

#### Học hỏi từ các diễn giả có chuyên môn cao
- Được lắng nghe những phân tích sâu sắc từ các diễn giả giàu kinh nghiệm thực chiến từ GoTyme Bank, VPBank, Cloud Kinetics. Mọi người chia sẻ thật về những khó khăn, lỗi hệ thống gặp phải khi vận hành thực tế chứ không chỉ giới thiệu sản phẩm.
- Hiểu được rằng để đưa giải pháp công nghệ từ local lên môi trường sản xuất thực tế (production) đòi hỏi phải có quy trình nghiêm ngặt và giải quyết các bài toán rủi ro lớn hơn rất nhiều.

#### Trải nghiệm kỹ thuật thực tế
- Các phần trình bày kỹ thuật đi thẳng vào cấu hình cụ thể: cách cấu hình mTLS, cách thiết lập VPC Origin để ẩn hoàn toàn origin backend khỏi internet công cộng, hay cách xử lý lỗi không đồng nhất (non-determinism) của LLM ở mức phần cứng GPU.
- Có cái nhìn trực quan hơn về việc đánh giá hiệu năng và so sánh tài nguyên hệ thống (như việc giảm tải CPU của EC2 từ 5% xuống 1% nhờ cấu hình cache tối ưu).

#### Ứng dụng công cụ hiện đại
- Tìm hiểu và quan sát demo trực tiếp của Amazon Quick Suite và Amazon Bedrock AgentCore. Những công cụ này cho thấy xu hướng phát triển ứng dụng GenAI sắp tới là chuyển dịch từ các chatbot đơn lẻ sang các hệ thống agentic tự động hóa workflow hoàn chỉnh.
- Học hỏi các phương pháp kiểm soát đầu ra của mô hình như majority voting hay structured output nhằm khắc phục các hạn chế kỹ thuật hiện tại của GenAI.

#### Kết nối và trao đổi
- Sự kiện quy tụ khoảng 400 người tham gia, phần lớn là các thành viên First Cloud AI Journey và cộng đồng AWS FCAJ. Không khí trao đổi rất cởi mở, từ việc hỏi kinh nghiệm xin việc của các anh chị lớn đến các câu hỏi chi tiết về thuật toán RAG.
- Nhận ra sự năng động của cộng đồng AWS trẻ tuổi, nơi các bạn sinh viên và kỹ sư mới vào nghề chủ động chia sẻ, tìm kiếm giải pháp thực chiến hơn là các thảo luận mang tính thương mại.

#### Bài học rút ra
- Kỹ năng làm việc với AI (AI Collaboration) sẽ sớm trở thành ranh giới phân định năng lực của các kỹ sư lập trình. Do đó, việc xây dựng tư duy đúng về ngữ cảnh và kiểm soát rủi ro của AI là cực kỳ quan trọng đối với các thành viên khi mới bắt đầu hành trình Cloud.
- Đồng bộ team và tìm kiếm giải pháp thực tế quan trọng hơn việc tích lũy các ý tưởng hay công nghệ rời rạc nhưng thiếu sự liên kết thực tiễn.

#### Một số hình ảnh khi tham gia sự kiện
* Thêm các hình ảnh của các bạn tại đây
> Tổng thể, sự kiện không chỉ cung cấp kiến thức kỹ thuật hữu ích mà còn thay đổi tư duy của tôi về thiết kế hệ thống, giúp tôi hiểu rõ hơn cách tích hợp AI một cách bảo mật, tối ưu và hiệu quả trong các dự án thực tế.
