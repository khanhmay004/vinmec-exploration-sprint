# Log thử nghiệm prototype: Trợ lý hàng chờ (A/B/C)

> **Chưa có dữ liệu.** Mọi ô `[ĐIỀN SAU KHI THỬ THẬT]` chỉ được điền bằng quan sát thật từ buổi thử. Không dùng AI để tạo, đoán hay "làm đẹp" dữ liệu, trích dẫn hay nhận xét.
> Khung template này được soạn với sự hỗ trợ của AI (Claude). Nội dung điền vào là của người phỏng vấn.

## Cách dùng file này

- **Người thử:** 2–3 người từng đi khám và phải ngồi chờ (tuyển theo trải nghiệm gần đây, ví dụ "trong 3 tháng gần đây đã ngồi chờ khám hơn 30 phút"). Ẩn danh là **T1, T2, T3**. Nếu người thử trùng với người đã phỏng vấn ở `01-phong-van/` thì ghi chú "= P?".
- **Ràng buộc (đề bài 6.4):** xin đồng ý trước khi bắt đầu; không ghi âm khi chưa được đồng ý; không hỏi chẩn đoán, bệnh án hay tình trạng sức khỏe; không chụp ảnh người hay giấy tờ y tế; prototype và người phỏng vấn **không đưa lời khuyên y khoa**.
- **Chuẩn bị:** mở `index.html`, bấm ↺ Reset, xóa log phiên, bật "Đổi tab = reset", tốc độ "Chậm". Người thử **tự cầm** điện thoại/chuột. Che bảng điều phối.
- **Thứ tự phương án:** đổi vòng giữa các người thử để giảm thiên lệch thứ tự (T1: A→B→C, T2: B→C→A, T3: C→A→B).
- **Sau mỗi lượt:** tải log JSON (⬇ Tải JSON), lưu cạnh file này với tên `log-T1.json`… và điền mục "Tôi sửa gì sau lượt này" **trước khi** sang người tiếp theo.

### Kịch bản 5 nhịp (đọc gần nguyên văn, như nhau cho mọi người thử)

| # | Nhịp | Người phỏng vấn nói | Thời lượng |
|---|---|---|---|
| 01 | COMFORT | "Hôm nay mình thử một **ý tưởng**, không thử bạn. Không có đúng hay sai. Bạn cứ nói to điều mình đang nghĩ khi bấm nhé. Đây là màn hình giả lập cho bài học, không phải app thật, và nó không tư vấn sức khỏe. Bạn đồng ý cho mình ghi chép (và ghi âm, nếu bạn đồng ý) không?" | ~1' |
| 02 | CONTEXT | "Bạn kể giúp mình **lần gần nhất** bạn phải ngồi chờ khám lâu: lúc đó bạn làm gì trong lúc chờ? Có lúc nào muốn đi đâu đó mà không dám đi không?" (chỉ hỏi về trải nghiệm chờ, **không** hỏi bệnh) | ~2' |
| 03 | TASK | "Giả sử bạn vừa check-in xong, đang ngồi chờ, và đã gần trưa. **Hãy dùng màn hình này để quyết định xem bạn có kịp đi ăn trưa không.**" (chỉ đích, **không** chỉ đường: không nói "bấm Hỏi trợ lý") | mỗi phương án ~3–4' |
| 04 | OBSERVE | (im lặng). Chỉ khi phiên bị tắc: "Cứ nói to suy nghĩ nhé" · "Bạn sẽ làm gì tiếp theo?" · "Theo bạn nó nên hoạt động thế nào?" | trong lúc làm |
| 05 | COMPARE | "Trong tình huống bạn vừa kể, bạn chọn A, B hay C? **Vì sao?** Chọn nó thì bạn **chấp nhận đánh đổi gì**? Trường hợp nào bạn **muốn phương án khác**?" | ~4' |

Giữa các phương án: bấm tab tiếp theo (tự reset về 11:20, 7 người trước). Nhắc lại nguyên câu task. Với từng phương án, khi người thử đã có quyết định, người phỏng vấn bấm 🩺 hội chẩn (hoặc để tự kích hoạt ở phút 12) và quan sát họ phản ứng với lý do chậm.

### 4 tầng evidence (Day 18 §5.8)

| Tầng | Loại | Ví dụ dạng ghi | Ghi vào |
|---|---|---|---|
| 1 | Việc đã xảy ra (hành vi) | "Bấm chip Ăn trưa trước khi đọc thẻ trạng thái" | **OBSERVED** |
| 2 | Lời nói tại hiện trường, lúc đang làm | "…sát giờ à, thôi chắc không đi" | **OBSERVED (nói lúc làm)** |
| 3 | Giải thích sau khi được hỏi | "Tôi chọn C vì nó hỏi tôi trước" | **INTERPRETED** |
| 4 | Dự đoán về bản thân / tương lai | "Lần sau chắc tôi sẽ bật thông báo" | **STILL UNPROVEN** |

Một hành động ở tầng 1 nặng hơn mười câu ở tầng 4. **Quyết định thiết kế** ghi riêng ở mục "Tôi sửa gì sau lượt này".

---

## Người thử T1

- **Thông tin (ẩn danh):** [ĐIỀN SAU KHI THỬ THẬT]  <!-- nhóm tuổi, mức quen smartphone, lần chờ khám gần nhất bao lâu trước. KHÔNG ghi bệnh -->
- **Ngày / thời lượng / hình thức:** [ĐIỀN SAU KHI THỬ THẬT]
- **Đồng ý tham gia:** [ ] Có · Ghi âm: [ ] Có [ ] Không
- **Thứ tự phương án:** A → B → C
- **Chế độ AI:** [ ] AI thật (model: ____ ) [ ] Kịch bản mẫu · **Phiên bản prompt:** v__
- **File log phiên:** `log-T1.json`

### 01 COMFORT
- Đã đọc script, người thử có câu hỏi gì: [ĐIỀN SAU KHI THỬ THẬT]

### 02 CONTEXT (≈2'): lần chờ gần nhất
- Chuyện đã xảy ra (event → behavior → workaround → consequence): [ĐIỀN SAU KHI THỬ THẬT]
- Trích dẫn nguyên văn đáng chú ý: "[ĐIỀN SAU KHI THỬ THẬT]"

### 03 TASK + 04 OBSERVE

| Quan sát | A | B | C |
|---|---|---|---|
| First action (thao tác đầu tiên, sau bao nhiêu giây) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Hesitation (dừng / đọc lại ở đâu) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Đọc hay bỏ qua evidence (khoảng thời gian, nhãn Ổn định/Dao động, lý do hội chẩn, thẻ KỊP/SÁT GIỜ) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Misinterpretation (hiểu sai chỗ nào) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Correction / recovery (sửa thời gian, Ẩn/Tắt thông báo, bỏ nhắc, gọi nhân viên) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Cần cứu hộ? (dùng câu rescue nào) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Quyết định cuối của task (đi ăn / không / đi việc khác) và dựa vào đâu | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Thời gian hoàn thành task | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| AI trả lời sai / lạ (trích nguyên văn, chế độ AI thật hay mẫu) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |

**Lời nói tại hiện trường (nguyên văn, ghi kèm phương án):**
- A: "[ĐIỀN SAU KHI THỬ THẬT]"
- B: "[ĐIỀN SAU KHI THỬ THẬT]"
- C: "[ĐIỀN SAU KHI THỬ THẬT]"

### 05 COMPARE

| Câu hỏi | Trả lời (nguyên văn nếu được) |
|---|---|
| **CHOICE:** chọn A, B hay C? Vì sao? | [ĐIỀN SAU KHI THỬ THẬT] |
| **TRADE-OFF:** chọn nó thì chấp nhận đánh đổi gì? | [ĐIỀN SAU KHI THỬ THẬT] |
| **BOUNDARY:** trường hợp nào muốn phương án khác? (ví dụ đi một mình / có con nhỏ / đang mệt / ít thời gian) | [ĐIỀN SAU KHI THỬ THẬT] |
| Tiêu chí người thử thật sự dùng để so sánh | [ĐIỀN SAU KHI THỬ THẬT] |

### Bảng evidence 4 tầng: T1

| Tầng | Nội dung | Phương án liên quan |
|---|---|---|
| 1 · OBSERVED (hành vi) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| 2 · OBSERVED (nói lúc làm) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| 3 · INTERPRETED (giải thích sau) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| 4 · STILL UNPROVEN (dự đoán) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |

### Sự cố an toàn / ngoài phạm vi (nếu có)
- Người thử có hỏi câu y khoa không? AI xử lý thế nào? (handoff có hiện không): [ĐIỀN SAU KHI THỬ THẬT]
- Khối khẩn cấp có hiện đúng hay sai không: [ĐIỀN SAU KHI THỬ THẬT]

### Tôi sửa gì sau lượt này
| Vấn đề quan sát được (dẫn về tầng 1–2 ở trên) | Quyết định thiết kế (Decided) | Sửa ở đâu (prompt vN / UI / logic ước tính) | Đã sửa? |
|---|---|---|---|
| [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ ] |
| [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ ] |

- Điều muốn test tiếp ở người sau: [ĐIỀN SAU KHI THỬ THẬT]

---

## Người thử T2

- **Thông tin (ẩn danh):** [ĐIỀN SAU KHI THỬ THẬT]  <!-- nhóm tuổi, mức quen smartphone, lần chờ khám gần nhất bao lâu trước. KHÔNG ghi bệnh -->
- **Ngày / thời lượng / hình thức:** [ĐIỀN SAU KHI THỬ THẬT]
- **Đồng ý tham gia:** [ ] Có · Ghi âm: [ ] Có [ ] Không
- **Thứ tự phương án:** B → C → A
- **Chế độ AI:** [ ] AI thật (model: ____ ) [ ] Kịch bản mẫu · **Phiên bản prompt:** v__
- **File log phiên:** `log-T2.json`

### 01 COMFORT
- Đã đọc script, người thử có câu hỏi gì: [ĐIỀN SAU KHI THỬ THẬT]

### 02 CONTEXT (≈2'): lần chờ gần nhất
- Chuyện đã xảy ra (event → behavior → workaround → consequence): [ĐIỀN SAU KHI THỬ THẬT]
- Trích dẫn nguyên văn đáng chú ý: "[ĐIỀN SAU KHI THỬ THẬT]"

### 03 TASK + 04 OBSERVE

| Quan sát | A | B | C |
|---|---|---|---|
| First action (thao tác đầu tiên, sau bao nhiêu giây) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Hesitation (dừng / đọc lại ở đâu) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Đọc hay bỏ qua evidence (khoảng thời gian, nhãn Ổn định/Dao động, lý do hội chẩn, thẻ KỊP/SÁT GIỜ) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Misinterpretation (hiểu sai chỗ nào) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Correction / recovery (sửa thời gian, Ẩn/Tắt thông báo, bỏ nhắc, gọi nhân viên) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Cần cứu hộ? (dùng câu rescue nào) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Quyết định cuối của task (đi ăn / không / đi việc khác) và dựa vào đâu | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Thời gian hoàn thành task | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| AI trả lời sai / lạ (trích nguyên văn, chế độ AI thật hay mẫu) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |

**Lời nói tại hiện trường (nguyên văn, ghi kèm phương án):**
- A: "[ĐIỀN SAU KHI THỬ THẬT]"
- B: "[ĐIỀN SAU KHI THỬ THẬT]"
- C: "[ĐIỀN SAU KHI THỬ THẬT]"

### 05 COMPARE

| Câu hỏi | Trả lời (nguyên văn nếu được) |
|---|---|
| **CHOICE:** chọn A, B hay C? Vì sao? | [ĐIỀN SAU KHI THỬ THẬT] |
| **TRADE-OFF:** chọn nó thì chấp nhận đánh đổi gì? | [ĐIỀN SAU KHI THỬ THẬT] |
| **BOUNDARY:** trường hợp nào muốn phương án khác? (ví dụ đi một mình / có con nhỏ / đang mệt / ít thời gian) | [ĐIỀN SAU KHI THỬ THẬT] |
| Tiêu chí người thử thật sự dùng để so sánh | [ĐIỀN SAU KHI THỬ THẬT] |

### Bảng evidence 4 tầng: T2

| Tầng | Nội dung | Phương án liên quan |
|---|---|---|
| 1 · OBSERVED (hành vi) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| 2 · OBSERVED (nói lúc làm) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| 3 · INTERPRETED (giải thích sau) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| 4 · STILL UNPROVEN (dự đoán) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |

### Sự cố an toàn / ngoài phạm vi (nếu có)
- Người thử có hỏi câu y khoa không? AI xử lý thế nào? (handoff có hiện không): [ĐIỀN SAU KHI THỬ THẬT]
- Khối khẩn cấp có hiện đúng hay sai không: [ĐIỀN SAU KHI THỬ THẬT]

### Tôi sửa gì sau lượt này
| Vấn đề quan sát được (dẫn về tầng 1–2 ở trên) | Quyết định thiết kế (Decided) | Sửa ở đâu (prompt vN / UI / logic ước tính) | Đã sửa? |
|---|---|---|---|
| [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ ] |
| [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ ] |

- Điều muốn test tiếp ở người sau: [ĐIỀN SAU KHI THỬ THẬT]

---

## Người thử T3

- **Thông tin (ẩn danh):** [ĐIỀN SAU KHI THỬ THẬT]  <!-- nhóm tuổi, mức quen smartphone, lần chờ khám gần nhất bao lâu trước. KHÔNG ghi bệnh -->
- **Ngày / thời lượng / hình thức:** [ĐIỀN SAU KHI THỬ THẬT]
- **Đồng ý tham gia:** [ ] Có · Ghi âm: [ ] Có [ ] Không
- **Thứ tự phương án:** C → A → B
- **Chế độ AI:** [ ] AI thật (model: ____ ) [ ] Kịch bản mẫu · **Phiên bản prompt:** v__
- **File log phiên:** `log-T3.json`

### 01 COMFORT
- Đã đọc script, người thử có câu hỏi gì: [ĐIỀN SAU KHI THỬ THẬT]

### 02 CONTEXT (≈2'): lần chờ gần nhất
- Chuyện đã xảy ra (event → behavior → workaround → consequence): [ĐIỀN SAU KHI THỬ THẬT]
- Trích dẫn nguyên văn đáng chú ý: "[ĐIỀN SAU KHI THỬ THẬT]"

### 03 TASK + 04 OBSERVE

| Quan sát | A | B | C |
|---|---|---|---|
| First action (thao tác đầu tiên, sau bao nhiêu giây) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Hesitation (dừng / đọc lại ở đâu) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Đọc hay bỏ qua evidence (khoảng thời gian, nhãn Ổn định/Dao động, lý do hội chẩn, thẻ KỊP/SÁT GIỜ) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Misinterpretation (hiểu sai chỗ nào) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Correction / recovery (sửa thời gian, Ẩn/Tắt thông báo, bỏ nhắc, gọi nhân viên) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Cần cứu hộ? (dùng câu rescue nào) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Quyết định cuối của task (đi ăn / không / đi việc khác) và dựa vào đâu | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Thời gian hoàn thành task | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| AI trả lời sai / lạ (trích nguyên văn, chế độ AI thật hay mẫu) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |

**Lời nói tại hiện trường (nguyên văn, ghi kèm phương án):**
- A: "[ĐIỀN SAU KHI THỬ THẬT]"
- B: "[ĐIỀN SAU KHI THỬ THẬT]"
- C: "[ĐIỀN SAU KHI THỬ THẬT]"

### 05 COMPARE

| Câu hỏi | Trả lời (nguyên văn nếu được) |
|---|---|
| **CHOICE:** chọn A, B hay C? Vì sao? | [ĐIỀN SAU KHI THỬ THẬT] |
| **TRADE-OFF:** chọn nó thì chấp nhận đánh đổi gì? | [ĐIỀN SAU KHI THỬ THẬT] |
| **BOUNDARY:** trường hợp nào muốn phương án khác? (ví dụ đi một mình / có con nhỏ / đang mệt / ít thời gian) | [ĐIỀN SAU KHI THỬ THẬT] |
| Tiêu chí người thử thật sự dùng để so sánh | [ĐIỀN SAU KHI THỬ THẬT] |

### Bảng evidence 4 tầng: T3

| Tầng | Nội dung | Phương án liên quan |
|---|---|---|
| 1 · OBSERVED (hành vi) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| 2 · OBSERVED (nói lúc làm) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| 3 · INTERPRETED (giải thích sau) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| 4 · STILL UNPROVEN (dự đoán) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |

### Sự cố an toàn / ngoài phạm vi (nếu có)
- Người thử có hỏi câu y khoa không? AI xử lý thế nào? (handoff có hiện không): [ĐIỀN SAU KHI THỬ THẬT]
- Khối khẩn cấp có hiện đúng hay sai không: [ĐIỀN SAU KHI THỬ THẬT]

### Tôi sửa gì sau lượt này
| Vấn đề quan sát được (dẫn về tầng 1–2 ở trên) | Quyết định thiết kế (Decided) | Sửa ở đâu (prompt vN / UI / logic ước tính) | Đã sửa? |
|---|---|---|---|
| [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ ] |
| [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ ] |

- Điều muốn test tiếp ở người sau: [ĐIỀN SAU KHI THỬ THẬT]

---

## Tổng hợp sau 3 người thử

> Điền sau khi đã xong cả 3 lượt. Chỉ tổng hợp những gì đã có ở trên, không thêm suy đoán mới.

| | A (User-led) | B (Proactive) | C (Collaborative) |
|---|---|---|---|
| Số người chọn | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Hành vi lặp lại ở ≥ 2 người (tầng 1) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Đánh đổi được nêu | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |
| Bối cảnh muốn dùng (BOUNDARY) | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] | [ĐIỀN SAU KHI THỬ THẬT] |

- **Trả lời QUESTION** ("đứng ngoài / chủ động / hỏi lại"): [ĐIỀN SAU KHI THỬ THẬT]
- **Next design decision** (không phải "validated"): [ĐIỀN SAU KHI THỬ THẬT]
- **Điều vẫn chưa biết, cần vòng thử sau:** [ĐIỀN SAU KHI THỬ THẬT]
- **Giới hạn của vòng thử này** (số người, ai thử, dữ liệu mock, chế độ AI…): [ĐIỀN SAU KHI THỬ THẬT]
