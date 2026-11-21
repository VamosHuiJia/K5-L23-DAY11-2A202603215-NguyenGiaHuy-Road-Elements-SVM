# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): Nguyễn Gia Huy        Người kiểm (học viên): Nguyễn Hải Đăng  
Ngày: 21/11/2026               Phiên bản guideline: Road v1.0  
File được kiểm (tên + `revision` trong manifest): `nguyengiahuy-front.zip` và `nguyengiahuy-fisheye.zip`, revision 1; đây là kết quả sau sửa.  
Số ảnh kiểm: 6 (+ 0 ảnh thêm, ghi riêng)   Số nhãn đã kiểm (shape + tag): 114 = 90 shape + 24 tag.  

Mẫu kiểm gồm 6 ảnh A04, A08, B02, B03, B04 và B06, được đối chiếu với bản cũ lưu cục bộ trong `../r1/`. Cột “Số lỗi” ghi số lỗi còn lại sau sửa: 0 lỗi trong mẫu kiểm. Danh sách bên dưới giữ lại 10 lỗi cũ đã sửa để ghi nhận quá trình chỉnh nhãn, không tính vào số lỗi hiện tại. Một nhãn có thể được kiểm ở nhiều mã lỗi. Chưa kiểm được độ lệch so với GT vì không có nhãn chuẩn.

## Tổng hợp theo mã
| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 24 | 0 | nặng |
| QC1-02 đủ L1, R1 | bỏ sót | 6 | 0 | nặng |
| QC1-03 position | sai thuộc tính / thừa | 10 | 0 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 10 | 0 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 10 | 0 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 10 | 0 | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 32 | 0 | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 23 | 0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 48 | 0 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 25 | 0 | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | 38 | 0 | chính |
| QC1-12 file | lỗi file | 2 | 0 | nhẹ / nặng |

## Danh sách lỗi (mỗi lỗi một dòng)
| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| --- | --- | --- | --- | --- | --- |
| 1 | QC1-05 | A04 | `lane#1@(64,552)` | chính | Hai nét của vạch vàng đôi được vẽ riêng nhưng cùng đặt L1, làm nhãn bị lặp. Đã giữ một polyline với kind=double. |
| 2 | QC1-05 | A04 | `lane#4@(1279,536)` | chính | Cặp vạch trắng đôi bên phải cũng bị vẽ thành hai nhãn R2. Đã bỏ nhãn trùng và giữ kind=double. |
| 3 | QC1-05 | A08 | `lane#23@(765,452)` | chính | Vạch đứt R1 bị tách thành ba polyline riêng. Đã nối lại thành một đường và đặt style=dashed. |
| 4 | QC1-11 | B02 | `traffic_light#2@(118,114)` | chính | Đèn phía trên bên trái nằm ở vùng rìa nhưng chưa bật edge_zone. Đã bật lại thuộc tính này. |
| 5 | QC1-11 | B02 | `traffic_light#3@(1075,74)` | chính | Đèn phía trên bên phải còn để edge_zone=false. Đã đổi sang true sau khi kiểm tra vị trí tâm hộp. |
| 6 | QC1-11 | B02 | `traffic_light#4@(1095,18)` | chính | Cụm đèn sát mép trên bên phải cũng chưa bật edge_zone. Đã kiểm tra và sửa thành true. |
| 7 | QC1-11 | B03 | `traffic_sign#4@(1129,359)` | chính | Biển bên phải nằm ở vùng rìa nhưng vẫn để edge_zone=false. Đã bật true theo quy tắc 80% bán kính ảnh. |
| 8 | QC1-11 | B04 | `traffic_light#0@(103,314)` | chính | Đèn phía trái ảnh chưa bật edge_zone dù tâm hộp nằm ở vùng rìa. Đã bật lại thuộc tính này. |
| 9 | QC1-11 | B04 | `traffic_sign#7@(1062,163)` | chính | Biển cấm bên phải chưa bật edge_zone. Đã kiểm tra tâm hộp và sửa thành true. |
| 10 | QC1-03 | B06 | `lane#3@(1178,813)` | nặng | Lane trên camera fisheye_left bị gán nhầm position=L1. Đã đổi thành other theo quy tắc camera hai bên. |

Số sau dấu # là thứ tự nhãn trong XML, tính từ 0. Tọa độ được ghi thêm để dễ tìm lại; số này có thể khác ID trên CVAT.

## Ca mơ hồ
| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| A05 — ngoài mẫu | Không có vạch sơn nhìn thấy để gán L1 bên trái và R1 bên phải; hai bên có xe đỗ và lề đường. | Người kiểm không tính là lỗi bỏ sót. Ghi chú để coach xác nhận ngoại lệ QC1-02. |
| A06 — ngoài mẫu | Không có vạch sơn R1 nhìn thấy ở phía phải nên không gán thêm lane. | Người kiểm không tính là lỗi bỏ sót. Ghi chú để coach xác nhận ngoại lệ QC1-02. |
| A14 — ảnh thêm, ngoài mẫu | Không có vạch sơn R1 nhìn thấy ở phía phải taxi; phần đường này bị che nên không vẽ theo phỏng đoán. | Người kiểm không tính là lỗi bỏ sót. Ghi chú để coach xác nhận ngoại lệ QC1-02. |
| B03, B04 | Với camera sau, L/R tính theo bên trái, phải trên ảnh hay theo hướng xe chạy? | Guideline chưa nêu rõ quy ước này, đang chờ coach xác nhận. |

## Quyết định
Lỗi nặng: 0 đã xác nhận còn lại trong mẫu   Lỗi chính: 0 / 114 nhãn = 0%   Lỗi nhẹ: 0   Ca chờ lead: 4  
Quyết định (Release / Hold / Rework): Hold  
Lý do (theo luật của phiếu): 10 lỗi cũ, gồm 1 lỗi nặng và 9 lỗi chính, đã được sửa; số lỗi còn lại trong mẫu kiểm là 0. Lint vẫn báo 4 cảnh báo QC1-02 ở A05 (L1, R1), A06 (R1) và A14 (R1). Người kiểm không tính các cảnh báo này là lỗi bỏ sót vì không có vạch sơn nhìn thấy để gán. Giữ Hold để chờ coach xác nhận ngoại lệ và quy ước L/R ở camera sau; đây không phải lỗi annotation đã được xác nhận.

Loại lỗi: bỏ sót = thiếu nhãn phải có; thừa = gán cái không phải đối tượng; sai phạm vi = hình lệch, sai chiều, dừng sai chỗ, tràn vùng. Ba loại này theo cách chia lỗi gán nhãn của ISO/IEC 5259-4 (mục 8.4.2); "sai thuộc tính" và "lỗi file" là khóa học thêm. Cách xếp mức: [thang mức lỗi](../docs/qc_severity_road_v1.0.md).
