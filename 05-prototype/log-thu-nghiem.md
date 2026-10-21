# Log thử nghiệm prototype: Trợ lý hàng chờ (A/B/C)

> Log được ghi sau mỗi phiên thử; các ô trống sẽ được điền từ dữ liệu phiên thật.

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

### 4 tầng evidence

| Tầng | Loại | Ví dụ dạng ghi | Ghi vào |
|---|---|---|---|
| 1 | Việc đã xảy ra (hành vi) | "Bấm chip Ăn trưa trước khi đọc thẻ trạng thái" | **OBSERVED** |
| 2 | Lời nói tại hiện trường, lúc đang làm | "…sát giờ à, thôi chắc không đi" | **OBSERVED (nói lúc làm)** |
| 3 | Giải thích sau khi được hỏi | "Tôi chọn C vì nó hỏi tôi trước" | **INTERPRETED** |
| 4 | Dự đoán về bản thân / tương lai | "Lần sau chắc tôi sẽ bật thông báo" | **STILL UNPROVEN** |

Một hành động ở tầng 1 nặng hơn mười câu ở tầng 4. **Quyết định thiết kế** ghi riêng ở mục "Tôi sửa gì sau lượt này".

---

## Người thử T1

- **Thông tin (ẩn danh):** nữ, nhóm 18-24, thạo smartphone; lần chờ khám gần nhất ~6 tháng trước; KHÔNG trùng P1–P4 (người thứ 5 độc lập); quan hệ: bạn bè. Không ghi bệnh.
- **Ngày / thời lượng / hình thức:** 10/2026, buổi sáng; phần thử A/B/C ~15 phút; người thử tự cầm máy (tự bấm cả nút ⏩ trên bảng điều phối).
- **Đồng ý tham gia:** [x] Có · Ghi âm: [ ] Có [x] Không
- **Thứ tự phương án:** A → B → C (cuối phiên tự bấm lướt lại cả 3 tab để so sánh)
- **Chế độ AI:** [x] AI thật (model: gpt-4o-mini) [ ] Kịch bản mẫu · **Phiên bản prompt:** v1
- **File log phiên:** `log-T1.json` (đoạn chạy không tương tác ở đầu file là lúc người điều phối tự kiểm tra máy, không tính vào phiên)

### 01 COMFORT
- Đã đọc script, người thử có câu hỏi gì: Không có câu hỏi.

### 02 CONTEXT (≈2'): lần chờ gần nhất
- Chuyện đã xảy ra: đến viện lấy số → ngồi đợi → lướt điện thoại trong lúc chờ; thường đi khám cùng người nhà nên không sợ mất lượt khi đi vệ sinh (người nhà giữ chỗ); có thói quen đi thật sớm để được vào sớm khỏi chờ. — Khớp hai mẫu của vòng phỏng vấn: "tấm đệm người nhà" (P1) và "đệm thời gian" (P4).
- Trích dẫn nguyên văn đáng chú ý: không ghi kịp nguyên văn ở nhịp này.

### 03 TASK + 04 OBSERVE

| Quan sát | A | B | C |
|---|---|---|---|
| First action (thao tác đầu tiên, sau bao nhiêu giây) | Mở khung "Hỏi trợ lý" rồi bấm **chip gợi ý** "Còn bao lâu nữa đến lượt mình?" (không tự gõ; chip sau khi mở khung ~4 giây) | Bấm ⏩ tua nhanh (~27 giây), chỉ đọc thông báo đẩy, không mở gì khác | Bấm **chip tình huống** "đi vệ sinh ~5 phút" (~14 giây) |
| Hesitation (dừng / đọc lại ở đâu) | Khựng lâu nhất lúc MỚI VÀO: đọc vùng ước tính thời gian và banner "còn bao nhiêu người"; dừng lại hỏi về khoảng 35–65' và nhãn "dao động" | Không ghi nhận | Khựng khi khối khẩn cấp hiện dù chỉ nói chuyện đi vệ sinh |
| Đọc hay bỏ qua evidence | ĐỌC khoảng thời gian + nhãn tin cậy (nhưng không tự hiểu, phải hỏi — xem Lời nói); **KHÔNG đọc** banner giới hạn "prototype học tập / không phải cam kết" | Đọc các push (gồm push hội chẩn có lý do), không phản ứng đặc biệt | Đọc thẻ KỊP; tự hỏi trong chat "sao thời gian ước tính bị chênh nhau 30p" và chấp nhận lời giải thích (hội chẩn, nhịp không ổn định) |
| Misinterpretation (hiểu sai chỗ nào) | Tưởng các **chip gợi ý bấm được tiếp**: "sao k đc bấm tiếp mấy cái option mẫu khác nữa" (chip biến mất sau khi dùng) | — | Tưởng đã đổi được ngưỡng nhắc sang "còn 6 người" vì bot xác nhận — thực tế rule vẫn đặt 3 (xem Sự cố) |
| Correction / recovery | Bấm nút "gọi nhân viên" nhưng là để KHÁM PHÁ ("cái nút nhân viên y tế này để làm gì"), không phải cần thật | Bấm "gọi nhân viên" lần nữa (cũng kiểu khám phá) | Chủ động xin đổi ngưỡng nhắc ("khi còn 6 người thì nhắc"); khi bot từ chối báo hộ thì bỏ qua, tự tua tiếp |
| Cần cứu hộ? | Không | Không | Không |
| Quyết định cuối của task | **Đi ăn** — sau khi thử lại với con số của mình: bot nói 40' là SÁT GIỜ → cô ấy hỏi "nếu ăn 10p thì sao" → KỊP → chốt đi | (B không có kênh hỏi; quyết định giữ nguyên từ A, dựa các mốc push) | **Đi** — tình huống vệ sinh 5' được trả lời KỊP ngay |
| Thời gian hoàn thành task | ~2' tương tác + tua nhanh đến lúc được gọi (~4' cả lượt) | ~2' (toàn tua nhanh + đọc push) | ~4' (nhiều hội thoại nhất) |
| AI trả lời sai / lạ (AI thật) | Tự **giả định đi ăn 40 phút** khi người thử chưa hề nói đi bao lâu: "Nếu bạn đi ăn trưa khoảng 40 phút, thì… SÁT GIỜ" | — (push là mẫu soạn sẵn) | (1) Hứa "Mình sẽ nhắc bạn khi còn 6 người nhé!" nhưng nhắc thật nổ lúc còn 3, rồi tự khai "mình đã nhắc bạn khi còn 3 người"; (2) gắn giọng khẩn cấp vào các câu chỉ nói chuyện đi vệ sinh |

**Lời nói tại hiện trường (nguyên văn, ghi kèm phương án):**
- A: "cái nút nhân viên y tế này để làm gì" · "sao chỗ này thời gian chênh quá vậy tận 30 phút (35–65 phút), bình thường t thấy có 10 phút là lâu lắm rồi đó" · "nhãn dao động này là sao" · "đi ăn trưa gì tận 40 phút vậy, 10 phút thôi" · "sao k đc bấm tiếp mấy cái option mẫu khác nữa"
- B: (không có phát ngôn đáng chú ý — lượt ít tương tác nhất)
- C: "ko có bị khó thở, ý là đi vệ sinh lâu" · "ko cần báo vấn đề riêng tư" (khi khối khẩn cấp hiện nhầm) · cuối phiên: "ê thế ba cái này khác nhau chỗ nào"

### 05 COMPARE

| Câu hỏi | Trả lời (nguyên văn nếu được) |
|---|---|
| **CHOICE:** chọn A, B hay C? Vì sao? | "t thì t chọn cái phương án C… vì custom được" |
| **TRADE-OFF:** chọn nó thì chấp nhận đánh đổi gì? | KHÔNG HỎI ĐƯỢC ở phiên này (sót nhịp) — đưa vào việc cần làm ở người thử sau |
| **BOUNDARY:** trường hợp nào muốn phương án khác? | Tự nêu theo tuổi/mức thạo công nghệ: "mấy người kiểu trẻ thạo công nghệ thì cx chọn C vì custom được, nhưng người lớn thì họ chọn B vì không phải custom chỉnh sửa thao tác nhiều" |
| Tiêu chí người thử thật sự dùng để so sánh | Mức được tùy chỉnh/điều khiển so với số thao tác phải làm. Lưu ý: phải HỎI mới phân biệt được 3 phương án ("ê thế ba cái này khác nhau chỗ nào") — khác biệt cơ chế không tự lộ qua UI |

### Bảng evidence 4 tầng: T1

| Tầng | Nội dung | Phương án liên quan |
|---|---|---|
| 1 · OBSERVED (hành vi) | Bấm chip gợi ý thay vì tự gõ (A, C); **thử lại ước tính với con số của mình** ("nếu ăn 10p thì sao") rồi mới quyết (A); chủ động xin đổi ngưỡng nhắc (C); tự bấm tua nhanh liên tục cả 3 tab; bấm nút nhân viên y tế 2 lần để khám phá; chốt ĐI ĂN sau khi thấy KỊP | A, C |
| 2 · OBSERVED (nói lúc làm) | "sao chênh tận 30 phút… 10 phút là lâu lắm rồi"; "nhãn dao động này là sao"; "đi ăn trưa gì tận 40 phút, 10 phút thôi"; "sao k đc bấm tiếp option mẫu"; "ko có bị khó thở, ý là đi vệ sinh lâu"; "ê thế ba cái này khác nhau chỗ nào" | A, C |
| 3 · INTERPRETED (giải thích sau) | Chọn C vì "custom được" | C |
| 4 · STILL UNPROVEN (dự đoán) | "Người trẻ thạo công nghệ chọn C, người lớn chọn B"; muốn có nút báo cho bác sĩ là sẽ đến muộn nếu không về kịp | B, C |

### Sự cố an toàn / ngoài phạm vi (nếu có)
- Người thử có hỏi câu y khoa không?: Không hỏi câu y khoa thật nào; handoff không kích hoạt.
- Khối khẩn cấp có hiện đúng hay sai không: **HIỆN SAI 3 lần liên tiếp ở C** — (1) bot gắn giọng khẩn cấp cho câu "sắp đến lượt của tôi, nhưng tôi chưa đi vệ sinh xong"; (2) từ khóa "khó thở" trong câu PHỦ ĐỊNH "ko có bị khó thở, ý là đi vệ sinh lâu" vẫn kích khối đỏ; (3) "ko cần báo vấn đề riêng tư" vẫn bị nhắc đi gặp nhân viên y tế. Đúng hướng thiên-nhạy đã chọn (bỏ lọt đắt hơn báo nhầm) nhưng chuỗi 3 lần nhầm liên tiếp làm người thử bực — cần xử lý phủ định.

### Tôi sửa gì sau lượt này
| Vấn đề quan sát được (dẫn về tầng 1–2 ở trên) | Quyết định thiết kế (Decided) | Sửa ở đâu (prompt vN / UI / logic ước tính) | Đã sửa? |
|---|---|---|---|
| Khối khẩn cấp bắn nhầm khi từ khóa nằm trong câu phủ định ("ko có bị khó thở") và bot tự gắn giọng khẩn cấp cho chuyện rời chỗ | Bộ lọc từ khóa bỏ qua từ khóa đứng ngay sau từ phủ định (không/ko/k/chưa/hết/đâu có); prompt cấm model dùng giọng khẩn cấp khi người dùng chỉ nói việc rời chỗ/sinh hoạt | Logic `index.html` + prompt v2 | [x] |
| AI HỨA "nhắc khi còn 6 người" nhưng rule vẫn nổ ở 3, rồi tự khai ngược — lớp diễn đạt hứa thay lớp cơ chế | App parse "khi còn N người" trong tin nhắn để đặt ngưỡng nhắc THẬT; prompt chỉ cho phép xác nhận ngưỡng mà hệ thống báo đã đặt được | Logic `index.html` + prompt v2 | [x] |
| Bot tự giả định "đi ăn 40 phút" khi người thử chưa nói đi bao lâu | Chưa biết thời lượng thì HỎI LẠI trước, không giả định rồi phán KỊP/SÁT GIỜ | Prompt v2 (phương án A) | [x] |
| "sao k đc bấm tiếp mấy cái option mẫu khác nữa" — chip gợi ý biến mất sau một lần dùng | Giữ chip hiển thị, cho bấm nhiều lần | UI `index.html` | [x] |
| Khoảng 30' và nhãn "dao động" phải hỏi mới hiểu; banner giới hạn không ai đọc | Thêm dòng giải thích ngắn ngay dưới ước tính ("khoảng rộng vì nhịp khám đang không ổn định"); banner giới hạn cân nhắc chuyển thành dòng gắn trong thẻ trạng thái | UI — để người thử sau kiểm chứng trước khi làm | [ ] |
| Muốn nút "báo cho bác sĩ là sẽ đến muộn" | Ghi nhận là tín hiệu tầng 4; đụng quy trình vận hành (ai nhận tin báo?) — không làm trong prototype, ghi vào câu hỏi cho sprint | — | [ ] |

- Điều muốn test tiếp ở người sau: (1) hỏi đủ nhịp TRADE-OFF (phiên này sót); (2) người lớn tuổi/ít thạo công nghệ để kiểm chứng dự đoán "người lớn chọn B"; (3) sau khi sửa khẩn cấp + ngưỡng nhắc, lặp lại đúng tình huống "đi vệ sinh lâu" xem còn bắn nhầm không; (4) người thử có tự nhận ra khác biệt A/B/C không nếu không ai giải thích.

---

## Người thử T2

- **Thông tin (ẩn danh: nhóm tuổi, mức quen smartphone, lần chờ khám gần nhất bao lâu trước; không ghi bệnh):**
- **Ngày / thời lượng / hình thức:** 
- **Đồng ý tham gia:** [ ] Có · Ghi âm: [ ] Có [ ] Không
- **Thứ tự phương án:** B → C → A
- **Chế độ AI:** [ ] AI thật (model: ____ ) [ ] Kịch bản mẫu · **Phiên bản prompt:** v__
- **File log phiên:** `log-T2.json`

### 01 COMFORT
- Đã đọc script, người thử có câu hỏi gì:

### 02 CONTEXT (≈2'): lần chờ gần nhất
- Chuyện đã xảy ra (event → behavior → workaround → consequence):
- Trích dẫn nguyên văn đáng chú ý: ""

### 03 TASK + 04 OBSERVE

| Quan sát | A | B | C |
|---|---|---|---|
| First action (thao tác đầu tiên, sau bao nhiêu giây) |  |  |  |
| Hesitation (dừng / đọc lại ở đâu) |  |  |  |
| Đọc hay bỏ qua evidence (khoảng thời gian, nhãn Ổn định/Dao động, lý do hội chẩn, thẻ KỊP/SÁT GIỜ) |  |  |  |
| Misinterpretation (hiểu sai chỗ nào) |  |  |  |
| Correction / recovery (sửa thời gian, Ẩn/Tắt thông báo, bỏ nhắc, gọi nhân viên) |  |  |  |
| Cần cứu hộ? (dùng câu rescue nào) |  |  |  |
| Quyết định cuối của task (đi ăn / không / đi việc khác) và dựa vào đâu |  |  |  |
| Thời gian hoàn thành task |  |  |  |
| AI trả lời sai / lạ (trích nguyên văn, chế độ AI thật hay mẫu) |  |  |  |

**Lời nói tại hiện trường (nguyên văn, ghi kèm phương án):**
- A: ""
- B: ""
- C: ""

### 05 COMPARE

| Câu hỏi | Trả lời (nguyên văn nếu được) |
|---|---|
| **CHOICE:** chọn A, B hay C? Vì sao? |  |
| **TRADE-OFF:** chọn nó thì chấp nhận đánh đổi gì? |  |
| **BOUNDARY:** trường hợp nào muốn phương án khác? (ví dụ đi một mình / có con nhỏ / đang mệt / ít thời gian) |  |
| Tiêu chí người thử thật sự dùng để so sánh |  |

### Bảng evidence 4 tầng: T2

| Tầng | Nội dung | Phương án liên quan |
|---|---|---|
| 1 · OBSERVED (hành vi) |  |  |
| 2 · OBSERVED (nói lúc làm) |  |  |
| 3 · INTERPRETED (giải thích sau) |  |  |
| 4 · STILL UNPROVEN (dự đoán) |  |  |

### Sự cố an toàn / ngoài phạm vi (nếu có)
- Người thử có hỏi câu y khoa không? AI xử lý thế nào? (handoff có hiện không):
- Khối khẩn cấp có hiện đúng hay sai không:

### Tôi sửa gì sau lượt này
| Vấn đề quan sát được (dẫn về tầng 1–2 ở trên) | Quyết định thiết kế (Decided) | Sửa ở đâu (prompt vN / UI / logic ước tính) | Đã sửa? |
|---|---|---|---|
|  |  |  | [ ] |
|  |  |  | [ ] |

- Điều muốn test tiếp ở người sau:

---

## Người thử T3

- **Thông tin (ẩn danh: nhóm tuổi, mức quen smartphone, lần chờ khám gần nhất bao lâu trước; không ghi bệnh):**
- **Ngày / thời lượng / hình thức:** 
- **Đồng ý tham gia:** [ ] Có · Ghi âm: [ ] Có [ ] Không
- **Thứ tự phương án:** C → A → B
- **Chế độ AI:** [ ] AI thật (model: ____ ) [ ] Kịch bản mẫu · **Phiên bản prompt:** v__
- **File log phiên:** `log-T3.json`

### 01 COMFORT
- Đã đọc script, người thử có câu hỏi gì:

### 02 CONTEXT (≈2'): lần chờ gần nhất
- Chuyện đã xảy ra (event → behavior → workaround → consequence):
- Trích dẫn nguyên văn đáng chú ý: ""

### 03 TASK + 04 OBSERVE

| Quan sát | A | B | C |
|---|---|---|---|
| First action (thao tác đầu tiên, sau bao nhiêu giây) |  |  |  |
| Hesitation (dừng / đọc lại ở đâu) |  |  |  |
| Đọc hay bỏ qua evidence (khoảng thời gian, nhãn Ổn định/Dao động, lý do hội chẩn, thẻ KỊP/SÁT GIỜ) |  |  |  |
| Misinterpretation (hiểu sai chỗ nào) |  |  |  |
| Correction / recovery (sửa thời gian, Ẩn/Tắt thông báo, bỏ nhắc, gọi nhân viên) |  |  |  |
| Cần cứu hộ? (dùng câu rescue nào) |  |  |  |
| Quyết định cuối của task (đi ăn / không / đi việc khác) và dựa vào đâu |  |  |  |
| Thời gian hoàn thành task |  |  |  |
| AI trả lời sai / lạ (trích nguyên văn, chế độ AI thật hay mẫu) |  |  |  |

**Lời nói tại hiện trường (nguyên văn, ghi kèm phương án):**
- A: ""
- B: ""
- C: ""

### 05 COMPARE

| Câu hỏi | Trả lời (nguyên văn nếu được) |
|---|---|
| **CHOICE:** chọn A, B hay C? Vì sao? |  |
| **TRADE-OFF:** chọn nó thì chấp nhận đánh đổi gì? |  |
| **BOUNDARY:** trường hợp nào muốn phương án khác? (ví dụ đi một mình / có con nhỏ / đang mệt / ít thời gian) |  |
| Tiêu chí người thử thật sự dùng để so sánh |  |

### Bảng evidence 4 tầng: T3

| Tầng | Nội dung | Phương án liên quan |
|---|---|---|
| 1 · OBSERVED (hành vi) |  |  |
| 2 · OBSERVED (nói lúc làm) |  |  |
| 3 · INTERPRETED (giải thích sau) |  |  |
| 4 · STILL UNPROVEN (dự đoán) |  |  |

### Sự cố an toàn / ngoài phạm vi (nếu có)
- Người thử có hỏi câu y khoa không? AI xử lý thế nào? (handoff có hiện không):
- Khối khẩn cấp có hiện đúng hay sai không:

### Tôi sửa gì sau lượt này
| Vấn đề quan sát được (dẫn về tầng 1–2 ở trên) | Quyết định thiết kế (Decided) | Sửa ở đâu (prompt vN / UI / logic ước tính) | Đã sửa? |
|---|---|---|---|
|  |  |  | [ ] |
|  |  |  | [ ] |

- Điều muốn test tiếp ở người sau:

---

## Tổng hợp sau 3 người thử

| | A (User-led) | B (Proactive) | C (Collaborative) |
|---|---|---|---|
| Số người chọn |  |  |  |
| Hành vi lặp lại ở ≥ 2 người (tầng 1) |  |  |  |
| Đánh đổi được nêu |  |  |  |
| Bối cảnh muốn dùng (BOUNDARY) |  |  |  |

- **Trả lời QUESTION** ("đứng ngoài / chủ động / hỏi lại"):
- **Next design decision** (không phải "validated"):
- **Điều vẫn chưa biết, cần vòng thử sau:** 
- **Giới hạn của vòng thử này** (số người, ai thử, dữ liệu mock, chế độ AI…):
