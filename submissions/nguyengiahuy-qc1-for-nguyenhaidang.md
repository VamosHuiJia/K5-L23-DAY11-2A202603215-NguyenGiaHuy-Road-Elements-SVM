# Phiếu QC1 tổng hợp — Nguyễn Gia Huy kiểm Nguyễn Hải Đăng

**Kết quả hiện hành: Rework — 1 lỗi nặng, 12 lỗi chính / 264 nhãn = 4.55%, 1 lỗi nhẹ.**

File tổng hợp ba phiếu QC1 của **Nguyễn Gia Huy** cho **Nguyễn Hải Đăng**. Kết quả hiện hành lấy từ phiếu ngày **21/11/2026 lúc 01:04:31 +07**, trên bộ bàn giao revision 2. Hai vòng trước được giữ nguyên trong phụ lục để đối chiếu; số lỗi giữa các vòng không cộng dồn. Đây là tổng hợp hồ sơ đã lưu, không phải một lần kiểm nhãn mới.

## Lịch sử các vòng QC

| Vòng kiểm (21/11/2026, +07) | Nhãn đã kiểm | Lỗi nặng | Lỗi chính | Lỗi nhẹ | Tỉ lệ lỗi chính | Quyết định |
| --- | ---: | ---: | ---: | ---: | --- | --- |
| Lần đầu, 00:03 | 238 = 182 shape + 56 tag | 12 | 29 | 24 | 29/238 = 12.18% | Rework; đã được thay thế |
| Vòng 2, 00:25 | 262 = 182 shape + 80 tag | 8 | 25 | 1 | 25/262 = 9.54% | Rework; đã được thay thế |
| Hiện hành, 01:04:31 | 264 = 184 shape + 80 tag | 1 | 12 | 1 | 12/264 = 4.55% | **Rework** |

Số lỗi giảm do cả sửa nhãn, gộp lỗi cùng đối tượng, đính chính nhận định và thay đổi giả định áp dụng. Không suy ra rằng mọi lỗi không còn được tính đều đã được sửa trên CVAT.

## Đối chiếu các thay đổi chính

| Nhóm vấn đề | Diễn biến và cách xử lý trong kết quả hiện hành |
| --- | --- |
| 24 tag còn thiếu ở A01–A12 | Đã bổ sung; vẫn còn weather của A10 cần đổi thành rain. |
| Position trên camera bên B05/B07/B08 | Hiện không còn lỗi xác nhận thuộc QC1-03; B05/B07 đã được ghi nhận sửa từ vòng 2. |
| Position ở A02/A03/A08/A12 | Chấp nhận theo giả định học viên yêu cầu, chờ coach; không đồng nghĩa đã sửa hay được coach phê duyệt. Lỗi style/color ở các ảnh này vẫn được tính. |
| Biên làn A07 | Gộp lỗi xác định biên thành một lỗi nặng; vẫn thiếu R1 liền thực tế. Hai đoạn hiện tại được nhận diện là #3136/#3226; phiếu cũ dùng #3136/#3137. Không cộng lỗi của các ID qua nhiều vòng. |
| Điểm cuối R1 A01 | Rút lại yêu cầu kéo dài sau khi xem lại ảnh; giữ điểm cuối hiện có. |
| Phạm vi drivable A03/A12 và hình học lane B06 | Các nhận định ban đầu đã được rút lại do chưa đủ căn cứ hoặc do giải thích bổ sung của giảng viên. |
| Drivable né theo xe ở A07/A10/A11/B03/B05 | Sáu lỗi ở vòng 2 được loại khỏi số hiện hành theo giả định chấp nhận car cutout; chưa có xác nhận coach cho giả định này. |
| Vạch đôi và đoạn chuyển kiểu vạch | Chấp nhận hai polyline theo hai vệt sơn; không tự động coi cùng position là lỗi tách vạch. |
| Nhóm biển A03/A06 và cụm biển A10 | Không còn trong danh sách lỗi hiện hành; vẫn còn ONE WAY A10 #3202 cần mandatory. |
| edge_zone | B02 #3082/#3083 và B04 #3086 không còn lỗi hiện hành. B03 cần bật cho #3084 và tắt cho #3085. |
| Kiểm file | Hai vòng đầu dùng bản chụp API, chưa kiểm ZIP native. Kết quả hiện hành đã ghi nhận mở lại và đối chiếu hai ZIP native với 20 ảnh / 264 nhãn. |

## Phiếu hiện hành

Lô được kiểm (học viên): **Nguyễn Hải Đăng**. Người kiểm: **Nguyễn Gia Huy**.
Ngày: **2026-11-21 01:04:31 +07**. Guideline: **Road v1.0 + các giả định học viên yêu cầu**.
File được kiểm: `nguyenhaidang-front.zip`, `nguyenhaidang-fisheye.zip`; manifest `nguyenhaidang-manifest.json`, **revision 2**.
Số ảnh kiểm: **20 core, 0 extra**. Số nhãn đã kiểm: **264 = 184 shapes + 80 tags**.
Phạm vi CVAT: project #3; job/task #13 và #15. Task #14/#16 và mọi ảnh extra bị loại khỏi kiểm và export.

## Tổng hợp theo mã

| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera và tag ảnh | sai thuộc tính / bỏ sót | 80 | 1 | nhẹ (tag khác camera) |
| QC1-02 đủ L1, R1 khi thấy vạch | bỏ sót | 32 | 1 | nặng |
| QC1-03 position | sai thuộc tính / thừa | 47 | 0 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / chiều | 47 | 2 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / thuộc tính | 47 | 1 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 47 | 6 | chính |
| QC1-07 vùng lái, crosswalk, curb | sai phạm vi / bỏ sót / thừa | 76 | 0 | chính |
| QC1-08 đèn, màu | bỏ sót / phạm vi / thuộc tính | 28 | 0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính / cách tách biển | 61 | 1 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 33 | 0 | chính |
| QC1-11 fisheye / edge_zone | sai thuộc tính / phạm vi | 46 | 2 | chính |
| QC1-12 file | lỗi file | 2 | 0 | nhẹ / nặng |

QC1-02 gồm 32 vị trí biên được sàng lọc ở 16 ảnh front/rear; chỉ tính lỗi khi có vạch nhìn thấy. QC1-03: 47 lane, trong đó position của 16 lane ở A02/A03/A08/A12 được chấp nhận theo giả định. QC1-07 không tính car cutout. QC1-10 kiểm 33 box biển và quét cả 20 ảnh; kiểm đầy đủ nhóm label bị giới hạn bởi bảng kế hoạch chưa có. Số mục kiểm giữa các mã có thể trùng nhau.

## Danh sách lỗi (mỗi lỗi một dòng)

| # | Mã | Ảnh | Nhãn (label, id CVAT) | Mức | Mô tả và hướng sửa |
| ---: | --- | --- | --- | --- | --- |
| 1 | QC1-02 | A07 | lane #3136 / #3226; thiếu R1 liền thực tế | nặng | Hai polyline hiện tại bám vạch đứt ngoài cùng bên phải. Vạch trắng liền ngay bên phải xe sedan bạc, khoảng (772,563) đến (695,270), vẫn chưa có nhãn lane. Bổ sung R1 thực tế và gán vạch đứt phía ngoài là R2. Biên drivable không thay thế polyline lane; tính gộp một lỗi nặng về xác định biên. |
| 2 | QC1-04 | A04 | lane #3113 | chính | Polyline đi từ (604,323) đến (718,536), tức từ xa về gần. Đảo thứ tự điểm để đầu gần xe đứng trước. |
| 3 | QC1-04 | B03 | lane #3016 | chính | Polyline bắt đầu gần xe ở xa tại (677,285) và kết thúc gần camera hơn tại (785,361). Đảo thứ tự điểm. |
| 4 | QC1-05 | A07 | lane #3136 + #3226 | chính | Hai đoạn rời vẫn mô tả cùng một vạch đứt phía ngoài. Nối các đoạn và khoảng trống thành một polyline; không gộp các vệt sơn riêng biệt của vạch đôi. |
| 5 | QC1-06 | A02 | lane #3098 | chính | Vạch ngoài bên trái là các đoạn trắng đứt nhưng đang có style=solid. Đổi thành style=dashed. |
| 6 | QC1-06 | A02 | lane #3099 | chính | Vạch gần hơn bên trái là các đoạn trắng đứt nhưng đang có style=solid. Đổi thành style=dashed. |
| 7 | QC1-06 | A03 | lane #3104 | chính | Vệt sơn biên trái màu vàng nhưng đang có color=white. Đổi thành color=yellow. |
| 8 | QC1-06 | A03 | lane #3105 | chính | Biên phải gồm các đoạn trắng đứt nhưng đang có style=solid. Đổi thành style=dashed. |
| 9 | QC1-06 | A07 | lane #3136 + #3226 | chính | Vạch phía ngoài là vạch đứt nhưng cả hai đoạn hiện có style=solid. Đổi thành style=dashed; tính một lỗi thuộc tính cho cùng một vạch thực tế. |
| 10 | QC1-06 | A12 | lane #3213 | chính | Biên bên phải ở xa gồm các đoạn trắng đứt nhưng đang có style=solid. Đổi thành style=dashed. |
| 11 | QC1-09 | A10 | traffic_sign #3202 | chính | Biển mũi tên ONE WAY đang có group=information. Đổi thành group=mandatory. |
| 12 | QC1-11 | B03 | traffic_sign #3084 | chính | Đang có edge_zone=false. Tâm hộp (1144.2,379.4) cách tâm ảnh 514.7 px, vượt ngưỡng 0.8 × 640 = 512 px. Đặt edge_zone=true theo quy ước của bài lab. |
| 13 | QC1-01 | A10 | thẻ weather | nhẹ | Thẻ weather đã có nhưng đang lưu overcast. Theo Road v1.0, weather=rain áp dụng cả mặt đường ướt rõ do mưa như trong ảnh. Đặt weather=rain; đây là lỗi nhẹ, không liên quan camera. |
| 14 | QC1-11 | B03 | traffic_sign #3085 | chính | edge_zone đang được bật cho biển xanh ở giữa thay vì biển ngoài rìa #3084. Tâm hộp #3085 nằm trong bán kính 512 px: đặt #3085 là edge_zone=false và #3084 là true. |

## Ca mơ hồ

| Ảnh | Câu hỏi cho lead | Lời đáp / xử lý lần này |
| --- | --- | --- |
| A02/A03/A08/A12 | Position làn đang tranh luận. | Chấp nhận đúng theo yêu cầu học viên cho lần QC này; chưa có kết luận coach. Không tính lỗi position. |
| Các polygon drivable | Car cutout có được chấp nhận? | Chấp nhận đúng theo yêu cầu học viên. Không tính lỗi cutout; không ghi là coach đã xác nhận. |
| A05/A06/A07/A09/A10 | Miễn cảnh báo L1/R1 tại biên không có vạch sơn nhìn thấy? | Người kiểm không yêu cầu vẽ vạch không tồn tại; xác nhận ngoại lệ chính thức của coach chưa được cung cấp. Riêng A07 còn lỗi R1 nhìn thấy nhưng chưa được gán. |
| A06/B02 | Màu đèn người đi bộ trắng hoặc rất mờ trong taxonomy? | Chưa có quy ước bổ sung; không đoán màu và không tính lỗi nặng. |
| 20 ảnh core | Danh sách nhóm label bắt buộc cho từng ảnh theo slide Task 1/2? | Không có bảng slide đầy đủ trong repo; không tính lỗi bỏ sót nhóm dựa trên suy đoán. |

## Quyết định

**Lỗi nặng: 1. Lỗi chính: 12 / 264 = 4.55%. Lỗi nhẹ: 1. Ca chờ lead: 5 nhóm, đã xử lý bằng giả định hoặc không tính lỗi như bảng trên.**

**Quyết định: Rework.** Còn lỗi nặng A07 nằm ngoài các giả định được chấp nhận. Tỉ lệ lỗi chính dưới 5% không xóa điều kiện lỗi nặng. Không ghi Release hoặc coach phê duyệt khi chưa có xác nhận.

Job #13 và #15 đã có `state=completed`, `stage=annotation` trước khi kiểm. Trạng thái completed là trạng thái tiến độ, không đồng nghĩa Release QC. Không thay đổi nhãn, stage hay state trong lần hoàn tất hồ sơ này.

Hai ZIP native đã mở lại, đối chiếu toàn bộ 20 ảnh / 264 nhãn với API đã lưu và kiểm taxonomy. Không kèm ảnh. Raw lint còn **9 nặng / 18 chính / 22 nhẹ**, gồm nhiều cảnh báo theo khả năng nhìn thấy vạch, double markings, thuộc tính position được giả định, box nhỏ và điểm lặp; chúng được giữ nguyên trong manifest và [bảng đối chiếu](evidence/lint-reconciliation.csv). Không đổi raw lint thành 0.

Ảnh không có lỗi QC đã xác nhận trong phạm vi/giả định: A01, A05, A06, A08, A09, A11, B01, B02, B04, B05, B06, B07, B08. “Không có lỗi xác nhận” không phải so khớp GT hoặc quyết định coach cho ca tranh luận.

Bằng chứng: [kiểm export](evidence/export-checks.json), [danh sách lỗi có cấu trúc](evidence/final-findings.json), [raw lint](evidence/lint-raw.txt). Hai vòng kiểm trước được lưu đầy đủ trong phụ lục của file này; kết quả hiện hành thay thế các số lỗi cũ trong phạm vi giả định mới.


## Phụ lục — nguyên văn hai vòng kiểm trước

Các bảng lỗi, ghi chú theo ảnh và câu hỏi trong phụ lục phản ánh thời điểm kiểm cũ. Những chỉ dẫn đã được rút lại hoặc được thay thế không áp dụng cho kết quả hiện hành. Các liên kết bằng chứng đã được chỉnh theo vị trí của file tổng hợp.


<details>
<summary>Vòng kiểm đầu — 00:03 +07; 12 nặng, 29 chính, 24 nhẹ</summary>

### Phiếu QC 1 — Road v1.0

**Decision: Rework.** Correct lane positions first, then repair the drivable polygons and the listed attribute/geometry errors.

Learner: Nguyen Hai Dang. Reviewer: Nguyễn Gia Huy. Reviewed: 2026-11-21 00:03 +07.

Scope: local Docker CVAT project `d11-road-nguyenhaidang` (#3); `front` task/job #13 (A01–A12), `fisheye` task/job #15 (B01–B08). All 20 core images reviewed. Both `*-extra` tasks (#14 and #16) and their images were excluded. No annotations, job stages, or issues were changed.

Labels inspected: **238 existing annotations = 182 shapes + 56 tags**. The 24 absent tag instances are findings, not existing annotations in this denominator. Each of 80 expected tag slots was checked. The same annotation may receive findings under different rules for distinct defects; the numerator below counts findings as on QC1.

All 20 local source images matched SHA-256 hashes of CVAT original frames. Saved annotation update times: front `2026-11-20T16:43:20.003630Z`; fisheye `2026-11-20T15:00:12.528603Z`. Both jobs had state `completed` and stage `annotation`; this review did not change their state.

#### Tổng hợp theo mã

| Code | Check | Items checked | Confirmed findings | Severity |
| --- | --- | --- | ---: | --- |
| QC1-01 | camera and image tags | 80 expected tag slots | 24 | 24 minor |
| QC1-02 | visible L1 and R1 | 32 front/rear boundary slots screened | 1 | 1 critical |
| QC1-03 | position / false lanes | 47 lanes | 11 | 11 critical |
| QC1-04 | paint center, direction and stops | 47 lanes | 3 | 3 major |
| QC1-05 | dashes and occlusion | 47 lanes | 1 | 1 major |
| QC1-06 | style, color and kind | 47 lanes | 7 | 7 major |
| QC1-07 | drivable, crossing and curb geometry | 76 shapes (34 drivable + 16 crosswalk + 26 curb) | 8 | 8 major |
| QC1-08 | lights, color and box fit | 28 light boxes | 0 | No confirmed finding; see scope/lead notes |
| QC1-09 | facing, type, group and separate plates | 59 light/sign boxes | 5 | 5 major |
| QC1-10 | sign presence and printed/reflected signs | 31 sign boxes + 20 image sweeps | 0 | No confirmed finding; see scope/lead notes |
| QC1-11 | fisheye geometry and edge_zone | 46 fisheye shapes across 8 images | 5 | 5 major |
| QC1-12 | file and serialization | 2 API snapshots; native ZIPs pending | 0 | No confirmed finding; see scope/lead notes |

#### Danh sách lỗi

Object numbers below are persistent CVAT shape IDs from the saved API snapshot. Frame links open the original job; each image also has a local annotation overlay.

| # | Code | Image | Label and ID | Level | Finding and correction |
| ---: | --- | --- | --- | --- | --- |
| 1 | QC1-01 | [A01](http://localhost:8080/tasks/13/jobs/13?frame=0) | tag:timeofday | minor | Missing timeofday tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 2 | QC1-01 | [A01](http://localhost:8080/tasks/13/jobs/13?frame=0) | tag:weather | minor | Missing weather tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 3 | QC1-01 | [A02](http://localhost:8080/tasks/13/jobs/13?frame=1) | tag:timeofday | minor | Missing timeofday tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 4 | QC1-01 | [A02](http://localhost:8080/tasks/13/jobs/13?frame=1) | tag:weather | minor | Missing weather tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 5 | QC1-01 | [A03](http://localhost:8080/tasks/13/jobs/13?frame=2) | tag:timeofday | minor | Missing timeofday tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 6 | QC1-01 | [A03](http://localhost:8080/tasks/13/jobs/13?frame=2) | tag:weather | minor | Missing weather tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 7 | QC1-01 | [A04](http://localhost:8080/tasks/13/jobs/13?frame=3) | tag:timeofday | minor | Missing timeofday tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 8 | QC1-01 | [A04](http://localhost:8080/tasks/13/jobs/13?frame=3) | tag:weather | minor | Missing weather tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 9 | QC1-01 | [A05](http://localhost:8080/tasks/13/jobs/13?frame=4) | tag:timeofday | minor | Missing timeofday tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 10 | QC1-01 | [A05](http://localhost:8080/tasks/13/jobs/13?frame=4) | tag:weather | minor | Missing weather tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 11 | QC1-01 | [A06](http://localhost:8080/tasks/13/jobs/13?frame=5) | tag:timeofday | minor | Missing timeofday tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 12 | QC1-01 | [A06](http://localhost:8080/tasks/13/jobs/13?frame=5) | tag:weather | minor | Missing weather tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 13 | QC1-01 | [A07](http://localhost:8080/tasks/13/jobs/13?frame=6) | tag:timeofday | minor | Missing timeofday tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 14 | QC1-01 | [A07](http://localhost:8080/tasks/13/jobs/13?frame=6) | tag:weather | minor | Missing weather tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 15 | QC1-01 | [A08](http://localhost:8080/tasks/13/jobs/13?frame=7) | tag:timeofday | minor | Missing timeofday tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 16 | QC1-01 | [A08](http://localhost:8080/tasks/13/jobs/13?frame=7) | tag:weather | minor | Missing weather tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 17 | QC1-01 | [A09](http://localhost:8080/tasks/13/jobs/13?frame=8) | tag:timeofday | minor | Missing timeofday tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 18 | QC1-01 | [A09](http://localhost:8080/tasks/13/jobs/13?frame=8) | tag:weather | minor | Missing weather tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 19 | QC1-01 | [A10](http://localhost:8080/tasks/13/jobs/13?frame=9) | tag:timeofday | minor | Missing timeofday tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 20 | QC1-01 | [A10](http://localhost:8080/tasks/13/jobs/13?frame=9) | tag:weather | minor | Missing weather tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 21 | QC1-01 | [A11](http://localhost:8080/tasks/13/jobs/13?frame=10) | tag:timeofday | minor | Missing timeofday tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 22 | QC1-01 | [A11](http://localhost:8080/tasks/13/jobs/13?frame=10) | tag:weather | minor | Missing weather tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 23 | QC1-01 | [A12](http://localhost:8080/tasks/13/jobs/13?frame=11) | tag:timeofday | minor | Missing timeofday tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 24 | QC1-01 | [A12](http://localhost:8080/tasks/13/jobs/13?frame=11) | tag:weather | minor | Missing weather tag. Add one value based on this image; A10 has visibly wet pavement and needs weather=rain. |
| 25 | QC1-03 | [A02](http://localhost:8080/tasks/13/jobs/13?frame=1) | lane #3098 | critical | The outer left marking is labeled L1, duplicating the nearer left boundary #3099. Use L2 for this marking. |
| 26 | QC1-03 | [A02](http://localhost:8080/tasks/13/jobs/13?frame=1) | lane #3100 | critical | The right boundary of the current lane is labeled L1. Set position=R1. |
| 27 | QC1-03 | [A03](http://localhost:8080/tasks/13/jobs/13?frame=2) | lane #3105 | critical | The dashed boundary to the right of the current lane is labeled L1. Set position=R1. |
| 28 | QC1-02 | [A07](http://localhost:8080/tasks/13/jobs/13?frame=6) | lane R1, missing | critical | The prominent solid white marking from about (772,563) toward (695,270), immediately right of the silver sedan, has no lane polyline. Add R1 along its paint center; the green polygon edge does not substitute for a lane label. |
| 29 | QC1-03 | [A07](http://localhost:8080/tasks/13/jobs/13?frame=6) | lane #3136 | critical | This marking lies to the right of the current lane but is labeled L1. After adding the actual R1, assign the adjacent outer boundary R2 and reconcile the two fragments. |
| 30 | QC1-03 | [A07](http://localhost:8080/tasks/13/jobs/13?frame=6) | lane #3137 | critical | This marking lies to the right of the current lane but is labeled L1. After adding the actual R1, assign the adjacent outer boundary R2 and reconcile the two fragments. |
| 31 | QC1-03 | [A08](http://localhost:8080/tasks/13/jobs/13?frame=7) | lane #3142 | critical | This short distant segment lies on the continuation of the right boundary #3140, but is labeled L1. Correct the position to R1; ask the lead how to represent the local style transition. |
| 32 | QC1-03 | [A12](http://localhost:8080/tasks/13/jobs/13?frame=11) | lane #3213 | critical | The far-side boundary on the right of the current lane is labeled L1. Set position=R1. |
| 33 | QC1-03 | [A12](http://localhost:8080/tasks/13/jobs/13?frame=11) | lane #3215 | critical | The outer left boundary is labeled L1, duplicating the nearer left boundary #3214. Assign its position relative to the current lane (L2 for the next boundary outside #3214). |
| 34 | QC1-03 | [B05](http://localhost:8080/tasks/15/jobs/15?frame=4) | lane #3035 | critical | Side-camera lane has position=L1. Road v1.0 requires position=other on every lane in fisheye_left/fisheye_right. |
| 35 | QC1-03 | [B07](http://localhost:8080/tasks/15/jobs/15?frame=6) | lane #3070 | critical | Side-camera lane has position=R1. Road v1.0 requires position=other on every lane in fisheye_left/fisheye_right. |
| 36 | QC1-03 | [B08](http://localhost:8080/tasks/15/jobs/15?frame=7) | lane #3078 | critical | Side-camera lane has position=R1. Road v1.0 requires position=other on every lane in fisheye_left/fisheye_right. |
| 37 | QC1-04 | [A01](http://localhost:8080/tasks/13/jobs/13?frame=0) | lane #3089 | major | The near endpoint is (654,680), while the same visible dashed marking continues down toward (710,720). Extend to the nearest visible paint instead of stopping roughly 40 image rows early. |
| 38 | QC1-04 | [A04](http://localhost:8080/tasks/13/jobs/13?frame=3) | lane #3113 | major | Polyline runs from (604,323) to (718,536), far to near. Reverse its point order so the near endpoint comes first. |
| 39 | QC1-04 | [B03](http://localhost:8080/tasks/15/jobs/15?frame=2) | lane #3016 | major | Polyline starts near the distant car at (677,285) and ends nearer the camera at (785,361). Reverse the point order. |
| 40 | QC1-05 | [A07](http://localhost:8080/tasks/13/jobs/13?frame=6) | lane #3136 + #3137 | major | Two separated polylines describe fragments of the same right-side dashed marking. Reconcile them as one polyline across the gaps; retain the correctly assigned position. |
| 41 | QC1-06 | [A02](http://localhost:8080/tasks/13/jobs/13?frame=1) | lane #3098 | major | The outer-left marking has separated white dashes but style=solid. Use dashed. |
| 42 | QC1-06 | [A02](http://localhost:8080/tasks/13/jobs/13?frame=1) | lane #3099 | major | The nearer-left marking has separated white dashes but style=solid. Use dashed. |
| 43 | QC1-06 | [A03](http://localhost:8080/tasks/13/jobs/13?frame=2) | lane #3104 | major | The left boundary paint is yellow but color=white. Use yellow. |
| 44 | QC1-06 | [A03](http://localhost:8080/tasks/13/jobs/13?frame=2) | lane #3105 | major | The right boundary consists of separated white dashes but style=solid. Use dashed. |
| 45 | QC1-06 | [A07](http://localhost:8080/tasks/13/jobs/13?frame=6) | lane #3136 | major | This fragment belongs to a dashed marking but style=solid. Use dashed when reconciling the marking. |
| 46 | QC1-06 | [A07](http://localhost:8080/tasks/13/jobs/13?frame=6) | lane #3137 | major | This right-side marking is visibly dashed but style=solid. Use dashed. |
| 47 | QC1-06 | [A12](http://localhost:8080/tasks/13/jobs/13?frame=11) | lane #3213 | major | The distant right boundary has separated white dashes but style=solid. Use dashed. |
| 48 | QC1-07 | [A03](http://localhost:8080/tasks/13/jobs/13?frame=2) | drivable #3106 | major | The direct region expands rightward beyond the dashed current-lane boundary toward the parked-car strip. Restrict direct to the current lane and keep the neighboring same-direction region separate. |
| 49 | QC1-07 | [A07](http://localhost:8080/tasks/13/jobs/13?frame=6) | drivable #3138 | major | The direct polygon traces a rectangular cutout around the silver sedan, approximately x447–674, y352–414. Include the road footprint as if the other car were absent; do not trace its silhouette. |
| 50 | QC1-07 | [A10](http://localhost:8080/tasks/13/jobs/13?frame=9) | drivable #3193 | major | The polygon cuts around the Subaru and right-side cars and combines current and adjacent lanes into direct. Draw the current lane as if traffic were absent; use a separate alternative polygon for the adjacent same-direction lane. |
| 51 | QC1-07 | [A11](http://localhost:8080/tasks/13/jobs/13?frame=10) | drivable #3208 | major | The alternative polygon steps down around the visible SUVs, including the SUV near x671–797. Include the drivable road footprint through vehicle occlusions instead of excluding each car. |
| 52 | QC1-07 | [A12](http://localhost:8080/tasks/13/jobs/13?frame=11) | drivable #3219 | major | The right-side alternative region follows the row of curbside parked vehicles. Exclude the parking strip unless the lead confirms an actual same-direction travel lane here; parked space is not alternative simply because it is paved. |
| 53 | QC1-07 | [B03](http://localhost:8080/tasks/15/jobs/15?frame=2) | drivable #3019 | major | The direct polygon follows the lower outline of the silver car near the distant center (around x600–675, y280–306). Continue the road region as if the car were absent. |
| 54 | QC1-07 | [B03](http://localhost:8080/tasks/15/jobs/15?frame=2) | drivable #3022 | major | The alternative polygon bends around the black car near the far end. Include the road footprint through the car rather than making a silhouette cutout. |
| 55 | QC1-07 | [B05](http://localhost:8080/tasks/15/jobs/15?frame=4) | drivable #3032 | major | The drivable polygon bends around the black car at upper left. A moving/standing car is not a permanent road boundary; annotate the road if empty while retaining the true curb and own-vehicle exclusions. |
| 56 | QC1-09 | [A03](http://localhost:8080/tasks/13/jobs/13?frame=2) | traffic_sign #3222 | major | Orange diamond warning sign is grouped prohibitory. Use group=warning. |
| 57 | QC1-09 | [A06](http://localhost:8080/tasks/13/jobs/13?frame=5) | traffic_sign #3127 | major | Orange diamond construction warning sign is grouped prohibitory. Use group=warning. |
| 58 | QC1-09 | [A06](http://localhost:8080/tasks/13/jobs/13?frame=5) | traffic_sign #3128 | major | ONE WAY sign is grouped information. Road v1.0 explicitly assigns One Way to group=mandatory. |
| 59 | QC1-09 | [A10](http://localhost:8080/tasks/13/jobs/13?frame=9) | traffic_sign #3202 | major | The ONE WAY arrow plate is grouped information. Use group=mandatory. |
| 60 | QC1-09 | [A10](http://localhost:8080/tasks/13/jobs/13?frame=9) | traffic_sign #3196 | major | One tall box encloses the stack of separate parking/no-standing plates. Give each physical plate its own tight rectangle instead of enclosing the full stack in one box. |
| 61 | QC1-11 | [B02](http://localhost:8080/tasks/15/jobs/15?frame=1) | traffic_light #3082 | major | edge_zone=false, but box center (134.2,165.0) is 597.4px from image center, outside the lab radius threshold 0.8 × 640 = 512px. Set edge_zone=true under the repo convention. |
| 62 | QC1-11 | [B02](http://localhost:8080/tasks/15/jobs/15?frame=1) | traffic_light #3083 | major | edge_zone=false, but box center (1109.2,119.6) is 593.5px from image center, outside the lab radius threshold 0.8 × 640 = 512px. Set edge_zone=true under the repo convention. |
| 63 | QC1-11 | [B03](http://localhost:8080/tasks/15/jobs/15?frame=2) | traffic_sign #3084 | major | edge_zone=false, but box center (1144.2,379.4) is 514.7px from image center, outside the lab radius threshold 0.8 × 640 = 512px. Set edge_zone=true under the repo convention. |
| 64 | QC1-11 | [B04](http://localhost:8080/tasks/15/jobs/15?frame=3) | traffic_sign #3086 | major | edge_zone=false, but box center (1085.9,201.5) is 527.3px from image center, outside the lab radius threshold 0.8 × 640 = 512px. Set edge_zone=true under the repo convention. |
| 65 | QC1-11 | [B06](http://localhost:8080/tasks/15/jobs/15?frame=5) | lane #3066 | major | The long final straight segment from (345,254) to (910,444) cuts across the crosswalk region instead of following a visible curved longitudinal paint line. Trace the actual marking with appropriate vertices, or remove it if it is only the crossing boundary; do not label crossing stripes as lane. |

#### Per image review

| Image | Shapes + tags checked | Confirmed findings | Review note | Evidence |
| --- | ---: | --- | --- | --- |
| A01 | 12 | 1 major, 2 minor | Overall lane positions and the information-sign group look consistent; extend the near R1 endpoint. | [Overlay](../../reviews/core20/overlays/A01.jpg) |
| A02 | 10 | 2 critical, 2 major, 2 minor | Fix duplicated L1 positions and dashed styles. One polyline per dashed boundary is already used. | [Overlay](../../reviews/core20/overlays/A02.jpg) |
| A03 | 12 | 1 critical, 4 major, 2 minor | Fix right-boundary position, yellow/dashed attributes, direct extent and the orange warning-sign group. | [Overlay](../../reviews/core20/overlays/A03.jpg) |
| A04 | 12 | 1 major, 2 minor | Reverse R1. Resolve the representation of double markings and style changes with the lead. | [Overlay](../../reviews/core20/overlays/A04.jpg) |
| A05 | 4 | 2 minor | No confirmed shape error. Missing image tags remain; no painted lane is visible, so do not fabricate L1/R1. | [Overlay](../../reviews/core20/overlays/A05.jpg) |
| A06 | 19 | 2 major, 2 minor | Fix the warning/ONE WAY groups. Separate crosswalk regions interrupted by scene geometry were not automatically treated as split-object errors. | [Overlay](../../reviews/core20/overlays/A06.jpg) |
| A07 | 6 | 3 critical, 4 major, 2 minor | Add the actual solid R1; repair right-side positions, dashed fragments and the car cutout in direct. | [Overlay](../../reviews/core20/overlays/A07.jpg) |
| A08 | 39 | 1 critical, 2 minor | Fix the distant right segment mislabeled L1. Many close light/sign objects were annotated; color ambiguities remain separate. | [Overlay](../../reviews/core20/overlays/A08.jpg) |
| A09 | 8 | 2 minor | No confirmed shape error. The direct region is to the right of the nearest dashed divider, consistent with the ego lane. Missing image tags remain; no missing-R1 error was charged where no right painted boundary is clear. | [Overlay](../../reviews/core20/overlays/A09.jpg) |
| A10 | 16 | 3 major, 2 minor | Remove car silhouette cutouts; divide travel-lane areas and split the stacked sign plates. | [Overlay](../../reviews/core20/overlays/A10.jpg) |
| A11 | 11 | 1 major, 2 minor | Keep the correct green vehicle lights; repair the alternative polygon around the SUVs. | [Overlay](../../reviews/core20/overlays/A11.jpg) |
| A12 | 11 | 2 critical, 2 major, 2 minor | Fix lane positions/style and exclude the curbside parking strip from alternative. | [Overlay](../../reviews/core20/overlays/A12.jpg) |
| B01 | 8 | 0 | No confirmed semantic or visible geometry error. All four tags are present; crossing and own-vehicle exclusions look consistent. Lint duplicate vertices are optional cleanup. | [Overlay](../../reviews/core20/overlays/B01.jpg) |
| B02 | 11 | 2 major | Both peripheral lights need edge_zone; ask the lead about faint pedestrian color and the far alternative patch. | [Overlay](../../reviews/core20/overlays/B02.jpg) |
| B03 | 14 | 4 major | Reverse #3016, correct the outer sign edge_zone and remove road-area car cutouts. | [Overlay](../../reviews/core20/overlays/B03.jpg) |
| B04 | 11 | 1 major | Crosswalk and own-vehicle exclusion look consistent; the outer no-entry sign needs edge_zone. | [Overlay](../../reviews/core20/overlays/B04.jpg) |
| B05 | 9 | 1 critical, 1 major | Use other on the side-camera lane and remove the drivable cutout around the other car. The crossing was inspected separately from the drivable overlay and was not found missing. | [Overlay](../../reviews/core20/overlays/B05.jpg) |
| B06 | 7 | 1 major | The side-camera position=other is correct; the long straight lane segment needs a geometry/identity correction. Missing drivable depends on the coach plan. | [Overlay](../../reviews/core20/overlays/B06.jpg) |
| B07 | 11 | 1 critical | Use other on #3070. Confirm side-view drivable extent; the three crossing polygons correspond to distinct visible crossing regions. | [Overlay](../../reviews/core20/overlays/B07.jpg) |
| B08 | 7 | 1 critical | Use other on #3078. Confirm side-view drivable extent; the crossing was inspected in isolation and was not found missing. | [Overlay](../../reviews/core20/overlays/B08.jpg) |

#### Ca mơ hồ

| Image | Question for lead | Status |
| --- | --- | --- |
| All images | The coach Task 1/2 per-image label plan is absent. Confirm required groups before charging missing signs/lights/curbs/drivable. A07, A09 and A12 visibly contain unboxed lights/signs, but their required-group omissions are not included in the counts. | Pending; excluded from confirmed counts |
| A05, A06, A09, A10, B01, B02, B04 | Lint flags missing L1/R1 in some scenes with no visible painted boundary or a hidden boundary. Do not invent paint. Ask the coach to confirm applicable visibility exceptions. A07 has a plainly visible missing R1 and is already counted. | Pending; excluded from confirmed counts |
| A04, A08, A11 | Confirm how the lead wants double markings and solid/dashed transitions represented. Multiple polylines at one position do not by themselves prove an error. No duplicate/split penalty was added for these cases. | Pending; excluded from confirmed counts |
| A06, B02 | Pedestrian signals include a white walk symbol (#3177) and a faint green-looking figure (#3083). Confirm color mapping and whether B02 off is correct; white is not a Road v1.0 color option. No unverified wrong-color critical was counted. | Pending; excluded from confirmed counts |
| B02 | The distant alternative patch #3020 overlaps or nearly overlaps the upper direct region. Confirm the intended travel-lane division at the junction. | Pending; excluded from confirmed counts |
| B07, B08 | Drivable regions #3076 and #3080 cover only parts of the crossing road. Confirm the intended direct/alternative extent for these side views and check the near boundary against the own vehicle; these uncertain area findings are not counted. | Pending; excluded from confirmed counts |
| B03, B05, B07, B08 | Few-point fisheye curves and unusual curb/lane traces need a final vertex check at full zoom. A low vertex count alone was not scored as a >5px deviation. | Pending; excluded from confirmed counts |
| Delivery | Native CVAT for images 1.1 ZIP exports and their manifest revision were not supplied for this live-task review. Test both actual delivery ZIPs before release. The local reconstructed XML files are review snapshots, not native delivery exports. | Pending; excluded from confirmed counts |

#### Quyết định

Critical: **12**. Major: **29 / 238 = 12.18%**. Minor: **24**.

**Rework** under Road v1.0: at least one critical finding requires rework; the confirmed major-finding rate also exceeds 5%. Lead questions do not change this decision, so Hold is not the appropriate overall result.

Repair order: correct positions and the missing A07 R1; repair drivable semantics; fix styles/direction/sign groups/edge_zone; add the 24 front-image tags; resolve the lead questions; export and reopen both native core delivery ZIPs for QC1-12.

#### Evidence and rules

- [Saved CVAT API snapshot](../../reviews/core20/snapshot.json), [decoded objects](../../reviews/core20/review-data.json), [original-frame SHA-256 checks](../../reviews/core20/frame-hashes.json), and [raw lint suggestions](../../reviews/core20/lint.txt).
- [Front review XML](../../reviews/core20/front-snapshot.xml) and [fisheye review XML](../../reviews/core20/fisheye-snapshot.xml) were reconstructed from the API snapshot for local linting. They are not native CVAT delivery exports and have no delivery revision.
- The linter produced 78 suggestions, including optional small boxes, duplicate vertices and visibility-dependent warnings. This form counts only adjudicated findings; those 78 suggestions are not an error total.
- [Road v1.0 guideline](../../../docs/guideline_road_v1.0.md), [severity rules](../../../docs/qc_severity_road_v1.0.md), [QC1 form](../../../templates/qc1_form.md). No coach GT or numeric grade was used.

</details>


<details>
<summary>Vòng kiểm thứ hai — 00:25 +07; 8 nặng, 25 chính, 1 nhẹ</summary>

### Phiếu QC vòng 2 sau khi sửa bài — Road v1.0

**Quyết định: Cần sửa (Rework).** Các tác vụ bắt buộc đã lưu còn **8 lỗi nặng, 25 lỗi chính và 1 lỗi nhẹ**. Tỉ lệ lỗi chính: **25/262 = 9.54%**. Những lỗi gán làn còn lại đủ để đưa ra quyết định này, không phụ thuộc vào các lỗi vùng lái.

Học viên: Nguyễn Hải Đăng. Người kiểm: Nguyễn Gia Huy. Thời điểm kiểm: 2026-11-21 00:25 +07.

Phạm vi: dự án #3 trên CVAT chạy bằng Docker trên máy; tác vụ/công việc front #13 (A01–A12) và fisheye #15 (B01–B08). Đã kiểm toàn bộ 20 ảnh bắt buộc; loại tác vụ #14/#16 và mọi ảnh làm thêm. Không thay đổi nhãn hoặc trạng thái công việc.

#### Quy tắc áp dụng trong lần kiểm này

Lần kiểm này áp dụng giải thích bổ sung của giảng viên do học viên cung cấp: vùng drivable không gồm làn ngược chiều, vùng dừng khẩn cấp và nơi xe không thể đi. Vùng alternative gồm các làn khác và đường nhánh mà xe có thể chuyển sang; mặt đường xe có thể tiếp cận, không có vạch kẻ, được tính là direct. Vạch đôi cần hai đường gấp khúc, mỗi đường bám một vệt sơn; chấp nhận cặp đường có cùng thuộc tính vị trí.

Quy tắc riêng của Road v1.0 “không khoét lỗ quanh xe khác” vẫn được áp dụng trong vòng kiểm này: vẽ phần mặt đường như khi không có xe khác. Học viên xác nhận giảng viên chưa hướng dẫn ngược lại và các nhãn minh họa có thể phủ qua xe. Đa giác phủ phần đường bên dưới xe khác được chấp nhận; biên đa giác né theo hình dáng xe là lỗi được giữ trong danh sách bên dưới.

#### Các mục đã sửa và điều chỉnh nhận định trước

- Đã bổ sung đủ 24 thẻ còn thiếu của ảnh camera trước. Mỗi ảnh bắt buộc hiện có đúng bốn thẻ, với camera và source đúng.
- Nhãn lane #3035 ở B05 và #3070 ở B07 đã có position=other. Thứ tự điểm của đường B05 cũng đã được đảo.
- A07 #3136/#3137 đã được đặt là R1 nhưng đang bám vạch phía ngoài; vẫn thiếu đường gán nhãn cho biên liền thực tế ngay cạnh xe sedan màu bạc. A07 #3137 còn bị đảo thành thứ tự từ xa về gần.
- **Đính chính lần kiểm đầu:** điểm cuối gần xe của R1 ở A01 được chấp nhận. Không kéo dài vào khoảng trống hoặc về phía hình phản chiếu trên kính chắn gió.
- Rút lại nhận định trước về phạm vi direct ở A03 và việc xác định dải đỗ xe ở A12. Chưa có đủ căn cứ chắc chắn cho hai nhận định đó theo giải thích bổ sung của giảng viên.
- Rút lại lỗi hình học trước đây ở B06: chỉ riêng một đoạn dài chưa chứng minh được độ lệch trên 5 px. Không tính lỗi chỉ vì đường trên ảnh mắt cá có ít đỉnh.
- Chấp nhận cặp đường của vạch đôi ở A04, A09 và A11. Việc có cùng thuộc tính vị trí không phải lỗi tách vạch đứt. Các đoạn chuyển tiếp liền/đứt ở A04/A08 không bị tính là đường trùng.

Bản dữ liệu dùng để đối chiếu có 182 đối tượng hình học và 80 thẻ ảnh, so với 182 đối tượng hình học và 56 thẻ ở bản đầu. Chỉ bốn đối tượng hình học hiện có đã thay đổi: A07 #3136, A07 #3137, B05 #3035 và B07 #3070. Các giá trị còn lỗi bên dưới được lấy từ bản chụp dữ liệu API đã lưu của vòng kiểm này.

#### Danh sách lỗi được xác nhận trong vòng kiểm này

| # | Mã | Ảnh | Đối tượng | Mức | Mô tả và hướng sửa |
| ---: | --- | --- | --- | --- | --- |
| 1 | QC1-03 | [A02](http://localhost:8080/tasks/13/jobs/13?frame=1) | lane #3098 | nặng | Vạch ngoài bên trái đang có L1, trùng với biên trái gần hơn #3099. Đặt vạch này là L2. |
| 2 | QC1-03 | [A02](http://localhost:8080/tasks/13/jobs/13?frame=1) | lane #3100 | nặng | Biên phải của làn đang đi được gán L1. Đặt position=R1. |
| 3 | QC1-03 | [A03](http://localhost:8080/tasks/13/jobs/13?frame=2) | lane #3105 | nặng | Biên vạch đứt bên phải làn đang đi được gán L1. Đặt position=R1. |
| 4 | QC1-02 | [A07](http://localhost:8080/tasks/13/jobs/13?frame=6) | thiếu R1 thực; lane #3136 / #3137 ở biên ngoài | nặng | Vạch trắng liền lớn ngay bên phải xe sedan màu bạc, khoảng từ (772,563) đến (695,270), vẫn chưa có đường gấp khúc lane. Hai đoạn vạch đứt phía ngoài #3136/#3137 đã được đổi thành R1 nhưng nằm cách thêm một biên về bên phải. Bổ sung vạch liền R1 thực tế và gán vạch đứt phía ngoài là R2. Tính gộp một lỗi về xác định biên, không tính riêng hai đoạn thành hai lỗi nặng. |
| 5 | QC1-03 | [A08](http://localhost:8080/tasks/13/jobs/13?frame=7) | lane #3142 | nặng | Đoạn ngắn ở xa này nối tiếp biên phải #3140 nhưng đang có L1. Đổi vị trí thành R1; hỏi người phụ trách cách biểu diễn đoạn chuyển kiểu vạch tại đây. |
| 6 | QC1-03 | [A12](http://localhost:8080/tasks/13/jobs/13?frame=11) | lane #3213 | nặng | Biên bên phải làn đang đi ở phía bên kia giao lộ đang có L1. Đặt position=R1. |
| 7 | QC1-03 | [A12](http://localhost:8080/tasks/13/jobs/13?frame=11) | lane #3215 | nặng | Biên ngoài bên trái đang có L1, trùng với biên trái gần hơn #3214. Gán vị trí theo làn đang đi: L2 cho biên kế tiếp nằm ngoài #3214. |
| 8 | QC1-03 | [B08](http://localhost:8080/tasks/15/jobs/15?frame=7) | lane #3078 | nặng | Làn trên ảnh camera bên đang có position=R1. Road v1.0 yêu cầu position=other cho mọi lane ở fisheye_left/fisheye_right. |
| 9 | QC1-04 | [A04](http://localhost:8080/tasks/13/jobs/13?frame=3) | lane #3113 | chính | Đường gấp khúc đi từ (604,323) đến (718,536), tức từ xa về gần. Đảo thứ tự điểm để đầu gần xe đứng trước. |
| 10 | QC1-04 | [B03](http://localhost:8080/tasks/15/jobs/15?frame=2) | lane #3016 | chính | Đường gấp khúc bắt đầu gần xe ở xa tại (677,285), rồi kết thúc gần camera hơn tại (785,361). Đảo thứ tự điểm. |
| 11 | QC1-05 | [A07](http://localhost:8080/tasks/13/jobs/13?frame=6) | lane #3136 + #3137 | chính | Hai đường gấp khúc rời nhau mô tả các đoạn của cùng một vạch đứt bên phải. Nối thành một đường qua các khoảng trống; giữ thuộc tính vị trí đã xác định đúng. |
| 12 | QC1-06 | [A02](http://localhost:8080/tasks/13/jobs/13?frame=1) | lane #3098 | chính | Vạch ngoài bên trái gồm các đoạn trắng đứt nhưng đang có style=solid. Đổi thành style=dashed. |
| 13 | QC1-06 | [A02](http://localhost:8080/tasks/13/jobs/13?frame=1) | lane #3099 | chính | Vạch gần hơn bên trái gồm các đoạn trắng đứt nhưng đang có style=solid. Đổi thành style=dashed. |
| 14 | QC1-06 | [A03](http://localhost:8080/tasks/13/jobs/13?frame=2) | lane #3104 | chính | Vệt sơn biên trái màu vàng nhưng đang có color=white. Đổi thành color=yellow. |
| 15 | QC1-06 | [A03](http://localhost:8080/tasks/13/jobs/13?frame=2) | lane #3105 | chính | Biên phải gồm các đoạn trắng đứt nhưng đang có style=solid. Đổi thành style=dashed. |
| 16 | QC1-06 | [A07](http://localhost:8080/tasks/13/jobs/13?frame=6) | lane #3136 + #3137 | chính | Vạch thực tế phía ngoài là vạch đứt nhưng cả hai đoạn đang có style=solid. Đổi thành style=dashed khi nối hai đoạn. Tính một lỗi cho cùng một vạch thực tế. |
| 17 | QC1-06 | [A12](http://localhost:8080/tasks/13/jobs/13?frame=11) | lane #3213 | chính | Biên phải ở xa gồm các đoạn trắng đứt nhưng đang có style=solid. Đổi thành style=dashed. |
| 18 | QC1-07 | [A07](http://localhost:8080/tasks/13/jobs/13?frame=6) | drivable #3138 | chính | Đa giác direct tạo phần lõm hình chữ nhật quanh xe sedan màu bạc, khoảng x447–674, y352–414. Bao phủ phần mặt đường như khi không có xe đó; không bám theo hình dáng xe. |
| 19 | QC1-07 | [A10](http://localhost:8080/tasks/13/jobs/13?frame=9) | drivable #3193 | chính | Đa giác direct vẫn bám theo mép dưới xe Subaru và các xe bên phải, tạo vùng khoét quanh xe. Vẽ liên tục phần mặt đường qua các xe như khi đường trống. Giải thích của giảng viên cho phép vùng direct rộng hơn trên mặt đường không có vạch; lỗi này không yêu cầu tách đa giác chỉ vì vùng đó rộng. |
| 20 | QC1-07 | [A11](http://localhost:8080/tasks/13/jobs/13?frame=10) | drivable #3208 | chính | Đa giác alternative né theo các xe SUV nhìn thấy, gồm xe khoảng x671–797. Bao phủ phần mặt đường có thể đi qua chỗ bị xe che, thay vì loại từng xe ra. |
| 21 | QC1-07 | [B03](http://localhost:8080/tasks/15/jobs/15?frame=2) | drivable #3019 | chính | Đa giác direct bám theo mép dưới xe màu bạc gần giữa ảnh ở xa, khoảng x600–675, y280–306. Tiếp tục vùng mặt đường như khi không có xe. |
| 22 | QC1-07 | [B03](http://localhost:8080/tasks/15/jobs/15?frame=2) | drivable #3022 | chính | Đa giác alternative uốn theo xe màu đen ở đầu xa. Bao phủ phần mặt đường qua vị trí xe thay vì khoét vùng theo hình dáng xe. |
| 23 | QC1-07 | [B05](http://localhost:8080/tasks/15/jobs/15?frame=4) | drivable #3032 | chính | Đa giác drivable uốn theo xe màu đen ở phía trên bên trái. Xe đang đi hoặc đang dừng không phải biên đường cố định; gán mặt đường như khi đường trống, đồng thời vẫn loại mép vỉa hè thực tế và thân xe mình. |
| 24 | QC1-09 | [A03](http://localhost:8080/tasks/13/jobs/13?frame=2) | traffic_sign #3222 | chính | Biển cảnh báo hình thoi màu cam đang ở nhóm prohibitory. Đổi thành group=warning. |
| 25 | QC1-09 | [A06](http://localhost:8080/tasks/13/jobs/13?frame=5) | traffic_sign #3127 | chính | Biển cảnh báo công trường hình thoi màu cam đang ở nhóm prohibitory. Đổi thành group=warning. |
| 26 | QC1-09 | [A06](http://localhost:8080/tasks/13/jobs/13?frame=5) | traffic_sign #3128 | chính | Biển ONE WAY đang ở nhóm information. Road v1.0 quy định rõ biển một chiều thuộc group=mandatory. |
| 27 | QC1-09 | [A10](http://localhost:8080/tasks/13/jobs/13?frame=9) | traffic_sign #3202 | chính | Biển mũi tên ONE WAY đang ở nhóm information. Đổi thành group=mandatory. |
| 28 | QC1-09 | [A10](http://localhost:8080/tasks/13/jobs/13?frame=9) | traffic_sign #3196 | chính | Một hộp bao cao đang chứa nhiều tấm biển đỗ xe/cấm dừng riêng biệt. Vẽ hộp chữ nhật sát mép cho từng tấm biển thực tế, thay vì bao cả cụm bằng một hộp. |
| 29 | QC1-11 | [B02](http://localhost:8080/tasks/15/jobs/15?frame=1) | traffic_light #3082 | chính | Đang có edge_zone=false, nhưng tâm hộp bao (134.2,165.0) cách tâm ảnh 597.4 px, vượt ngưỡng bán kính bài lab: 0.8 × 640 = 512 px. Đặt edge_zone=true theo quy ước trong kho mã. |
| 30 | QC1-11 | [B02](http://localhost:8080/tasks/15/jobs/15?frame=1) | traffic_light #3083 | chính | Đang có edge_zone=false, nhưng tâm hộp bao (1109.2,119.6) cách tâm ảnh 593.5 px, vượt ngưỡng bán kính bài lab: 0.8 × 640 = 512 px. Đặt edge_zone=true theo quy ước trong kho mã. |
| 31 | QC1-11 | [B03](http://localhost:8080/tasks/15/jobs/15?frame=2) | traffic_sign #3084 | chính | Đang có edge_zone=false, nhưng tâm hộp bao (1144.2,379.4) cách tâm ảnh 514.7 px, vượt ngưỡng bán kính bài lab: 0.8 × 640 = 512 px. Đặt edge_zone=true theo quy ước trong kho mã. |
| 32 | QC1-11 | [B04](http://localhost:8080/tasks/15/jobs/15?frame=3) | traffic_sign #3086 | chính | Đang có edge_zone=false, nhưng tâm hộp bao (1085.9,201.5) cách tâm ảnh 527.3 px, vượt ngưỡng bán kính bài lab: 0.8 × 640 = 512 px. Đặt edge_zone=true theo quy ước trong kho mã. |
| 33 | QC1-04 | [A07](http://localhost:8080/tasks/13/jobs/13?frame=6) | lane #3137 | chính | Thứ tự điểm bị đảo trong lúc sửa: điểm đầu (754,284), điểm cuối (1191,450), nên hiện đi từ xa về gần. Đảo lại thành gần ra xa khi chỉnh vạch phía ngoài. |
| 34 | QC1-01 | [A10](http://localhost:8080/tasks/13/jobs/13?frame=9) | thẻ weather | nhẹ | Thẻ đã được bổ sung nhưng đang lưu giá trị overcast. Theo Road v1.0, weather=rain áp dụng cả khi mặt đường ướt rõ do mưa như trong ảnh này. Đặt weather=rain. Lỗi thông tin ảnh không liên quan camera này được ghi mức nhẹ trong vòng kiểm. |

#### Tổng hợp phạm vi kiểm theo mã QC1

| Mã | Nội dung kiểm | Số mục kiểm | Lỗi đã xác nhận |
| --- | --- | --- | --- |
| QC1-01 | thẻ ảnh | 80 thẻ ảnh | 1 nhẹ |
| QC1-02 | đủ L1/R1 khi nhìn thấy vạch | 32 vị trí biên camera trước/sau được sàng lọc | 1 nặng |
| QC1-03 | vị trí làn (position) | 47 đường gán nhãn lane | 7 nặng |
| QC1-04 | tâm vạch, chiều và điểm cuối | 47 đường gán nhãn lane | 3 chính |
| QC1-05 | vạch đứt và chỗ che | 47 đường gán nhãn lane; miễn cảnh báo do cặp vạch đôi | 1 chính |
| QC1-06 | kiểu vạch, màu và loại đơn/đôi | 47 đường gán nhãn lane | 6 chính |
| QC1-07 | vùng và mép đường | 34 drivable, 16 crosswalk, 26 road_curb | 6 chính |
| QC1-08 | đèn và màu | 28 hộp bao đèn | 0; xem giới hạn bên dưới |
| QC1-09 | thuộc tính hộp bao và từng tấm biển | 59 hộp bao đèn/biển | 5 chính |
| QC1-10 | đủ biển / hình biển in | 31 hộp bao biển và quét 20 ảnh | 0; xem giới hạn bên dưới |
| QC1-11 | ảnh mắt cá và edge_zone | 46 đối tượng hình học trên ảnh mắt cá | 4 chính |
| QC1-12 | tệp | 2 bản chụp dữ liệu API; chưa có ZIP bàn giao gốc | 0; xem giới hạn bên dưới |

#### Kết quả của toàn bộ 20 ảnh

| Ảnh | Số hình + thẻ | Lỗi | Ghi chú | Bằng chứng |
| --- | ---: | --- | --- | --- |
| A01 | 14 | 0 lỗi xác nhận | Chưa xác nhận lỗi. Chấp nhận điểm cuối gần xe của R1 sau khi đính chính phiếu đầu. | [Ảnh chồng nhãn](../../reviews/core20-r2/overlays/A01.jpg) |
| A02 | 12 | 2 nặng, 2 chính | Vạch ngoài trái #3098 cần L2; vạch phải #3100 cần R1. Cả hai vạch trái cần kiểu dashed. Xem lại dusk/day nhưng chưa tính lỗi thời điểm khi thiếu nguồn đối chiếu đáng tin cậy. | [Ảnh chồng nhãn](../../reviews/core20-r2/overlays/A02.jpg) |
| A03 | 14 | 1 nặng, 3 chính | Vạch phải #3105 cần R1/dashed; vạch trái #3104 cần yellow; biển cam #3222 cần warning. Chấp nhận phạm vi direct rộng trên đường không có vạch. | [Ảnh chồng nhãn](../../reviews/core20-r2/overlays/A03.jpg) |
| A04 | 14 | 1 chính | Đảo chiều #3113. Chấp nhận hai đường gấp khúc theo hai vệt sơn của từng vạch đôi. | [Ảnh chồng nhãn](../../reviews/core20-r2/overlays/A04.jpg) |
| A05 | 6 | 0 lỗi xác nhận | Chưa xác nhận lỗi. Mặt đường xe có thể tiếp cận, không có vạch, có thể là direct. Không yêu cầu vẽ thêm L1/R1 không tồn tại. | [Ảnh chồng nhãn](../../reviews/core20-r2/overlays/A05.jpg) |
| A06 | 21 | 2 chính | Đổi biển cam #3127 thành warning và ONE WAY #3128 thành mandatory. Cần quy ước nhãn cho biểu tượng đi bộ trắng; không đoán để tính lỗi đỏ/xanh. | [Ảnh chồng nhãn](../../reviews/core20-r2/overlays/A06.jpg) |
| A07 | 8 | 1 nặng, 4 chính | Sửa biên R1 thực tế/R2 phía ngoài, các đoạn vạch đứt, chiều ngược của #3137 và vùng khoét theo xe sedan. | [Ảnh chồng nhãn](../../reviews/core20-r2/overlays/A07.jpg) |
| A08 | 41 | 1 nặng | Đoạn xa bên phải #3142 vẫn là L1. Đổi thành R1. Các đoạn chuyển kiểu vạch khác không bị coi là lỗi đường trùng. | [Ảnh chồng nhãn](../../reviews/core20-r2/overlays/A08.jpg) |
| A09 | 10 | 0 lỗi xác nhận | Chưa xác nhận lỗi. Chấp nhận hai đường cho vạch đôi và cách phân vùng direct/alternative hiện tại. | [Ảnh chồng nhãn](../../reviews/core20-r2/overlays/A09.jpg) |
| A10 | 18 | 3 chính, 1 nhẹ | Sửa ONE WAY #3202, tách các tấm biển trong #3196, bỏ vùng khoét theo xe và đặt weather=rain. Chấp nhận direct rộng trên đường không có vạch. | [Ảnh chồng nhãn](../../reviews/core20-r2/overlays/A10.jpg) |
| A11 | 13 | 1 chính | Chấp nhận cặp đường của vạch vàng đôi; bỏ vùng khoét theo xe SUV khỏi #3208. | [Ảnh chồng nhãn](../../reviews/core20-r2/overlays/A11.jpg) |
| A12 | 13 | 2 nặng, 1 chính | Vạch phải #3213 cần R1/dashed và vạch ngoài trái #3215 cần vị trí phía ngoài tương ứng. Đã rút lại nhận định trước về dải đỗ xe. | [Ảnh chồng nhãn](../../reviews/core20-r2/overlays/A12.jpg) |
| B01 | 8 | 0 lỗi xác nhận | Chưa xác nhận lỗi. Vùng qua đường/biên thân xe mình có vẻ nhất quán; không tính việc dọn đỉnh lặp tùy chọn thành lỗi. | [Ảnh chồng nhãn](../../reviews/core20-r2/overlays/B01.jpg) |
| B02 | 11 | 2 chính | Bật edge_zone cho cả hai đèn phía ngoài. Màu đèn người đi bộ mờ vẫn là câu hỏi cho người phụ trách, chưa phải lỗi nặng. | [Ảnh chồng nhãn](../../reviews/core20-r2/overlays/B02.jpg) |
| B03 | 14 | 4 chính | Đảo chiều #3016, bật edge_zone cho #3084 và bỏ hai vùng khoét theo xe. | [Ảnh chồng nhãn](../../reviews/core20-r2/overlays/B03.jpg) |
| B04 | 11 | 1 chính | Bật edge_zone cho #3086. Chưa xác nhận lỗi khác. | [Ảnh chồng nhãn](../../reviews/core20-r2/overlays/B04.jpg) |
| B05 | 9 | 1 chính | Đã sửa position=other. Còn vùng khoét theo xe khác; việc loại thân xe mình là đúng. | [Ảnh chồng nhãn](../../reviews/core20-r2/overlays/B05.jpg) |
| B06 | 7 | 0 lỗi xác nhận | Chưa xác nhận lỗi. Đã rút lại lỗi hình học trước; có thể hỏi giảng viên để xác định đối tượng vệt sơn nếu cần. | [Ảnh chồng nhãn](../../reviews/core20-r2/overlays/B06.jpg) |
| B07 | 11 | 0 lỗi xác nhận | Đã sửa position=other. Chưa xác nhận lỗi còn lại. Không tự động tính lỗi vì có nhiều vùng qua đường riêng biệt. | [Ảnh chồng nhãn](../../reviews/core20-r2/overlays/B07.jpg) |
| B08 | 7 | 1 nặng | #3078 vẫn có R1; đặt other cho camera bên này. | [Ảnh chồng nhãn](../../reviews/core20-r2/overlays/B08.jpg) |

#### Đối chiếu với phiếu kiểm đầu

| Lỗi ở lần kiểm trước | Xử lý trong vòng kiểm này |
| --- | --- |
| 1–24: thiếu thẻ ảnh camera trước | Đã sửa; hiện có đủ thẻ. |
| 34 ở B05 và 35 ở B07: vị trí làn trên camera bên | Đã sửa. |
| 28–30 ở A07: thiếu/sai vị trí biên | Gộp thành một lỗi xác định biên thực tế; không tính ba lỗi nặng riêng. |
| 45–46 ở A07: kiểu vạch đứt | Gộp thành một lỗi cho cùng một vạch thực tế. |
| 37 | Rút lại: ảnh cắt phóng to cho thấy vệt R1 gần nhất kết thúc xấp xỉ điểm cuối hiện có. Chỉ dẫn trước về việc kéo dài đến (710,720) là sai. Giữ điểm cuối. |
| 48 | Rút lại: nhận định trước về phạm vi direct quá rộng. Áp dụng quy tắc giảng viên rằng mặt đường xe có thể tiếp cận, không có vạch, có thể là direct; chưa đủ bằng chứng cho lỗi loại vùng trước đây. |
| 52 | Rút lại: chưa đủ chắc chắn để xác định dải đỗ xe trong ảnh này. Theo giải thích của giảng viên, vùng xe có thể chuyển sang có thể là alternative; rút lại lỗi trước. |
| 65 | Rút lại: chỉ riêng đoạn dài hoặc ít đỉnh chưa chứng minh được độ lệch đo được trên 5 px hay vẽ nhầm làn. Rút lại lỗi hình học B06; chỉ giữ ghi chú xem lại tùy chọn. |

#### Câu hỏi cho người phụ trách và việc bàn giao

Chưa có đầy đủ bảng kế hoạch gán nhãn theo từng ảnh của giảng viên nên việc đánh giá độ đầy đủ còn giới hạn: không tính lỗi thiếu đèn, biển, mép đường hoặc đa giác drivable ở B06 khi chưa xác nhận các nhóm nhãn đó là bắt buộc. Tương tự, không vẽ thêm vạch sơn không tồn tại chỉ để hết cảnh báo của công cụ kiểm tra định dạng.

Cần xác nhận quy ước nhãn cho biểu tượng người đi bộ màu trắng ở A06 và đèn người đi bộ có vẻ xanh nhưng mờ ở B02. Không tính lỗi nặng về màu cho các ca chưa rõ này. Những giá trị thời điểm trong ngày chưa rõ chỉ được ghi chú để xem lại.

Việc kiểm hình học của edge_zone dùng quy ước trong kho mã: trên ảnh mắt cá 1280×966, tâm hộp bao cách điểm (640,483) trên 512 px thì thuộc vùng rìa. Cả bốn hộp bao ngoài rìa được liệt kê đều vượt ngưỡng này. Cặp đường của vạch đôi, hộp bao nhỏ không bắt buộc và đỉnh lặp có thể gây cảnh báo định dạng mà chưa phải lỗi QC.

Hai ZIP bàn giao theo định dạng gốc CVAT for images 1.1 và tệp kê khai có số lần nộp vẫn cần được kiểm riêng về khả năng mở lại/nhập lại. Các bản XML dựng từ dữ liệu kiểm cho thấy nhãn đã lưu có thể đọc được; chúng không phải bản xuất bàn giao gốc. Cả hai công việc vẫn có trạng thái completed (đã hoàn thành), ở giai đoạn annotation (gán nhãn).

#### Quyết định và bằng chứng

**Cần sửa (Rework):** còn 8 lỗi nặng. Tỉ lệ lỗi chính là 25/262 = 9.54%, với mẫu số là số đối tượng hình học cộng thẻ ảnh hiện có. Các lỗi nặng liên quan biên làn ở A07 và lỗi kiểu vạch của các đoạn rời được gộp như đã nêu. Không suy ra điểm số của môn học.

Ngay cả khi loại cả sáu lỗi về vùng lái né theo hình dáng xe, vẫn còn 19 lỗi chính (19/262 = 7.25%) cùng các lỗi nặng về làn. Vì vậy quyết định của vòng kiểm này không phụ thuộc vào cách hiểu vùng lái đang được tranh luận.

- [Bản chụp dữ liệu CVAT của vòng kiểm](../../reviews/core20-r2/snapshot.json), [nhãn đã giải mã](../../reviews/core20-r2/review-data.json), [thay đổi so với bản đầu](../../reviews/core20-r2/changes.json), [mã băm ảnh](../../reviews/core20-r2/frame-hashes.json), [danh sách lỗi dạng JSON](../../reviews/core20-r2/findings.json) và [cảnh báo định dạng](../../reviews/core20-r2/lint.txt).
- Giữ [phiếu kiểm đầu](../../reviews/core20/nguyengiahuy-qc1-for-nguyenhaidang.md) để truy vết; phiếu vòng 2 thay thế những nhận định đã rút lại và số lỗi tương ứng của phiếu đầu.
- [Road v1.0](../../../docs/guideline_road_v1.0.md), [quy tắc xếp mức lỗi](../../../docs/qc_severity_road_v1.0.md) và giải thích bổ sung của giảng viên do học viên cung cấp trong cuộc trao đổi.

Thời điểm lưu dữ liệu theo giờ địa phương: front lúc 2026-11-21 00:15:07 +07; fisheye lúc 2026-11-21 00:06:03 +07. Mã băm SHA-256 của toàn bộ 20 ảnh dùng để kiểm trên máy đều khớp với ảnh gốc vừa đọc từ CVAT.

</details>
