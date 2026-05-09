# BÁO CÁO BÀI TẬP 02  
# XÂY DỰNG WEB QUẢN LÝ TIỆM CẦM ĐỒ BẰNG DJANGO  

## Thông tin sinh viên  

- Họ và tên: Ngụy Đình Tuấn Hà  
- MSV:K225480106011  
- Lớp: 58KTPM  
- Môn học: Phát triển ứng dụng với mã nguồn mở - TEE0421  

---

# 1. Giới thiệu đề tài  

Trong bài tập này em thực hiện xây dựng hệ thống quản lý tiệm cầm đồ bằng framework Django kết hợp với Docker và MariaDB.  

Mục tiêu của hệ thống:  
- Quản lý khách hàng  
- Quản lý tài sản cầm cố  
- Quản lý hợp đồng cầm đồ  
- Quản lý thanh toán  
- Theo dõi danh sách con nợ quá hạn  

Hệ thống sử dụng Django Admin để thực hiện chức năng thêm, sửa, xóa dữ liệu.  

---

# 2. Công nghệ sử dụng  

Các công nghệ được sử dụng trong bài:  

- Python 3.11  
- Django 5.0  
- MariaDB 11  
- phpMyAdmin  
- Docker  
- Docker Compose  
- Cloudflare Tunnel  

---

# 3. Kiến trúc hệ thống  

Hệ thống gồm 3 service chính:  

## MariaDB  
Dùng để lưu trữ dữ liệu của hệ thống quản lý tiệm cầm đồ.  

## phpMyAdmin  
Dùng để kiểm tra và quan sát cơ sở dữ liệu.  

## Django  
Dùng để xây dựng backend, giao diện quản trị và giao diện HTML.  

---

# 4. Thiết kế cơ sở dữ liệu  

Hệ thống gồm các bảng chính:  

- Quản lý khách hàng (Customers)  
- Quản lý loại tài sản (Asset types)  
- Quản lý tài sản (Assets)  
- Quản lý hợp đồng cầm đồ (Pawn contracts)  
- Quản lý thanh toán (Payments)  

Các bảng được liên kết với nhau bằng khóa ngoại.  

Ví dụ:
- Một khách hàng có nhiều hợp đồng cầm đồ  
- Một hợp đồng liên kết với một tài sản  
- Một hợp đồng có nhiều lần thanh toán  

Ngoài ra em có thiết kế sơ đồ cơ sở dữ liệu bằng tay và upload ảnh lên Github theo yêu cầu bài tập.  

---  

# 5. Chức năng của hệ thống  

Các chức năng chính:  

- Quản lý khách hàng  
- Quản lý tài sản  
- Quản lý hợp đồng cầm đồ  
- Quản lý thanh toán  
- Quản lý danh sách con nợ quá hạn  
- CRUD dữ liệu bằng Django Admin  

---

# 6. Django Admin  

Hệ thống sử dụng Django Admin để:  
- Thêm dữ liệu  
- Sửa dữ liệu  
- Xóa dữ liệu  

Các trường khóa ngoại được hiển thị bằng dropdown giúp dễ chọn dữ liệu liên kết.  

---

# 7. Giao diện HTML  

Hệ thống sử dụng Django Template để tạo giao diện HTML.  

Trang chủ hiển thị:  
- Danh sách con nợ quá hạn  
- Khách hàng  
- Tài sản cầm cố  
- Số tiền vay  
- Ngày hết hạn  

Dữ liệu được lấy từ view thông qua context.  

---

# 8. Docker  

Hệ thống được triển khai bằng Docker Compose.  

Các container:  
- mariadb_container  
- phpmyadmin_container  
- django_container  

Docker giúp:  
- Dễ triển khai  
- Dễ quản lý môi trường  
- Dễ mở rộng hệ thống  

---

# 9. Cloudflare Tunnel  

Sau khi hoàn thành hệ thống, em sử dụng Cloudflare Tunnel để public website ra Internet thông qua sub-domain.  

Điều này giúp có thể truy cập website từ bên ngoài mà không cần public IP thật.  

---

# 10. Kết quả đạt được  

Sau khi hoàn thành bài tập:  
- Chạy thành công Django bằng Docker  
- Kết nối MariaDB thành công  
- CRUD dữ liệu bằng Django Admin  
- Hiển thị giao diện HTML bằng Template  
- Public website bằng Cloudflare Tunnel  
- Kiểm tra dữ liệu bằng phpMyAdmin  

---

# 11. Hình ảnh minh họa  

Bài nộp bao gồm các hình ảnh minh họa sau:  

## 11.1 Docker Containers  

Hệ thống chạy thành công với 3 container chính:  

<img width="977" height="515" alt="z7807091866264_147e1cfe51afdd201eb3b68d71f99529" src="https://github.com/user-attachments/assets/4c3f0498-e334-414d-8462-9dc22ab9e5b2" />  


- **mariadb_container**: Lưu trữ cơ sở dữ liệu  
- **phpmyadmin_container**: Quản lý cơ sở dữ liệu  
- **django_container**: Chạy ứng dụng Django  

## 11.2 phpMyAdmin

Giao diện phpMyAdmin cho phép kiểm tra và quản lý dữ liệu trong MariaDB:  

<img width="1920" height="954" alt="z7807091160099_7b6431013abfca6e95e55f57fbac4507" src="https://github.com/user-attachments/assets/79c42c7f-7cea-4f6d-83a4-1b447235c066" />  


## 11.3 Giao diện HTML - Danh sách con nợ quá hạn  

Trang chủ hiển thị danh sách khách hàng có con nợ quá hạn:  

<img width="1852" height="1054" alt="z7807202987571_df40cfb94cbbedf732439938980fe2a1" src="https://github.com/user-attachments/assets/6e544e9a-bc12-4158-b48e-e7c802ed951f" />  


Bảng hiển thị thông tin:  
- ID: Mã khách hàng  
- Khách hàng: Tên khách hàng  
- Tài sản: Loại tài sản cầm cố  
- Số tiền vay: Số tiền đã vay  
- Ngày hết hạn: Hạn trả nợ  
- Trạng thái: Tình trạng hợp đồng  

## 11.4 Django Admin  

Django Admin cung cấp giao diện quản trị dữ liệu:  

<img width="1839" height="983" alt="z7807172138502_6153149581e57eaf79d2a41464bc5b84" src="https://github.com/user-attachments/assets/d6c0d490-a954-4c51-b6ba-2068e639be97" />  

Các chức năng:  
- Quản lý khách hàng (Customers)  
- Quản lý loại tài sản (Asset types)  
- Quản lý tài sản (Assets)  
- Quản lý hợp đồng cầm đồ (Pawn contracts)  
- Quản lý thanh toán (Payments)  

## 11.5 Cloudflare Tunnel  

Website được public bằng Cloudflare Tunnel với domain name:  

<img width="1691" height="930" alt="c89c004c-c3bf-4c8c-866b-c47e79acd097" src="https://github.com/user-attachments/assets/442d2f8d-611c-4751-9cb8-7abafc398b4a" />  

Thông tin Tunnel:  
- Tunnel name: pawnshop-new  
- Tunnel type: cloudflared  
- Status: HEALTHY  
- Uptime: 2 minutes  
  
## 11.6 Giao diện domian  

<img width="1672" height="941" alt="be219596-563d-400c-9fd3-ca66be1da5ba" src="https://github.com/user-attachments/assets/19bd78d0-cdce-489e-83cd-d0d499e4dfed" />  


# 12. Kết luận  

Qua bài tập này em đã:  
- Hiểu cách sử dụng Django  
- Hiểu cách kết nối Django với MariaDB  
- Biết sử dụng Docker Compose  
- Biết sử dụng Django Template  
- Biết triển khai website bằng Cloudflare Tunnel  

Đây là một bài tập giúp em hiểu rõ hơn về quy trình xây dựng và triển khai một ứng dụng web thực tế bằng mã nguồn mở.  
