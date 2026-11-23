# Khai báo dùng AI — Nguyễn Công Quý · G04

| Công cụ | Yêu cầu hỗ trợ | Cách dùng kết quả | Đối chiếu |
|---|---|---|---|
| Codex | Đọc tài liệu Lab 12, chọn G04 và hỗ trợ tạo project, task, nhãn và nạp ảnh vào CVAT local. | Dùng để thiết lập bộ 22 ảnh và chuẩn bị quy trình gán nhãn. | Đối chiếu bộ nhãn Cabin v1.0, tên khung và số ảnh. |
| Codex, các công cụ phát hiện cục bộ | Hỗ trợ gán và rà nhãn cabin từ ảnh nguồn, gồm box, keypoint và thuộc tính. | Dùng để tạo và sửa đề xuất nhãn trên CVAT local, gồm rà DMS và OMS, sửa một điểm môi D06 trên job rà và cập nhật thuộc tính mặt trên Job #26. | Phóng vùng liên quan trên ảnh nguồn, đối chiếu với guideline và đọc lại annotation CVAT sau khi lưu. Các trường khó xác định giữ `unknown` hoặc `other`. |
| Codex | Xuất Job #26, chạy `cabin_check` và giải thích cảnh báo. | Dùng để tạo bản export chỉ có annotation và báo cáo E2. Hai báo cáo checkpoint được chạy lại từ export cuối. | Kiểm ZIP chỉ chứa `annotations.xml`, đủ 22 ảnh và 22 tag `frame_meta`, checker báo 0 lỗi và 4 cảnh báo. |
| Codex | Soạn hồ sơ nộp, gồm nhật ký IR, danh sách lớp, tự đánh giá, exit ticket, TEAM và khai báo này. | Dùng bản dự thảo để đối chiếu và hoàn thiện hồ sơ. | Đối chiếu tài liệu, bản export và mẫu nộp. |
| Codex | Đọc phiếu QC Phong, tăng sáng ảnh gốc để đối chiếu, cập nhật nhãn qua API CVAT và đóng lại hồ sơ. | Dùng để rà log QC, sửa các trường thấy rõ trên Job #26, xuất bản v2 chỉ gồm XML. | Đọc lại dữ liệu sau khi lưu, xác nhận chỉ thay đổi các đối tượng đã rà. Checker v2 báo 0 lỗi và một cảnh báo trục so mắt D02. |
| Codex | Đối chiếu schema mới của coach và ảnh gốc S01, S03, S04, S08. | Bổ sung 8 box ghế trẻ em rõ trên Job #26 và sửa 4 kết luận QC. | Kiểm schema, ranh giới box, xác minh annotation cũ giữ nguyên và chạy lại checker trên bản xuất XML. |
