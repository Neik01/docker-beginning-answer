1. Ý nghĩa câu lệnh:
    - docker compose build: Build hoặc rebuild toàn bộ service 
    - docker compose up: Tạo và chạy các container tương ứng với service
    - docker compose down: Dừng các container và xóa các volume, network, image, container được tạo bởi lệnh up
    - docker compose start: Khởi động các container tương ứng với các service
    - docker compose stop: Tạm dừng các container đang chạy mà không xóa chúng
    - docker compose restart: Khởi động lại tất cả các container đã dừng hoặc đang chạy, hoặc có thể chỉ định service 
    - docker compose logs: Hiển thị logs của service
    - docker compose exec: Thực thi câu lệnh trên container

2. Sử dụng depends_on kết hợp với condition trong docker-compose file để đảm bảo việc khởi động theo thứ tự của các service

3. 