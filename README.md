## 1. Tạo Docker Image

Chạy lệnh trong thư mục `ex03`, nơi chứa hai tệp `Dockerfile` và `index.html`:

```bash
docker build -t my-html-app:v1 .
```

Image được đặt tên là `my-html-app` với tag `v1`.

## 2. Khởi chạy container

```bash
docker run -d -p 8081:80 --name html-app my-html-app:v1
```

Container có tên `html-app`. Cổng `8081` trên máy được ánh xạ đến cổng `80` của Nginx trong container.

## 3. Kiểm tra nội dung trang web

```bash
curl http://localhost:8081
```

Trên Windows PowerShell, có thể dùng `curl.exe http://localhost:8081` để gọi trực tiếp chương trình curl.

Kết quả minh họa (log mô phỏng, chưa chạy Docker thực tế):

```text
<h1>Hello Docker Session 09!</h1>
```

Có thể mở `http://localhost:8081` trên trình duyệt để xem trang web.
