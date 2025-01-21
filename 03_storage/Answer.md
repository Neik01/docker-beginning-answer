1. So sánh volume và bind mount
    - volume: Lưu trữ dữ liệu trên file của máy host. Muốn truy cập được dữ liệu này thì cần phải thông qua việc mount data từ máy host đến container. Việc lưu trữ này giúp bảo toàn dữ liệu kể cả khi container bị ngắt, xóa. Các volume sẽ được quản lý bởi Docker và tách biệt khỏi các chức năng của máy host. Nếu nguời dùng không chủ động tạo volume, Docker sẽ tự tạo một volume mặc định cho container 
    - bind mount: Tạo ra một liên kết giữa máy host và container, cho phép container có thể truy cập vào file hoặc folder của máy host. bind mount được quản lý bởi người dùng, cần phải có đường dẫn tuyệt đối đến nơi được mount, vậy nên, khi file hoặc thư mục bị lỗi hoặc không tồn tại, quá trình mount sẽ bị lỗi

2. Trường hợp sử dụng:
- Volume: 
    - Dễ lưu trữ và di chuyển hơn bind mount
    - Khi chia sẻ dữ liệu giữa nhiều container đang chạy
    - Lưu dữ liệu tới một server remote hoặc cloud.

-Bind mount:
    - Chia sẻ tài nguyên từ docker host tới container
    - Khi muốn tạo file trong container và lưu trữ lại trong host

3. 
Câu lệnh để chạy mysql với thư mục data (/var/lib/mysql) được mount vào **volume**: 
docker run -d --name mysql-container -e MYSQL_ROOT_PASSWORD=root -v /path/to/data:/var/lib/mysql mysql:latest

4. 
Sử dụng bind mount để đưa src vào container
Ứng dụng NodeJS
docker run -v ./path:/usr/src/app imageName
