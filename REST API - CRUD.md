  PHẦN I: REST API (REpresentational State Transfer Application Programming Interface) 
  
REST API là một kiểu kiến trúc được sử dụng rộng rãi để xây dựng các giao diện lập trình ứng dụng (API) dựa trên web. Nó đóng vai trò như một cầu nối cho phép các hệ thống phần mềm khác nhau giao tiếp và trao đổi dữ liệu thông qua môi trường internet. 

I. Cách thức hoạt động
REST API hoạt động dựa trên mô hình Client-Server và sử dụng giao thức HTTP để thực hiện các thao tác trên tài nguyên (Resources). Mỗi tài nguyên được định danh bằng một địa chỉ URL duy nhất. 
Dưới đây là các phương thức HTTP (HTTP Methods) phổ biến nhất được sử dụng trong REST:
.GET: Lấy thông tin từ một hoặc một danh sách tài nguyên.
.POST: Tạo mới một tài nguyên.
.PUT: Cập nhật toàn bộ thông tin của một tài nguyên đã tồn tại
.PATCH: Chỉ cập nhật một phần dữ liệu cụ thể của tài nguyên.
.DELETE: Xóa bỏ một tài nguyên khỏi hệ thống. 

II. Định dạng dữ liệu
Khi trao đổi dữ liệu, REST API thường sử dụng các định dạng nhẹ và dễ đọc, phổ biến nhất là JSON (JavaScript Object Notation), đôi khi cũng sử dụng XML hoặc văn bản thuần túy. 

III. Các đặc điểm chính (Constraints)
Để được gọi là một RESTful API chuẩn, kiến trúc cần tuân thủ 6 ràng buộc cơ bản, bao gồm: 
1.Client-Server: Tách biệt rõ ràng giữa giao diện người dùng và hệ thống lưu trữ dữ liệu.
2.Stateless (Không trạng thái): Mỗi yêu cầu (request) từ client phải chứa đầy đủ thông tin cần thiết để server hiểu và xử lý, không lưu trữ ngữ cảnh giữa các request.
3.Cacheable: Phản hồi từ server có thể được đánh dấu là có thể lưu bộ nhớ đệm (cache) để cải thiện hiệu suất.
4.Layered System (Hệ thống phân tầng): Client không cần biết mình đang kết nối trực tiếp với server cuối hay qua các máy chủ trung gian (như proxy, load balancer).
5.Uniform Interface: Giao diện thống nhất giúp việc giao tiếp giữa các thành phần trở nên đơn giản hơn.
6.Code on Demand (Tùy chọn): Server có thể gửi mã thực thi (như JavaScript) về cho client. 

IV. Lợi ích của REST API
Tính linh hoạt: Có thể được sử dụng bởi bất kỳ ngôn ngữ lập trình nào hỗ trợ HTTP.
Dễ mở rộng: Cấu trúc phân tầng và không trạng thái giúp hệ thống dễ dàng mở rộng quy mô.
Hiệu suất: Tiết kiệm tài nguyên mạng nhờ các định dạng dữ liệu nhẹ như JSON. 

   Phần II: CRUD
   
CRUD là viết tắt của bốn thao tác cơ bản nhất để quản lý dữ liệu: Create (Tạo), Read (Đọc), Update (Cập nhật) và Delete (Xóa)
1. Ý nghĩa của các thành phần trong CRUD
Create (C): Thêm dữ liệu mới vào hệ thống (ví dụ: đăng ký tài khoản mới, tạo bài viết mới).
Read (R): Truy xuất hoặc xem dữ liệu hiện có mà không làm thay đổi nó (ví dụ: xem danh sách sản phẩm, đọc nội dung email).
Update (U): Chỉnh sửa dữ liệu đã tồn tại (ví dụ: đổi mật khẩu, cập nhật giá sản phẩm).
Delete (D): Xóa bỏ dữ liệu khỏi hệ thống (ví dụ: xóa một bình luận, hủy đơn hàng).
2. Ánh xạ CRUD trong thực tế
### Tùy vào công nghệ bạn sử dụng, CRUD sẽ tương ứng với các lệnh hoặc phương thức cụ thể:
|Thao tác|SQL (Database)|	HTTP Method (REST API)|	MongoDB (NoSQL)|
|---------|-----------|---------------|--------|
|Create|INSERT|POST|insertOne() / insertMany()|
|Read|SELECT|GET|find() / findOne()|
|Update|UPDATE|PUT / PATCH|updateOne() / updateMany()|
|Delete|DELETE|DELETE|deleteOne() / deleteMany()|
---
3. Tại sao CRUD lại quan trọng?
Tiêu chuẩn hóa: CRUD cung cấp một khung làm việc (framework) thống nhất giúp lập trình viên thiết kế hệ thống dữ liệu đầy đủ và dễ bảo trì.
Quản lý vòng đời dữ liệu: Nó bao quát toàn bộ quá trình của một tài nguyên dữ liệu từ khi được tạo ra cho đến khi bị xóa bỏ.
Nền tảng cho Backend: 90% thời gian lập trình backend thường xoay quanh việc xử lý các thao tác CRUD
4. Các biến thể phổ biến của CRUD
Ngoài 4 thao tác chính, người ta còn mở rộng thêm các biến thể khác để phù hợp với từng mục đích cụ thể:
CRUDL: Thêm List (Liệt kê danh sách lớn, thường đi kèm phân trang).
BREAD: Viết tắt của Browse, Read, Edit, Add, Delete (thường dùng trong thiết kế giao diện người dùng).
DAVE: Viết tắt của Delete, Add, View, Edit
