# Sổ tay hướng dẫn canh tác cà chua

Báo cáo thực tập cơ sở: website thông tin về canh tác cà chua, viết bằng **PHP + MySQL**, chạy trên XAMPP.

> Đây là khung dự án trống. Mỗi thành viên viết code trong thư mục của mình theo bảng phân công bên dưới.

## Cấu trúc thư mục

```
tomato-guide/
├── admin/        Trang quản trị (đăng nhập, quản lý bài viết, sâu bệnh...)
├── public/       Trang người xem (danh sách, chi tiết, tìm kiếm, tra cứu)
├── includes/     Mã dùng chung (kết nối CSDL, hàm tiện ích, header, footer)
├── assets/
│   ├── css/      Giao diện
│   ├── js/       JavaScript
│   └── img/      Ảnh giao diện (logo, banner)
├── config/       Cấu hình (config.php riêng từng máy, không đưa lên Git)
├── database/     Script SQL tạo bảng và dữ liệu mẫu
├── uploads/      Ảnh người dùng tải lên (không đưa lên Git)
└── docs/         Báo cáo, sơ đồ (use case, ERD), test case, nội dung bài viết
```

## Phân công

| Thành viên | Thư mục phụ trách |
|---|---|
| Trung (nhóm trưởng) | `database/`, `config/`, `includes/` (kết nối CSDL), gộp code vào `main` |
| Dũng | `admin/`, `uploads/`, đăng nhập và phân quyền |
| Quang Anh | `public/`, truy vấn và tìm kiếm cho trang người xem |
| Vũ | `assets/`, header và footer, lịch canh tác, triển khai |
| Giang | `docs/`, nội dung bài viết, kiểm thử, tổng hợp báo cáo |

## Quy ước làm việc nhóm
- Tên bảng, cột CSDL: tiếng Anh, viết thường, dạng `snake_case`. Chỉ Trung được đổi cấu trúc bảng, cần thêm cột thì báo Trung.
- Mỗi người một nhánh: `dung-admin`, `quanganh-public`, `vu-ui`, `giang-docs`. Chỉ Trung gộp vào `main` qua Pull Request.
- Commit nhỏ, mô tả rõ việc đã làm. Đẩy code lên GitHub cuối mỗi buổi làm.
- Không commit `config/config.php` và ảnh trong `uploads/`.
- Luôn dùng PDO prepared statement khi truy vấn, và `htmlspecialchars` khi in dữ liệu ra HTML.

## Cách chạy trên máy (XAMPP)
1. Đặt dự án tại `C:\xampp\htdocs\tomato-guide`.
2. Bật Apache và MySQL trong XAMPP Control Panel.
3. Import file SQL trong `database/` bằng phpMyAdmin (sẽ bổ sung khi có).
4. Tạo `config/config.php` (nhóm thống nhất mẫu cấu hình, ví dụ `config.example.php`).
5. Mở http://localhost/tomato-guide/

## Tiến độ
Xem lịch mốc trong file Excel của nhóm. Mốc quan trọng: code freeze 02/12, chương trình hoàn thành 08/12, bản thảo báo cáo 16/12.
