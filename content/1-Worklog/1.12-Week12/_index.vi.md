---
title: "Worklog Tuần 12"
date: 2026-07-12
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---
### Mục tiêu tuần 12:

* Hoàn thiện các luồng receipt, review, restaurant và kiểm thử mobile.
* Rà soát, sửa lỗi cuối kỳ và xây dựng nền tảng Terraform AWS MVP.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Phát triển module xử lý hóa đơn backend.<br>- Xây dựng S3 upload, tích hợp OCR queue và test các trường hợp lỗi. | 13/07/2026 | 13/07/2026 | [Receipt Processing Module](https://github.com/trustbite-team-tcc/trustbite-review-system)<br>[Amazon S3 & Textract](https://docs.aws.amazon.com/textract/) |
| 3 | - Phát triển review API.<br>- Viết integration test cho toàn bộ luồng tạo, xác minh và trả kết quả review. | 14/07/2026 | 14/07/2026 | [Review API](https://github.com/trustbite-team-tcc/trustbite-review-system)<br>[Review Integration Tests](https://github.com/NguyenSonnt04/docs_trustbite) |
| 4 | - Phát triển tìm kiếm và lọc nhà hàng Phase 3.<br>- Viết integration test cho danh sách, chi tiết và tìm kiếm nhà hàng. | 15/07/2026 | 15/07/2026 | [Restaurant API](https://github.com/trustbite-team-tcc/trustbite-review-system)<br>[Phase 3 Documentation](https://github.com/NguyenSonnt04/docs_trustbite) |
| 5 | - Kiểm thử Cognito login, điều hướng, Home, Thông báo và hồ sơ mobile.<br>- Rà soát Favorites, Splash Screen, icon và tính nhất quán UI. | 16/07/2026 | 16/07/2026 | [TrustBite Mobile](https://github.com/trustbite-team-tcc/trustbite-review-system)<br>[Cognito Authentication](https://docs.aws.amazon.com/cognito/) |
| 6 | - Sửa lỗi, refactor và dọn mã nguồn.<br>- Xây dựng Terraform MVP cho VPC, ECS, RDS, Redis, S3, IAM, CloudWatch; chạy format, init, validate, plan và không apply production. | 17/07/2026 | 17/07/2026 | [Terraform AWS MVP](https://github.com/trustbite-team-tcc/trustbite-review-system)<br>[Terraform Documentation](https://developer.hashicorp.com/terraform/docs) |

### Kết quả đạt được tuần 12:

* Hoàn thiện và kiểm thử các luồng receipt, review, restaurant và nhiều màn hình mobile.
* Khắc phục lỗi cuối kỳ và hoàn thành Terraform AWS MVP ở mức validate/plan, không triển khai production.
