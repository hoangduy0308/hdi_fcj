---
title: "Blog 2"
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

# Các cách kiểm soát quyền truy cập ứng dụng Web trên AWS với Amazon Cognito

Trong quá trình tích hợp xác thực cho dự án thực tập TrustBite, mình nhận ra rằng đăng nhập chỉ giải quyết một phần của bài toán bảo mật. Hệ thống còn phải bảo đảm các request chưa được xác thực không thể truy cập trang quản trị, API hoặc dịch vụ backend được bảo vệ.

Amazon Cognito cung cấp kho người dùng được quản lý và hỗ trợ OAuth 2.0 cùng OpenID Connect. Tùy vị trí thực hiện kiểm tra xác thực, Cognito có thể kết hợp với Application Load Balancer, Amazon API Gateway hoặc Amazon CloudFront và AWS Lambda. Mỗi mô hình phù hợp với một kiểu kiến trúc khác nhau.

---

## 1. Luồng OAuth 2.0 chung

Ba mô hình đều dựa trên một luồng xác thực cơ bản:

1. Người dùng mở ứng dụng.
2. Ứng dụng chuyển người dùng đến trang đăng nhập được quản lý bởi Cognito.
3. Cognito xác thực người dùng và trả về kết quả ủy quyền.
4. Client nhận session hoặc token tùy theo kiến trúc.
5. Dịch vụ bảo vệ backend kiểm tra session hoặc token trước khi chuyển request tiếp.

Nhờ vậy, Cognito chịu trách nhiệm quản lý danh tính, còn ứng dụng tập trung vào nghiệp vụ chính.

---

## 2. Mô hình 1: Application Load Balancer kết hợp Amazon Cognito

Application Load Balancer có thể xác thực người dùng trước khi request đến ứng dụng web. Khi nhận request chưa xác thực, ALB chuyển trình duyệt sang Cognito. Sau khi đăng nhập thành công, ALB tạo session và chỉ chuyển request hợp lệ đến target group.

### Ưu điểm

* Xác thực được xử lý trước khi traffic đến ứng dụng.
* Backend không cần tự triển khai toàn bộ luồng đăng nhập.
* Phù hợp với website truyền thống hoặc ứng dụng server-rendered đặt sau ALB.

### Hạn chế

* Phụ thuộc vào session và cookie của trình duyệt.
* Kém phù hợp hơn với mobile app và hệ thống API-first.
* Cơ chế xác thực gắn chặt với traffic đi qua ALB đó.

---

## 3. Mô hình 2: Amazon API Gateway kết hợp Amazon Cognito

Với REST API hoặc HTTP API, client đăng nhập qua Cognito rồi gửi JWT trong header `Authorization`. API Gateway xác minh token trước khi gọi backend integration. Token sai hoặc hết hạn sẽ bị từ chối ngay tại gateway.

### Ưu điểm

* Phù hợp với web, mobile và kiến trúc API.
* Chặn traffic không hợp lệ trước khi request đến backend.
* Backend có thể tập trung vào phân quyền nghiệp vụ và xử lý dữ liệu.
* Dễ mở rộng khi hệ thống được chia thành nhiều API hoặc service.

### Hạn chế

* Client phải lưu trữ và làm mới token an toàn.
* Scope, claim, CORS và cấu hình authorizer cần được thiết lập cẩn thận.
* API Gateway tạo thêm chi phí dịch vụ được quản lý.

---

## 4. Mô hình 3: CloudFront kết hợp AWS Lambda

Với ứng dụng phục vụ người dùng ở nhiều khu vực, CloudFront nhận request tại edge và Lambda@Edge kiểm tra trạng thái xác thực trước khi trả nội dung được bảo vệ. Request hợp lệ tiếp tục đến origin như ALB hoặc website trên S3. Origin cũng có thể yêu cầu secret header để ngăn người dùng bỏ qua CloudFront và truy cập trực tiếp.

### Ưu điểm

* Kiểm tra xác thực gần người dùng tại edge.
* Kết hợp kiểm soát truy cập với cache và phân phối nội dung toàn cầu.
* Có thể cô lập origin khỏi truy cập công khai trực tiếp.

### Hạn chế

* Quá trình triển khai và xử lý lỗi phức tạp hơn.
* Lambda@Edge chịu các giới hạn về Region và runtime.
* Token, cookie, cache behavior và redirect phải được thiết kế đồng bộ.

---

## 5. So sánh ba mô hình

| Mô hình | Phù hợp nhất | Trạng thái xác thực | Đánh đổi chính |
| --- | --- | --- | --- |
| **ALB + Cognito** | Website truyền thống | Session trình duyệt do ALB quản lý | Đơn giản nhưng phụ thuộc ALB và cookie |
| **API Gateway + Cognito** | Web/mobile gọi API | OAuth access token hoặc JWT | Linh hoạt, dễ mở rộng nhưng client phải quản lý token |
| **CloudFront + Lambda** | Ứng dụng toàn cầu và nội dung tại edge | Token hoặc secure cookie được kiểm tra tại edge | Kiểm soát mạnh nhưng triển khai phức tạp hơn |

Với TrustBite, mobile app và admin portal chủ yếu giao tiếp qua API. Vì vậy, xác minh JWT tại API Gateway hoặc middleware backend là điểm khởi đầu tự nhiên nhất. ALB authentication vẫn phù hợp cho cổng nội bộ chỉ chạy trên trình duyệt, còn CloudFront trở nên đáng cân nhắc khi hệ thống ưu tiên phân phối toàn cầu và bảo vệ origin.

---

## Kết luận

Amazon Cognito hỗ trợ nhiều kiến trúc kiểm soát truy cập thay vì buộc mọi ứng dụng dùng chung một mô hình. Lựa chọn phù hợp phụ thuộc vào loại client, thiết kế backend, cách quản lý session, quy mô và mức độ phức tạp vận hành mà đội ngũ có thể đảm nhận.

Với hệ thống API-first, API Gateway kết hợp Cognito giúp tách rõ xác thực khỏi dịch vụ nghiệp vụ. Với website truyền thống, xác thực tại ALB giúp giảm công việc cho backend. Với nền tảng toàn cầu, CloudFront kết hợp kiểm tra tại edge mang lại khả năng bảo vệ origin và phân phối nội dung tốt hơn.

---

## Tham khảo thêm

Bài viết đã đăng trên AWS Study Group:
[Các cách kiểm soát quyền truy cập ứng dụng Web trên AWS với Amazon Cognito](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2208350789929881/)
