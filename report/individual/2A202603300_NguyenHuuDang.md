# Báo cáo cá nhân — NguyenHuuDang-2A202603300

Đoạn video: MOT17-09, 150 frame (frame 1–150), nguồn MOTChallenge, giấy phép CC BY-NC-SA 3.0.

## 0. Thông tin học viên

- Họ tên:  Nguyễn Hữu Đăng
- MSSV: 2A202603300
- Mã đề (A/B/C): B
- Email: [Dang36390@gmail.com](mailto:Dang36390@gmail.com)
- Link repository: [github.com/huudang-de/K5-L2B-DAY05-NguyenHuuDang-2A202603300-MOTTracking](https://github.com/huudang-de/K5-L2B-DAY05-NguyenHuuDang-2A202603300-MOTTracking)
- Giờ bắt đầu: 16h10p
- Giờ kết thúc: 17h35p

## 1. Xem trước đoạn video (CP0)

Ghi **trước khi vẽ**, mỗi người một dòng.

| Mã | Frame xuất hiện | Frame cuối thấy được | Rẽ / dừng / đổi tốc độ ở frame | Bị che ở frame                        | Ghi chú                                              |
| --- | ----------------- | ------------------------- | -------------------------------------- | --------------------------------------- | ----------------------------------------------------- |
| P1  | 0                 | 149                       | 0–30, 50–60                          | 29–52 (mất hẳn 39–48)               | Người bị che chính ở CP2, hiện lại ở frame 49 |
| P2  | 0                 | 149                       | 103–130, 139–149                     | Không                                  | Đi từ xa lại gần camera suốt 150 frame           |
| P3  | 0                 | 149                       | 103–130                               | 0–69                                   | Có mặt đủ 150 frame                               |
| P4  | 0                 | 146                       | 137–146                               | 108–146 (mất hẳn 110–136, 147–149) | Bé gái đi cùng P5, khuất đoạn cuối            |
| P5  | 0                 | 109                       | Không                                 | 100–109 (mất hẳn 110–149)           | Mẹ của P4, bị P2 và P3 che hẳn từ frame 110     |

## 2. Keyframe và thời gian (CP1, CP4)

Số keyframe lấy từ kết quả `src/check_submission.py`.

| Mã             | Số keyframe | Keyframe ở frame                                                                                                                        | Số frame có mặt | Keyframe / 100 frame | Thời gian (phút) | Chỗ khó                              |
| --------------- | ------------ | ---------------------------------------------------------------------------------------------------------------------------------------- | ------------------ | -------------------- | ------------------ | -------------------------------------- |
| P1              | 16           | 0, 20, 29, 49, 50, 53, 59, 60, 70, 80, 90, 100, 110, 120, 140, 149                                                                       | 140                | 11.4                 | 15                 | Lúc bị khuất                        |
| P2              | 30           | 0, 10, 20, 30, 40, 50, 60, 70, 74, 80, 90, 100, 103, 104, 105, 110, 118, 119, 120, 122, 125, 126, 127, 128, 129, 130, 139, 143, 146, 149 | 150                | 20.0                 | 20                 | Kích thước thay đổi khi lại gần |
| P3              | 27           | 0, 10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 103, 104, 110, 114, 115, 116, 118, 120, 125, 126, 127, 129, 130, 140, 145, 149               | 150                | 18.0                 | 20                 | Thay đổi liên tục                  |
| P4              | 18           | 0, 10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 108, 109, 137, 140, 143, 145, 146                                                            | 120                | 15.0                 | 15                 | Khuất sau P2, P3 đoạn cuối         |
| P5              | 5            | 0, 10, 20, 40, 100                                                                                                                       | 110                | 4.5                  | 15                 | Bị che hẳn từ frame 110             |
| **Tổng** | **96** |                                                                                                                                          | **670**      | **14.3**       | 1h25p              |                                        |

Keyframe / 100 frame của cả bài = tổng keyframe ÷ tổng số frame có mặt × 100 = 96 ÷ 670 × 100 = 14.3

Bạn đặt keyframe nhiều nhất ở người nào? Vì sao (người đó rẽ, dừng, lại gần camera hay bị che)?

Tôi đặt keyframe nhiều nhất ở người P2 (Track 1, 30 keyframe; 20.0 keyframe / 100 frame) vì người đó đi từ xa lại gần camera suốt 150 frame nên kích thước box và tốc độ thay đổi liên tục.

## 3. Đoạn bị che (CP2)

Người bị che: P1

| Mốc                                              | Frame |
| ------------------------------------------------- | ----: |
| Bắt đầu bị che một phần (bật `occluded`) |    29 |
| Mất hẳn (bật `outside`)                      |    39 |
| Hiện lại (tắt `outside`)                     |    49 |
| Thấy rõ trở lại (tắt `occluded`)           |    53 |

- Thời gian khuất hẳn: 10 frame = 0.33 giây.
- Quyết định: giữ cùng ID.
- Lý do (trả lời 3 câu: khuất bao lâu so với 60 frame, ngoại hình có khớp, chỗ hiện lại có đúng hướng và tốc độ):

  - Thời gian khuất hẳn là 10 frame (0,33 giây), nhỏ hơn ngưỡng 60 frame (2 giây) của lớp.
  - Ngoại hình và hướng/tốc độ khi hiện lại:
    - Ngoại hình hoàn toàn trùng khớp: người đàn ông mặc áo dài tay đen, quần jean xanh, đi giày tối màu, vóc dáng và kích thước box (~111×263 px) đồng nhất trước và sau khi bị người đi ngang (áo khoác đen, quần kaki) che khuất. Vị trí hiện lại ngay tại cửa ra vào cửa hàng Vodafone, tiếp tục hướng đi thẳng từ trong cửa hàng ra ngoài với tốc độ chậm và ổn định, khớp với quỹ đạo trước khi bị che.

Ảnh chụp màn hình:


`*Nguồn ảnh: MOT17, MOTChallenge (Milan et al., 2016).*`

## 4. Tự review ID (CP3)

Lượt 1 theo người (đi ngược từ frame 149 về 0 trên CVAT), lượt 2 theo cảnh (nhảy 10 frame). Ít nhất 3 dòng; không có lỗi thì ghi một dòng "đã kiểm hai lượt, không lỗi".

Loại lỗi dùng đúng một trong 7 mã: `id_switch`, `fragmentation`, `lost`, `merge`, `false_track`, `drift`, `flag`.

|        Frame | Mã người | Loại lỗi      | Mô tả một câu                                                                                          | Phát hiện ở lượt | Đã sửa?                                                              |
| -----------: | ----------- | --------------- | ---------------------------------------------------------------------------------------------------------- | --------------------- | ----------------------------------------------------------------------- |
|       0–109 | P4, P5      | `merge`       | Gộp chung bé gái (P4) và người mẹ (P5) vào cùng một bounding box ở bản gán đầu.             | Lượt 2              | Có (đã tách thành 2 track riêng cho P4 và P5)                    |
|       0–149 | P5          | `false_track` | Gán nhầm track sang người đi ngang ngoài danh sách P1–P5 của Đề B.                              | Lượt 2              | Có (đã xóa track sai và gán lại đúng P5)                       |
| 0–9, 39–58 | P1          | `flag`        | Bật `occluded` từ frame 0–9 khi chưa bị che và tắt trễ sau đoạn che.                           | Lượt 1              | Có (đã chỉnh lại `occluded` 29–52, `outside` 39–48)          |
|      52–130 | P2          | `drift`       | Box nội suy hơi lệch khỏi người ở đoạn tiến lại gần camera, có chỗ đặt keyframe quá dày. | Lượt 1              | Có (đã kéo chỉnh keyframe khớp lại và tỉa bớt keyframe thừa) |

Tổng hợp số lỗi theo loại:

| `id_switch` | `fragmentation` | `lost` | `merge` | `false_track` | `drift` | `flag` |
| ------------: | ----------------: | -------: | --------: | --------------: | --------: | -------: |
|             0 |                 0 |        0 |         1 |               1 |         1 |        1 |

Lỗi nào chỉ lượt 2 (theo cảnh) mới thấy, lượt 1 (theo người) không thấy? Vì sao?

Các lỗi như **`merge`**(1 box gộp 2 người như `P4`+ `P5`), **`false_track`**(vẽ nhầm sang người ngoài Đề B), hoặc **`id_switch`**(2 box tráo ID cho nhau) thường **chỉ phát hiện rõ ở Lượt 2**. Lý do là ở Lượt 1 mình chỉ tập trung nhìn từng người một nên dễ chỉ thấy box vẫn bám theo người đó, còn sang Lượt 2 khi nhìn toàn cảnh cả 5 box cùng lúc và đối chiếu với danh sách 5 người của đề, mình mới thấy ngay được chỗ nào bị thiếu người, thừa người hoặc gộp hai người vào chung một box.

## 5. File xuất và kết quả tự kiểm (CP4)

| Kiểm tra                                                          | Kết quả                                                                                               |
| ------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------- |
| Tên file MOT 1.1                                                  | `src/exports/NguyenHuuDang_mot.zip`                                                                   |
| Tên file CVAT for video 1.1                                       | `src/exports/NguyenHuuDang_cvat_video.zip`                                                            |
| Số track ID khác nhau trong `gt/gt.txt` (phải là 5)          | 5                                                                                                       |
| Frame `outside` không có dòng trong `gt.txt` (đúng / sai) | Đúng (đã kiểm tra tại `frame 39 CVAT / frame 40 gt.txt của Track 3 XML (Track 4 gt.txt - P1)`) |
| Job đã completed trên CVAT máy cá nhân                       | Đã hoàn thành (Completed)                                                                           |

Dán phần tóm tắt in ra từ `src/check_submission.py`:

```text
=== File MOT 1.1: NguyenHuuDang_mot.zip ===
  Số track ID: 5   |   Tổng số box: 670
  [OK]        Đúng 5 track ID.

=== File CVAT for video 1.1: NguyenHuuDang_cvat_video.zip ===
  Tổng: 96 keyframe / 670 frame có mặt = 14.3 keyframe / 100 frame
  [OK]        Đọc được 5 track từ annotations.xml.

=== Tóm tắt ===
  Lỗi: 0   |   Cảnh báo: 0
  Đạt. Dán phần tóm tắt này vào báo cáo mục 5.
```

## 6. Ba câu kết

1. Nếu được gán lại, bạn sẽ đặt keyframe khác ở đâu? Vì sao?

   Nếu gán lại, tôi sẽ chỉ đặt keyframe tại đúng các điểm đổi hướng, đổi tốc độ, đổi kích thước và ngay trước/sau đoạn che thay vì chỉnh sát nhau ở đoạn đi thẳng — vừa tiết kiệm thời gian, vừa giúp box nội suy mượt không bị rung.
2. Có chỗ nào bạn không chắc "cùng ID hay ID mới"? Bạn đã quyết định và ghi chú thế nào?

   Đoạn bị che của P1 (khuất **`39–48`**, chỉ 10 frame = 0,33 giây) : lúc người đó bị che khuất hoàn toàn, đối chiếu ngưỡng 60 frame (2 giây) cùng với ngoại hình và hướng/tốc độ khi hiện lại. Vì thời gian khuất ≤ 60 frame và mọi dấu hiệu đều khớp, quyết định dùng `outside`rồi tắt `outside`để  giữ cùng ID thay vì tách track mới).
3. Một lỗi ID trong job của bạn (nếu không còn sót, chọn lỗi đã sửa) có thể làm xe tự lái dự đoán sai chuyển động của người đó như thế nào? Lỗi đó ảnh hưởng MOTA hay IDF1 nhiều hơn?

   Tác động lên xe tự lái: Nếu bị **`fragmentation`**(đứt track thành ID mới): xe tự lái tưởng đó là người mới xuất hiện, bị mất lịch sử hướng đi và vận tốc trước đó nên dự đoán quỹ đạo tiếp theo bị lệch. Nếu bị **`id_switch`**(nhảy ID sang người khác): xe tự lái tính ra vận tốc nhảy vọt phi lý trong 1/30 giây, dễ dự đoán sai hướng băng qua đường và phanh/đánh lái nhầm.

   MOTA hay IDF1 bị ảnh hưởng nhiều hơn: Ảnh hưởng`IDF1` nhiều hơn , vì `IDF1`đo khả năng giữ đúng cùng một ID xuyên suốt cả đoạn video (đứt hoặc tráo ID giữa đường làm mất phần lớn thời lượng khớp ID), còn `MOTA`chủ yếu tính số lần `IDSW`tại frame xảy ra lỗi và độ khớp box từng frame.

## Bonus (nếu làm)

### B1 — Hai người đi sát

...

### B2 — So cách đặt keyframe

| Cách đặt             | Số keyframe | Frame trôi nhất | Ghi chú |
| ----------------------- | -----------: | ----------------: | -------- |
| Đều mỗi 30 frame     |              |                   |          |
| Theo chỗ đổi hướng |              |                   |          |

...

### B3 — So với tracker có sẵn

| Frame | Mã người | Tracker làm gì | Nhãn của bạn | Giải thích (đoán rồi sửa / ghép IoU / box score thấp / ngoại hình) |
| ----: | ----------- | ---------------- | --------------- | ---------------------------------------------------------------------------- |
|       |             |                  |                 |                                                                              |
|       |             |                  |                 |                                                                              |

## 7. Tài liệu tham khảo và công cụ AI đã dùng

Trợ lý AI Antigravity — hỗ trợ cài đặt môi trường `.venv` và `setup_local_lab.py`, giải thích khái niệm keyframe / `id_switch` / `outside`, chạy `src/check_submission.py` và tổng hợp số liệu thống kê (phần tự review mục 4 và ba câu kết mục 6 do học viên tự thực hiện).
