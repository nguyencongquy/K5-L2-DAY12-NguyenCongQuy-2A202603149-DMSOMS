# Tự đánh giá — Nguyễn Công Quý · G04

## Rà soát bốn khung

| Ảnh | Đối tượng | Loại lỗi | Ghi chú | Đã sửa? |
|---|---|---|---|---|
| S02_ir.png | Người lớn và nôi | `ok` | Người bên phải ảnh là `rear_left` và thấy rõ không có đường dây trên thân. Nôi ở phía đối diện là `rear_right`. | Giá trị bản cuối đã khớp. |
| S08_rgb.png | Dây an toàn người lớn | `guess` | Bản gốc để `unknown` vì vùng thân tối. Khi tăng sáng riêng ảnh RGB, thấy vai và hông không có dải dây. | V2 đổi `not_worn`. |
| D02.png | Thứ tự mắt ngoài | `ok` | Kiểm lại trục y, mắt trái 826,19 px và mắt phải 549,37 px. | Đã giải thích cảnh báo trục x. |
| D04.png | Mắt phải và `face13` | `flag` | Ảnh nghiêng và tối ở mắt phải. Khó phân biệt khe mí và không định vị được giữa mép mí trên, dưới. | V2 giữ `eye_right=unknown`, đặt hai điểm mí phải `outside`. |

## Lỗi lặp lại nhiều nhất

Trạng thái mắt `unknown` và cờ hiển thị của từng keypoint chưa được đối chiếu cùng lượt. Hiện tượng lặp ở D01, D03 và D04. Khi rà lần sau, phóng vùng mắt, quyết định trạng thái mí và kiểm bốn điểm của mắt đó trước khi chuyển ảnh. Với điểm bị che mà xác định được vị trí, dùng `occluded`. Nếu vị trí cũng không xác định được, dùng `outside`.

## Ghi chú về review chéo

Phong gán `worn_correct` ở D01, bản của Quý để `unknown`. Khi rà ảnh gốc thấy dải dây chéo từ vai xuống hông đối diện nên v2 nhận giá trị của Phong. Bài học là phóng cả vùng vai và hông trước khi để `unknown`.
