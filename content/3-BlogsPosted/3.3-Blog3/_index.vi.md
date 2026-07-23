---
title: "Blog 3"
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# AgentCore Harness: Từ ý tưởng đến một AI Agent hoạt động chỉ với hai API

Khi xây dựng một AI Agent, phần khó không chỉ nằm ở việc gọi mô hình ngôn ngữ mà còn ở vòng lặp xử lý, kết nối công cụ, quản lý bộ nhớ, trạng thái phiên, danh tính, khả năng quan sát và môi trường thực thi an toàn.

**Amazon Bedrock AgentCore Harness** đóng gói các thành phần này thành một dịch vụ được quản lý, giúp developer tập trung vào logic nghiệp vụ và khả năng của agent thay vì tự xây dựng toàn bộ phần hạ tầng.

---

## 1. Hai API chính

Một agent có thể được đưa vào hoạt động thông qua hai API:

* **CreateHarness:** Định nghĩa model, system prompt, tools, skills, memory và giới hạn thực thi.
* **InvokeHarness:** Gửi yêu cầu để agent phân tích, lựa chọn công cụ, thực thi và trả kết quả.

Ví dụ, một AWS Support Agent có thể đọc log CloudWatch, tìm tài liệu AWS, phân tích nguyên nhân lỗi, đề xuất cách xử lý và tạo support case khi cần thiết.

---

## 2. Những gì Harness quản lý

Mỗi phiên agent có thể chạy trong môi trường cô lập với filesystem và shell riêng. Harness cũng hỗ trợ kết nối với **AgentCore Gateway**, **MCP server**, **AgentCore Browser**, **Code Interpreter** và **Inline Function**.

Model được tách khỏi logic của agent, vì vậy developer có thể cấu hình model mặc định hoặc lựa chọn model khác cho từng yêu cầu mà không phải thay đổi toàn bộ hệ thống.

---

## 3. Harness và Runtime

* **AgentCore Harness** phù hợp với agent theo quy trình phổ biến: nhận yêu cầu, suy luận, gọi công cụ và trả kết quả. Giải pháp này ưu tiên tốc độ phát triển và sự đơn giản.
* **AgentCore Runtime** phù hợp hơn khi cần framework riêng, workflow đặc biệt, orchestration tùy chỉnh hoặc can thiệp sâu vào quá trình thực thi.

Harness không có nghĩa là xây dựng agent hoàn toàn không cần code. Developer vẫn phải thiết kế prompt, công cụ, dữ liệu, IAM role, quyền truy cập và cơ chế kiểm soát hành động.

---

## Kết luận

Với **CreateHarness** để định nghĩa và **InvokeHarness** để vận hành, AgentCore Harness giúp giảm đáng kể phần “khung xương” phải tự xây dựng cho một AI Agent. Nhờ đó, đội phát triển có thể dành nhiều thời gian hơn cho bài toán thực tế và nhanh chóng đưa agent từ ý tưởng đến môi trường production.

---

## Tham khảo thêm

Đọc bài viết chính thức từ AWS:
[Amazon Bedrock AgentCore harness is now generally available: Go from idea to production-grade agent in minutes](https://aws.amazon.com/blogs/machine-learning/amazon-bedrock-agentcore-harness-is-now-generally-available-go-from-idea-to-production-grade-agent-in-minutes/)

#AWS #AmazonBedrock #AgentCore #AgenticAI #GenerativeAI
