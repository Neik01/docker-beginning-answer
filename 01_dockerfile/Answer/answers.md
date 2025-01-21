1. Ý nghĩa của các instruction:
    - `From`: Khởi tạo một build stage mới, đặt base image cho những instruction sau trong giai đoạn, có thể xuất hiện nhiều lần trong một dockerfile để tạo nhiều image hoặc dùng kết quả của giai đoạn này làm cơ sở cho giai đoạn sau
    - `RUN`: Thực thi các câu lệnh để tạo ra layer mới trên image hiện tại. 
    - `COPY`: Copy các file hoặc folder từ nguồn đến thư mục hệ thống đích của image hiện tại
    - `CMD`: Cài các câu lệnh sẽ được thực thi khi chạy container từ image. Chỉ có một lệnh CMD trong dockerfile có hiệu lực, nếu có nhiều hơn một lệnh chỉ có câu lệnh cuối cùng có hiệu lực

2. Base image dùng cho FROM thường được lấy từ dockerhub - Repository
3. Tạo dockerfile cho java - maven và javascript - npm
4. Khi chạy nhiều câu lệnh RUN, thường sử dụng kểt hợp với && để giảm bớt số layer được tạo ra, tăng hiệu suẩt build. Ngoài ra, các câu lệnh sau && chỉ có thể được thực thi nếu như các câu lệnh trước đó được thực thi thành công
5. Build Context là tập hợp các file và folder được dùng cho lệnh docker build 
6. Tác dụng của .dockerignore: Loại bỏ những thành phần không cần thiết khi build image, giúp giảm dung lượng của build context, giảm dung lượng cache và tăng tính bảo mật khi có thể loại bỏ những file chứa thông tin quan trọng