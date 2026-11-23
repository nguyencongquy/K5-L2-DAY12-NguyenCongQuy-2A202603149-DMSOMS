# TEAM — Ngày 12

Mã bộ ảnh **G04** · Hình thức **cá nhân**

| Họ tên | MSSV | Phạm vi export | Bạn review chéo | Số dòng đã xử lý |
|---|---|---|---|---:|
| Nguyễn Công Quý | 2A202603149 | Đủ 22 ảnh | Trần Phạm Hoàng Phong · 2A202603198 | 35 |

Phong gửi phiếu QC cho Quý ngày 23/11/2026. Quý đối chiếu file của Phong và rà ảnh gốc để cập nhật v2. Log giữ mốc so sánh với bản gốc của Quý. Đã ghi kết quả rà cho 35/96 dòng, gồm 4 dòng mơ hồ. Các dòng còn lại để nguyên kết quả diff. Cột verdict ghi quyết định sau khi rà, chưa ghi là hai bên đồng thuận toàn bộ.

Ca mơ hồ còn ghi trong log gồm cờ che khuất mí trái D01 và ranh giới box tay phải D06. Sau cập nhật schema của coach, v2 thêm 8 box `child_seat` rõ trên S01, S03, S04 và S08 (mỗi cảnh một ảnh RGB và một ảnh IR-sim), với `occupied=yes`. Bốn kết luận về ghế S03 và S04 trong log được sửa. Các box nôi, người, mặt và đồ vật giữ nguyên.

## Cá nhân

### Nguyễn Công Quý · 2A202603149

- Phần bài cá nhân gồm 16 ảnh OMS và 6 ảnh DMS. Bản v2 có 22 tag `frame_meta`, 0 lỗi và một cảnh báo trục so mắt D02. Kết quả trước và sau review nằm ở `check_final.txt` và `check_final_v2.txt`.
- Điểm rút ra là xác định trái/phải theo người hoặc theo xe trước khi điền. Trên DMS xoay 90°, dùng trục y để đối chiếu mắt. Trên OMS nhìn về hàng ghế sau, người bên trái ảnh ngồi ở `rear_right`.
