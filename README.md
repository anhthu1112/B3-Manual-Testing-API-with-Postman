# 29/02/2024 Manual Testing API with Postman
## Nội dung chính

- Cơ bản về Manual testing API trong Postman
  + Quy trình testing API
  + Các test case trong testing API: 
    * Test case phi chức năng: chuẩn Restful API
    * Test case validation
    * Test case chức năng
- Làm quen postman script
- Viết test API bằng postman script

## Đầu ra học viên cần đạt

- Biết các bước của việc testing API
- Biết sử dụng Postman script biết test API

## Bài tập

### I. Lý thuyết

#### 1. Nêu quy trình của việc testing API
- Nhận tài liệu, API documentation 
- Viết testcase API 
- Thực hiện gọi các API 
- So khớp kết quả nhận được với test case ( Bằng tay hoặc dùng Postman Script)

#### 2. Các loại testcase của testing API

- Testcase về các tiêu chuẩn Restful API: 
  - Bộ API có đủ các API không: Get all, get a, post, put, delete; 
  - Url path: /api/v1/users, /api/v1/users/:id
  - Status code
  - Input data của request: request params, path variable, request body
  - Output data của response:
    - Status code valid
    - API GET list users: trả ra list + phân trang + status code 200
    - API GET 1 user: trả về 1 user + status code 200
    - API POST 1 user: trả về 1 user sau khi tạo + status code 201 Created
    - API PUT 1 user: trả về 1 user sau khi update + status code 200
    - API DELETE 1 user: không trả về cái gì hết + status code 200

- Testcase validate các trường dữ liệu đầu vào:
Dữ liệu người dùng truyền lên không thoả mãn các validation: trả lỗi 400 Bad request
Dữ liệu truyền lên không thể xử lý được: trả lỗi 422 Unprocessable entity
- Testcase về các chức năng của các API: 
Các API hoạt động như mô tả của tài liệu
Phương pháp tạo test case: phân lớp tương đương, phân tích giá trị biên, bảng quyết định


### II. Bài tập

#### 1. Thiết kế bộ testcase cho API: {{baseUrl}}/admin/customers.json của Sapo API

#### 2. Viết một testcase kiểm tra status code của API {{baseUrl}}/admin/customers.json bằng Postman script

Kiểm tra status code API khi gọi danh sách customers

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

#### Học 1 bài CoderX"