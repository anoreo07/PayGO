# TÀI LIỆU PayGO — Hệ thống ví điện tử

## Tổng quan
PayGO là hệ thống ví điện tử di động phục vụ người dùng tại Việt Nam, hỗ trợ quản lý và thực hiện giao dịch tài chính cá nhân một cách an toàn và thuận tiện. Hệ thống được xây dựng trong khuôn khổ môn học Công nghệ phần mềm tại Trường Đại học Công nghệ – ĐHQGHN.

## Mục tiêu
- Xây dựng ứng dụng ví đa nền tảng (iOS, Android) với trải nghiệm người dùng thân thiện.
- Đảm bảo hiệu năng, khả năng mở rộng và bảo mật ở mức doanh nghiệp.
- Dễ dàng tích hợp với ngân hàng và nhà cung cấp dịch vụ (hóa đơn, vé, nạp tiền).

## Phạm vi
Ứng dụng tập trung vào phần mềm di động, bao gồm:
- Đăng ký và đăng nhập người dùng.
- Quản lý ví và lịch sử giao dịch.
- Nạp tiền, rút tiền, chuyển tiền giữa các ví.
- Thanh toán hóa đơn, mua vé và nạp tiền điện thoại.
- Hệ thống hỗ trợ khách hàng trong ứng dụng.

## Tính năng chính

### Quản lý người dùng
- Đăng ký tài khoản bằng mật khẩu.
- Đăng nhập bằng mật khẩu hoặc sinh trắc học.
- Cập nhật thông tin hồ sơ người dùng.

### Quản lý ví
- Xem số dư ví.
- Xem và lọc lịch sử giao dịch.
- Thống kê chi tiêu theo loại giao dịch.

### Giao dịch tài chính
- Liên kết tài khoản ngân hàng.
- Nạp tiền từ ngân hàng vào ví.
- Rút tiền từ ví về ngân hàng.
- Chuyển tiền giữa các ví PayGO (P2P).

### Dịch vụ thanh toán
- Thanh toán hóa đơn điện, nước, Internet.
- Mua vé tàu, xe khách, vé xem phim.
- Nạp tiền điện thoại.

### Hỗ trợ khách hàng
- Hệ thống trả lời tự động (IVR).
- Gửi yêu cầu hỗ trợ trực tiếp trong ứng dụng.

## Kiến trúc hệ thống
Hệ thống được thiết kế theo kiến trúc Microservices kết hợp Domain-Driven Design, bao gồm:

- Mobile App (Flutter)
- API Gateway
- Core Services:
  - IAM Service (quản lý người dùng và xác thực)
  - Wallet Engine (quản lý số dư và giao dịch)
  - Payment Service (xử lý thanh toán)
  - Support Service (hỗ trợ khách hàng)
- Integration Layer:
  - Bank Gateway
  - Service Provider Gateway
  - Notification Service
- Foundational Services:
  - Message Queue (Kafka hoặc RabbitMQ)
  - Cache (Redis)
  - Monitoring (Prometheus, Grafana)
  - Logging (ELK Stack)

## Cơ sở dữ liệu
Hệ thống sử dụng cơ sở dữ liệu quan hệ kết hợp NoSQL, được chuẩn hóa và tách riêng dữ liệu nhạy cảm.

Các bảng chính:
- users, user_profiles, biometric_data
- wallets, transactions
- bank_accounts
- bills, tickets, service_providers
- support_tickets, notifications
- security_logs

Quan hệ chính:
- Một user tương ứng một wallet.
- Một wallet có nhiều transactions.
- Một user có nhiều bank_accounts, support_tickets và notifications.

## Bảo mật và tuân thủ
- Xác thực đa yếu tố (MFA).
- Mã hóa dữ liệu lưu trữ bằng AES-256.
- Mã hóa dữ liệu truyền tải bằng TLS 1.3.
- Ghi log và giám sát bảo mật.
- Tuân thủ các tiêu chuẩn PCI-DSS và ISO 27001.

## Yêu cầu phi chức năng
- Hiệu năng: xử lý tới 10.000 giao dịch mỗi giây.
- Độ trễ: 95% giao dịch hoàn thành trong vòng 2 giây.
- Tính sẵn sàng: uptime mục tiêu 99.99%.
- Khả năng mở rộng: hỗ trợ tới 10 triệu người dùng.
- Khả năng bảo trì: hỗ trợ CI/CD và triển khai tự động.

## Giao diện người dùng
Thiết kế UI/UX được xây dựng trên Figma, hỗ trợ thao tác cảm ứng, sinh trắc học và giao diện tiếng Việt.

## Nhóm phát triển
- Nguyễn Hải An — 23020581  
- Lê Hoàng Anh — 23020583  
- Vũ Quốc Anh — 23020587  
- Ngô Thị Thảo Linh — 23020620  

