---
title: "Worklog Tuần 10"
date: 2026-06-28
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---
### Mục tiêu tuần 10:

* Thiết lập đầy đủ môi trường backend và cơ sở dữ liệu TrustBite.
* Tìm hiểu Repository Harness, soft delete, phân quyền và quy trình story.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Thiết lập Docker Compose cho PostgreSQL, Redis, LocalStack và pgAdmin.<br>- Chạy `npm run docker:up` và kiểm tra kết nối cơ sở dữ liệu. | 29/06/2026 | 29/06/2026 | [Docker Compose](https://docs.docker.com/compose/)<br>[Local Development Guide](https://github.com/NguyenSonnt04/docs_trustbite) |
| 3 | - Áp dụng migration `001_init_schema.sql`.<br>- Tìm hiểu `pgcrypto`, PostGIS, các bảng dữ liệu và `schema_migrations`. | 30/06/2026 | 30/06/2026 | [Database Schema](https://github.com/trustbite-team-tcc/trustbite-review-system)<br>[PostGIS Documentation](https://postgis.net/documentation/) |
| 4 | - Nghiên cứu backend Express Native ESModules theo kiến trúc phân tầng.<br>- Rà soát config, routes, controllers, services, models và middlewares. | 01/07/2026 | 01/07/2026 | [TrustBite Backend](https://github.com/trustbite-team-tcc/trustbite-review-system)<br>[Express Documentation](https://expressjs.com/) |
| 5 | - Cài Harness CLI, khởi tạo database và truy vấn test matrix.<br>- Hoàn thành story TB-HARNESS. | 02/07/2026 | 02/07/2026 | [Repository Harness](https://github.com/trustbite-team-tcc/trustbite-review-system)<br>[TB-HARNESS Story](https://github.com/NguyenSonnt04/docs_trustbite) |
| 6 | - Rà soát soft delete cho restaurants.<br>- Tìm hiểu roles, user_roles, rank_definitions, coding convention và story packet. | 03/07/2026 | 03/07/2026 | [Mô hình dữ liệu](https://github.com/trustbite-team-tcc/trustbite-review-system)<br>[Coding Convention](https://github.com/NguyenSonnt04/docs_trustbite) |

### Kết quả đạt được tuần 10:

* Vận hành được môi trường backend và áp dụng migration dữ liệu cốt lõi.
* Hoàn thành TB-HARNESS và hiểu mô hình soft delete, phân quyền, coding convention của dự án.
