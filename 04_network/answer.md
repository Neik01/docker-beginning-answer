1. Những network mặc định được tạo ra bởi docker:
    - bridge: Docker sử dụng một phần mềm bridge, giúp cho các container được kết nối vào chung mạng bridge có thể kết nối với nhau và cô lập với các container không được kết nối vào mạng này
    - host: Container dùng mạng trực tiếp của host
    - nonde: Container không được cấu hình mạng

2. Khi run một container, nếu không chỉ định mạng thì nó sẽ dùng mạng brigde mặc định của Docker

3. Các cách để liên kết 1 container với 1 network
    - Sử dụng option --network trong lệnh docker run
    - Nếu container đã run, có thể sử dụng lệnh docker network connect
    - Sử dụng docker compose 

4. Câu lệnh để tạo network tên my_net: 
    **docker network create my_net**
    Network này thuộc mạng bridge

5. Chạy container database mysql:

    **docker run --name mysql-db --network my_net -e MYSQL_ROOT_PASSWORD=root -e MYSQL_USER=user -e MYSQL_PASSWORD=root -e MYSQL_DATABASE=testdb -d mysql:latest**

  Thêm các env vào Dockerfile  
  Chạy container web:
  **docker run -v .:/usr/src/app -p 3000:3000 --network my_net --name node-app -d  node-app**
