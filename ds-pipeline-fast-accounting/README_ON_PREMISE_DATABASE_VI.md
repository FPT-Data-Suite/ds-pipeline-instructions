Để Data Suite hiển thị dữ liệu thực tế trên báo cáo, bạn cần cài đặt Data Collector Agent trên server. Agent sẽ trích xuất dữ liệu từ database Fast Accounting và gửi về Data Suite dưới dạng raw data. Dữ liệu này sau đó được xử lý qua pipeline ETL để sẵn sàng hiển thị.

1. Nhấn "Tải Data Agent" phía trên, giải nén để lấy thư mục **./repo**
2. Upload thư mục **./repo** lên server của bạn.
3. Chỉnh sửa file **./repo/agent.env** để nhập thông tin kết nối database. Lưu ý: sử dụng tài khoản có quyền đọc dữ liệu từ database Fast Accounting.
4. Cài đặt Docker và Docker Compose trên server
   ```$ cd ./repo
   $ apt update
   $ apt install docker.io
   $ apt install docker-compose-plugin
```
5. Build và chạy agent
   ```$ docker compose build
   $ docker compose up -d
```
6. Để dừng agent
   ```$ docker compose down
```
7. Kiểm tra danh sách bên trái để xem raw data đã tải lên Data Suite chưa. Khi nút "Kích hoạt Pipeline" sáng, hệ thống đã sẵn sàng thông luồng.
8. Nhấn "Kích hoạt Pipeline" để chạy ETL và xem dữ liệu thực tế xuất hiện trên báo cáo.