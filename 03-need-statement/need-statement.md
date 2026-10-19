# 03 – Need statement

Trạng thái: **v0.1 (nháp trước phỏng vấn)**. Hướng về giả thuyết H2 (sự bất định thông tin khi chờ) trong `02-journey-map/journey-map.md`. Sau khi có P1–P3, chọn lại giữa bản chính và hai biến thể, hoặc đổi hẳn hướng nếu bằng chứng ủng hộ giả thuyết khác. Bằng chứng nằm ở `bang-chung.md`.

## 1. Need statement chính (v0.1)

Mẫu Biodesign: **Cách để [outcome] cho [population] gặp [problem]**.

> **Cách để người bệnh biết được mình đang ở đâu và còn phải chờ khoảng bao lâu, vì sao, trong quãng từ lúc check-in đến khi được gọi vào phòng khám (kể cả lúc chờ kết quả cận lâm sàng) cho người bệnh khám ngoại trú gặp tình trạng chỉ biết mình đã check-in mà không có hình dung nào về lượt của mình.**

Dạng ngắn dùng trên slide:

> Cách để người bệnh ngoại trú biết mình đang ở đâu và còn chờ bao lâu, vì sao, cho người bệnh đang chờ khám gặp sự bất định về lượt của mình.

## 2. Giải thích từng thành phần P-P-O

| Thành phần | Trong need statement | Vì sao viết vậy | Cần kiểm chứng gì |
|---|---|---|---|
| **Outcome** (kết quả mong muốn) | Người bệnh biết mình đang ở đâu, còn chờ khoảng bao lâu, vì sao | Là trạng thái của người bệnh sau khi vấn đề được giải, không phải một tính năng. Dùng "khoảng bao lâu" thay vì "chính xác bao lâu" để không hứa điều chưa biết có làm được hay không. Cụm "vì sao" tách riêng để giữ chỗ cho H4 (thứ tự gọi trông không công bằng) | Phỏng vấn: người bệnh thực sự cần cả ba thứ (vị trí, thời lượng, lý do) hay chỉ một? |
| **Population** (nhóm người) | Người bệnh khám ngoại trú, từ check-in đến khi được gọi vào phòng, gồm cả lúc chờ kết quả cận lâm sàng | Gắn với một khoảnh khắc cụ thể thay vì "người bệnh nói chung". Không thu hẹp theo bệnh/khoa vì chưa có bằng chứng nhóm nào chịu nặng nhất. Người nhà đi cùng chưa được tính, xem mục 4 | Nhóm nào chịu nặng nhất (người già, đi một mình, đi cùng con nhỏ...)? Người nhà có phải người chờ thật sự? |
| **Problem** (vấn đề) | Chỉ biết đã check-in, không có hình dung gì về lượt của mình | Mô tả tình trạng hiện tại ở góc nhìn người bệnh (không biết gì), không mô tả thiếu sót của hệ thống. Không nói "thiếu ứng dụng", "thiếu màn hình" vì như vậy là ngầm chỉ giải pháp | H2 có đứng vững không so với H1, H3, H4? Xem `bang-chung.md` |

### Vì sao không nêu giải pháp

- Biodesign yêu cầu need statement chỉ gồm vấn đề, nhóm người và kết quả mong muốn. Giải pháp nằm ở bước sau, sau khi vấn đề được xác nhận. Day 17: "Một solution được giao không phải là một problem đã được chứng minh."
- Mỗi cách giải thích về khó chịu khi chờ dẫn tới nhiều cách giải khác nhau (Day 17: cùng một hành vi, nhiều cách giải thích, mỗi cách một hướng giải). Nếu viết giải pháp vào need statement, ta khóa hướng đi trước khi phân xử giữa H1–H4.
- Câu trên đã được rà để không chứa tên công cụ, kênh, thiết bị hay công nghệ cụ thể. Các từ như "biết", "vị trí", "còn chờ bao lâu" mô tả trạng thái người bệnh, không mô tả cách đạt được trạng thái đó.
- Tự kiểm: bỏ câu need statement ra, hỏi "có cách nào khác để đạt cùng outcome không?". Nếu có (điều dưỡng báo trực tiếp, bảng hiển thị, thay đổi quy trình...), câu đang đủ rộng để không chỉ vào một giải pháp.

## 3. Hai biến thể để chọn sau phỏng vấn

### Biến thể A: hẹp hơn, chỉ quãng chờ kết quả cận lâm sàng

> Cách để người bệnh biết kết quả cận lâm sàng của mình đã tới đâu và khi nào cần quay lại phòng khám, cho người bệnh khám ngoại trú đang chờ lấy mẫu, chụp hoặc chờ kết quả gặp tình trạng không biết mình đang chờ gì và chờ bao lâu.

- **Chọn A khi:** P1–P3 cho thấy khó chịu rõ nhất rơi vào quãng chờ máy và chờ kết quả (PD-5, PD-6, PD-7) và ít kể về chờ gọi tên lần đầu. Phù hợp với quan sát CarePath rằng phần lớn thời gian mất ở chờ máy và chờ kết quả.
- **Ưu:** hẹp, dễ đo, dễ làm sâu trong 1 tuần.
- **Nhược:** bỏ qua quãng chờ gọi tên lần đầu; không phải ai cũng có chỉ định cận lâm sàng.

### Biến thể B: rộng hơn, cả chuyến khám ngoại trú

> Cách để người bệnh nắm được các chặng còn lại và thời gian dự kiến của cả chuyến khám ngoại trú, từ lúc đến viện đến lúc ra về, cho người bệnh khám ngoại trú gặp tình trạng chỉ thấy từng hàng chờ rời rạc mà không có hình dung tổng thể.

- **Chọn B khi:** P1–P3 cho thấy cảm giác "mất cả buổi mà không biết còn bao nhiêu chặng" quan trọng hơn từng quãng chờ riêng lẻ (PD-5 mạnh).
- **Ưu:** chạm đúng điều CarePath quan sát về thứ tự đi các phòng.
- **Nhược:** vượt khỏi khoảnh khắc đã chọn "chờ đến lượt khám", dễ rộng quá để làm sâu.

### Nếu bằng chứng ủng hộ giả thuyết khác

| Nếu phỏng vấn nghiêng về | Hướng viết lại need statement (chưa phải bản chính thức) |
|---|---|
| H3 Sợ lỡ lượt | Cách để người bệnh yên tâm rời chỗ trong lúc chờ mà không lo mất lượt, cho người bệnh khám ngoại trú gặp tình trạng phải ngồi yên một chỗ vì sợ bị gọi khi vắng mặt |
| H4 Công bằng | Cách để người bệnh hiểu vì sao thứ tự gọi khác với thứ tự đến, cho người bệnh khám ngoại trú gặp cảm giác thứ tự gọi không công bằng |
| H1 Chờ lâu tuyệt đối | Cách để rút ngắn tổng thời gian chờ của người bệnh khám ngoại trú. Trường hợp này vấn đề thiên về điều phối vận hành hơn là thông tin, cần xem lại có thuộc phạm vi bài tập hay không |

> [CẬP NHẬT SAU PHỎNG VẤN] Ghi lại lựa chọn cuối (bản chính / A / B / hướng khác), lý do, và 1–2 trích dẫn P1–P3 làm căn cứ.

## 4. Định nghĩa vận hành các từ trong câu

| Từ | Định nghĩa dùng trong bài | Ghi chú |
|---|---|---|
| "Đang ở đâu" | Người bệnh biết vị trí tương đối của mình trong hàng chờ hiện tại, và biết mình thuộc chặng nào của chuyến khám | Nếu P1–P3 chỉ cần biết "còn chờ bao lâu" thì rút gọn |
| "Khoảng bao lâu" | Một khoảng ước lượng, không cam kết chính xác. Có thể nói "chưa rõ" khi thực sự chưa rõ | Sai số chấp nhận được phải hỏi người bệnh, không tự đặt |
| "Vì sao" | Lý do thứ tự gọi hoặc lý do chờ (ví dụ phòng đang quá tải, ưu tiên ca khẩn) | Chỉ giữ nếu H4 được xác nhận |
| "Người bệnh khám ngoại trú" | Người đến khám theo lượt trong ngày, không nằm viện | Chưa gồm người nhà, chưa gồm cấp cứu |

## 5. Bảng định lượng hóa (theo Ngày 2: hiện trạng, mục tiêu, cách đo)

Nguyên tắc: không có con số nào được điền khi chưa đo. Ô `___` chờ dữ liệu từ P1–P3 hoặc từ thực địa sau này. Mục tiêu ghi dạng khung, chốt ngưỡng sau khi có hiện trạng.

Chỉ số đầu ra (kết quả cần cải thiện) và chỉ số đầu vào (đòn bẩy) được tách riêng, tránh nhầm một chỉ số đầu vào tăng với giá trị thật.

| Chỉ số | Loại | Hiện trạng | Mục tiêu | Cách đo | Nguồn dữ liệu |
|---|---|---|---|---|---|
| T1. Thời gian chờ từ check-in đến vào khám lần 1 | Bối cảnh (không phải mục tiêu chính của need này) | ___ phút (đo từ phỏng vấn) | Không đặt mục tiêu giảm ở giai đoạn này. Chỉ dùng làm mốc | Người bệnh tự kể theo lần gần nhất; sau này có thể đo bằng mốc thời gian | P1–P3; sau này dữ liệu hệ thống đã khử định danh |
| T2. Tổng thời gian chờ từ check-in đến ra về | Bối cảnh | ___ phút | Như trên | Như trên | P1–P3 |
| U1. Tỷ lệ lúc chờ người bệnh nói là "không biết mình đang ở đâu / còn chờ bao lâu" | **Đầu ra chính** | ___% các lần chờ (từ P1–P3 chỉ có vài người, nên chỉ coi là chỉ báo, không phải tỷ lệ thống kê) | Giảm có ý nghĩa so với hiện trạng; ngưỡng cụ thể: ___ (đặt sau khi có hiện trạng) | Câu hỏi 1 điểm sau khi chờ: "Lúc chờ, bạn có biết mình còn chờ khoảng bao lâu không?" (có / không / đoán) | Phỏng vấn P1–P3; khảo sát ngắn ở vòng thử nghiệm |
| U2. Mức bực bội / bất an khi chờ (tự đánh giá) | **Đầu ra chính** | ___ / 5 (thang tự đánh giá) | Giảm ___ điểm so với hiện trạng | Thang 1–5, hỏi ngay sau quãng chờ; so sánh trước và sau cải tiến | P1–P3, vòng thử |
| U3. Số lần người bệnh phải hỏi nhân viên / người xung quanh để biết tình hình chờ | Đầu ra phụ (đo hành vi, mạnh hơn lời nói) | ___ lần mỗi chuyến | Giảm | Người bệnh kể lại sự kiện cụ thể gần nhất; hoặc quan sát | P1–P3 |
| U4. Tỷ lệ người bệnh rời chỗ trong lúc chờ mà bị lỡ lượt, hoặc không dám rời chỗ | Đầu ra phụ (liên quan H3) | ___ | Giảm lỡ lượt, không buộc tăng rời chỗ | Người bệnh kể sự kiện | P1–P3 |
| I1. Mức đúng của thông tin dự kiến người bệnh nhận được (chênh lệch giữa dự kiến và thực tế) | **Đầu vào** (đòn bẩy, chỉ có nghĩa nếu có giải pháp) | Chưa có, vì chưa có thông tin dự kiến nào được cung cấp | Chênh lệch trong ngưỡng người bệnh chấp nhận, ngưỡng: ___ (hỏi người bệnh, không tự đặt) | So sánh thời gian dự kiến với thời gian thực | Chỉ đo được khi có prototype hoặc pilot |

Lưu ý về bẫy chỉ số (Ngày 2): U1 giảm không đồng nghĩa người bệnh yên tâm hơn nếu thông tin sai nhiều. Vì vậy cần đo song song U2 (cảm nhận) và I1 (độ đúng). Nếu thông tin cho người bệnh đúng ít mà vẫn làm U1 tăng "biết", đó là tín hiệu xấu, không phải thành công.

> [CẬP NHẬT SAU PHỎNG VẤN] Điền cột "Hiện trạng" từ P1–P3. Với mỗi số, ghi rõ: số thật (người bệnh kể lại lần cụ thể), hay ước lượng. Những câu "tùy ngày", "không nhớ số cụ thể" thì ghi nguyên văn, không ép ra con số.

## 6. Nguồn và giới hạn

- Hướng đề xuất (bất định thông tin) xuất phát từ quan sát CarePath 7/2026 và là giả thuyết của tác giả, không phải kết luận từ dữ liệu phỏng vấn mới.
- Cỡ mẫu P1–P3 rất nhỏ: chỉ đủ để phân xử giả thuyết định tính, không đủ để chốt số liệu thống kê.
- Bối cảnh quan sát ban đầu là bệnh viện công, không phải Vinmec; cần đối chiếu với trải nghiệm đi khám ở các cơ sở khác nhau.
- Phần do AI hỗ trợ: AI giúp rà cấu trúc và kiểm tra câu không chứa giải pháp; nội dung giả thuyết đến từ tác giả.
