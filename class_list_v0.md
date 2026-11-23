# Danh sách lớp v0 — Nguyễn Công Quý · G04

## DMS

| Lớp hoặc thuộc tính | Giá trị | Để làm gì | Nhìn thấy trên IR? |
|---|---|---|---|
| `person` và `seat` | Box người, `driver` | Xác định vùng tài xế để ghép mặt, tay và dây đúng người. | Có nếu thân người còn trong khung. |
| `face` | Box mặt | Cắt vùng mặt để ước lượng mắt và hướng đầu. | Có khi còn thấy đủ mặt. |
| `eye_left`, `eye_right` | `open`, `closed`, `unknown` | Đo thời gian khép mắt qua nhiều khung cho chức năng cảnh báo buồn ngủ. | Có nếu thấy khe mí. Gọng và phản xạ làm giảm độ tin cậy. |
| `face13` | 13 điểm và cờ `occluded`/`outside` | Ước lượng hướng đầu và theo dõi hình học của mắt, mũi, miệng. | Có theo từng điểm, phụ thuộc góc mặt và độ che. |
| `glasses` | `none`, `clear`, `sun`, `unknown` | Điều chỉnh độ tin cậy của tín hiệu mắt khi tài xế đeo kính. | Có thể thấy gọng. Khó phân biệt kính râm với kính trong chỉ bằng độ sáng NIR. |
| `gaze_zone` | `road`, `mirror_l`, `mirror_r`, `mirror_c`, `cluster`, `center`, `lap`, `other` | Phân biệt nhìn đường, kiểm tra gương và nhìn lệch đường kéo dài. | Có nếu hướng đầu, mắt và bố cục cabin đủ rõ. |
| `hand` và `on_wheel` | `whose`, `side` và `yes`, `no`, `unknown` | Kiểm tra mức sẵn sàng nắm vô lăng trong tình huống cần tiếp quản. | Có nếu quan sát rõ tiếp xúc giữa tay và vô lăng. |
| `phone` và `state` | `held`, `mounted`, `lap` | Phân biệt điện thoại đang cầm với điện thoại đặt trên giá hoặc đùi. | Có nếu còn thấy cạnh, góc hoặc màn hình. |
| `person.seatbelt` | `worn_correct`, `worn_incorrect`, `not_worn`, `unknown` | Nhắc đeo dây hoặc chỉnh dây sai vị trí. | Có nếu thấy được đường dây qua vai và hông. |

## OMS

| Lớp hoặc thuộc tính | Giá trị | Để làm gì | Nhìn thấy trên IR-sim? |
|---|---|---|---|
| `person` | Box người lớn theo ghế | Nhận biết chỗ có người và kích hoạt chức năng theo ghế. | Có nếu nhận ra đầu hoặc thân. |
| `seat` | `rear_left`, `rear_middle`, `rear_right` | Gắn cảnh báo và thiết bị an toàn với đúng chỗ ngồi. | Có dựa vào vị trí tương đối và bố cục ghế. |
| `face` | Box mặt người lớn | Xác định vùng mặt góp phần phân biệt người với đồ vật ở ghế. | Có nếu góc mặt và độ sáng đủ để nhận ra. |
| `person.seatbelt` | `not_worn`, `unknown` trên SVIRO | Xác định trên ghế có người khi nào đủ căn cứ đánh giá dây. | Có khi thấy rõ vùng vai và thân. SVIRO thiếu ví dụ đeo dây. |
| `child_seat` | Box ghế trẻ em, `seat`, `occupied=no/unknown/yes` | Xác định ghế có thiết bị giữ trẻ để áp dụng chính sách an toàn theo ghế. | Có thể thấy thành bên, đệm và đế. |
| `infant_seat` | Box nôi trống, `seat`, `facing=rear/front` | Xác định ghế có nôi và hướng đặt cho logic an toàn. | Có khi thấy vỏ nôi, tay xách hoặc hướng mở của nôi. |
| `object` | `bag`, `box`, `cup`, `other` theo ghế | Phân biệt đồ để trên ghế với người, hạn chế cảnh báo nhầm. | Có khi đường bao và chi tiết như quai hoặc cạnh hộp còn thấy. |

## Hai câu hỏi cho người viết guideline

1. **D01.png** — Khi khó phân biệt mí mở hay khép do mờ nhưng vẫn định vị được mép mí, checker có cần chấp nhận `eye_left=unknown` cùng keypoint hiện rõ không? Bản hiện tại giữ `unknown` và ghi riêng cảnh báo để đối chiếu từng điểm.
2. **S03_ir.png** — Khi ảnh SVIRO có hình giống trẻ em trong nôi có tay xách, nên ghi nhận thiết bị đó thế nào khi schema `infant_seat` chưa có trường `occupied`? Bản này gán `child_seat` có `occupied=yes` cho ghế nhìn rõ bên trái ảnh và giữ nhãn cốc ở giữa.
