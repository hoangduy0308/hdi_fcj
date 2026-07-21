---
title: "Worklog Tuần 11"
date: 2026-07-05
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---
### Mục tiêu tuần 11:

* Hoàn thiện kiểm thử JWT, đăng nhập và hồ sơ người dùng.
* Xây dựng GPS Proximity Service và rà soát CI cho TrustBite.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Tìm hiểu CognitoIdentityProvider và cơ chế xác thực JWT.<br>- Viết test cho token hợp lệ, hết hạn và bị cắt xén. | 06/07/2026 | 06/07/2026 | [Cognito JWT Verification](https://docs.aws.amazon.com/cognito/)<br>[JWT Test Suite](https://github.com/trustbite-team-tcc/trustbite-review-system) |
| 3 | - Viết test cho sai issuer, sai `client_id` và sai chữ ký.<br>- Refactor helper sinh JWT bằng cặp khóa RSA trong bộ nhớ. | 07/07/2026 | 07/07/2026 | [RSA JWT Helper](https://github.com/trustbite-team-tcc/trustbite-review-system)<br>[Vitest Documentation](https://vitest.dev/) |
| 4 | - Viết integration test cho đăng nhập và user profile.<br>- Kiểm thử user hợp lệ, SUSPENDED và request không có token. | 08/07/2026 | 08/07/2026 | [Authentication API](https://github.com/trustbite-team-tcc/trustbite-review-system)<br>[Integration Test Guide](https://github.com/NguyenSonnt04/docs_trustbite) |
| 5 | - Xây dựng `gpsProximityService.js` bằng công thức Haversine.<br>- Tạo `antiFraud.js` với ngưỡng GPS mặc định 200 mét và validation đầu vào. | 09/07/2026 | 09/07/2026 | [GPS Proximity Service](https://github.com/trustbite-team-tcc/trustbite-review-system)<br>[Anti-Fraud Configuration](https://github.com/NguyenSonnt04/docs_trustbite) |
| 6 | - Viết 13 GPS unit test; tổng cộng 80 test đều đạt.<br>- Rà soát GitHub Actions chạy database migration và Vitest. | 10/07/2026 | 10/07/2026 | [GPS Test Suite](https://github.com/trustbite-team-tcc/trustbite-review-system)<br>[GitHub Actions](https://docs.github.com/actions) |

### Kết quả đạt được tuần 11:

* Hoàn thiện kiểm thử Cognito JWT, login và user profile.
* Xây dựng GPS Proximity Service có cấu hình, validation và 13 test case; toàn bộ 80 test đều đạt.
