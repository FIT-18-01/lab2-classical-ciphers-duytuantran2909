# Report 1 Page – FIT4012 Lab 2
Nắm vững nguyên lý hoạt động của các thuật toán mã hóa cổ điển (Caesar, Rail Fence), triển khai thành thạo kỹ thuật xử lý chuỗi và đọc/ghi file trong C++, đồng thời làm quen với việc kiểm thử các trường hợp biên và tính đúng đắn của giải mã.

## 2. Cách làm
- Hoàn thiện Caesar Cipher cho chữ thường, dấu cách và giải mã.
- Hoàn thiện Rail Fence Cipher cho giải mã, giữ dấu cách, kiểm tra đầu vào và đọc file.
- Chạy thử trên nhiều test case.

## 3. Kết quả chính
### 3.1 Caesar Cipher
| Input | Key | Ciphertext / Plaintext | Nhận xét |
|---|---:|---|---|
| I LOVE YOU | 3 | L OYH BRX | Giữ nguyên dấu cách, dịch chuyển đúng 3 vị trí. |
| hello world | 5 | mjqqt btwqi | Xử lý tốt chữ thường và khoảng trắng. |
| LORYH BRX | 3 | I LOVE YOU | Giải mã chính xác về văn bản gốc. |

### 3.2 Rail Fence Cipher
| Input | Rails | Ciphertext / Plaintext | Nhận xét |
|---|---:|---|---|
| I LOVE YOU | 2 | ILOEYOUV | Gom nhóm theo 2 hàng zigzag (I O E Y U / L V O). |
| I LOVE YOU | 4 | IY OL OVEU | Phân tán ký tự thưa hơn trên 4 hàng. |
| IOEOLVYU | 2 | I LOVE YOU | Giải mã thành công từ cấu trúc zigzag 2 hàng. |

### 3.3 Input validation / file input
- Trường hợp đầu vào không hợp lệ: Hệ thống hiển thị thông báo lỗi khi Rails <= 1 hoặc Key < 0, yêu cầu người dùng nhập lại thay vì gây tràn bộ nhớ hoặc lỗi logic.
- Kết quả đọc từ `data/input.txt`: Chương trình đọc thành công chuỗi dữ liệu dài từ file, thực hiện mã hóa hàng loạt và xuất kết quả ra màn hình/file output đúng định dạng.

## 4. Kết luận
Thông qua bài lab, em đã hiểu rõ sự khác biệt giữa mã hóa thay thế (Caesar) và mã hóa hoán vị (Rail Fence). Khó khăn lớn nhất nằm ở việc logic hóa đường đi zigzag của Rail Fence khi giải mã. Việc vẽ tay ma trận trước khi code đã giúp em hình dung rõ hơn về luồng dữ liệu, từ đó triển khai thuật toán chính xác hơn.