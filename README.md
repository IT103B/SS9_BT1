# Bài 1 — Truy cập thuộc tính động bằng Bracket Notation

## Phân tích lỗi

Dòng `bookingReservation.priceKey` truy cập thuộc tính có tên cố định là `"priceKey"`, không phải giá trị `"roomPrice"` nằm trong biến `priceKey`. Vì đối tượng không có thuộc tính `priceKey`, kết quả là `undefined`. Phép nhân `undefined * 0.3` và phép cộng `undefined + surcharge` đều tạo ra `NaN`, làm sai phụ thu và tổng tiền.

Dùng `bookingReservation[priceKey]` để JavaScript lấy giá trị của biến làm tên thuộc tính. Dot notation chỉ phù hợp khi tên thuộc tính được biết cố định trong mã nguồn.

## Test cases

| Trường hợp kiểm thử | Dữ liệu đầu vào | Kết quả sai thực tế | Kết quả đúng mong đợi |
|---|---|---|---|
| Nhận phòng sớm | `roomPrice = 1.500.000`, `checkInHour = 9`, `priceKey = "roomPrice"` | `basePrice` là `undefined`; phụ thu và tổng tiền là `NaN` | Giá cơ bản `1.500.000`; phụ thu 30% là `450.000`; tổng tiền `1.950.000` |
| Nhận phòng từ 12 giờ trở đi | `roomPrice = 1.500.000`, `checkInHour = 12`, `priceKey = "roomPrice"` | `basePrice` là `undefined`; tổng tiền là `NaN` | Không có phụ thu; tổng tiền `1.500.000` |

Chạy bằng `node solution_ex1.js` trong thư mục `bt1`.
