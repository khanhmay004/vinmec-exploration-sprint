# 05 — Prototype: Trợ lý hàng chờ (A/B/C)

> **Prototype học tập, không phải sản phẩm Vinmec.** Dữ liệu hàng chờ là giả lập. Prototype không đưa lời khuyên y khoa.
> Mã nguồn `index.html`, prompt và khung tài liệu trong thư mục này được soạn với sự hỗ trợ của AI (Claude). Dữ liệu thử nghiệm trong `log-thu-nghiem.md` chỉ được điền sau khi thử với người thật, không do AI tạo.

Đây là một màn hình mô phỏng trong app đặt khám, dành cho người bệnh **đang ngồi chờ sau khi check-in**. Có 3 phương án A/B/C cho cùng một khoảnh khắc. Chúng chỉ khác nhau ở **cơ chế** AI tham gia.

| File | Nội dung |
|---|---|
| `index.html` | Prototype một file (HTML + CSS + JS thuần), có AI thật (OpenAI) và chế độ kịch bản mẫu khi offline |
| `prompts.md` | System prompt, prompt riêng cho từng phương án, template context nhúng, lịch sử phiên bản prompt |
| `log-thu-nghiem.md` | Template log thử với 3 người theo 5 nhịp prototype interview |

---

## 1. Cách chạy

1. Mở `index.html` bằng trình duyệt (Chrome/Edge/Safari/Firefox). Không cần build, không cần server.
2. **Không có API key:** app tự chạy ở chế độ **"Kịch bản mẫu"** (nhãn vàng trên khung chat). Các câu trả lời được soạn sẵn nhưng vẫn tính theo hàng chờ hiện tại, nên demo offline vẫn được.
3. **Dùng AI thật** — một trong hai cách:
   - **Cách nhanh (khuyên dùng khi tự thử trên máy mình):** copy `config.local.example.js` thành `config.local.js`, dán key vào — app tự nạp key mỗi lần mở, người thử không phải thao tác gì. File này nằm trong `.gitignore`, không bao giờ lên repo.
   - **Cách thủ công:** bấm ⚙ → dán OpenAI API key → Lưu (lưu trong `localStorage`, ưu tiên hơn `config.local.js` nếu có cả hai). Nhãn chuyển sang xanh `AI thật · gpt-4o-mini`.
   - Key chỉ nằm trên máy chạy app và được gửi thẳng tới `https://api.openai.com/v1/chat/completions`. Không có trong mã nguồn repo. Đừng dùng trên máy dùng chung; thử xong bấm "Xóa key" (hoặc xoá `config.local.js`).
   - Nếu gọi API lỗi (sai key, hết quota, mất mạng), app báo lỗi trong chat rồi trả lời tạm bằng kịch bản mẫu.
4. **Đổi model:** sửa hằng số ở đầu `<script>` trong `index.html`:
   ```js
   const MODEL = 'gpt-4o-mini';
   ```
   Hoặc nhập tên model ở ô "Model" trong ⚙ (chỉ áp dụng cho trình duyệt đó, để trống thì dùng `MODEL`).
5. **Bảng điều phối** (bên phải điện thoại trên desktop, bên dưới trên mobile) là chỗ cho người phỏng vấn dùng:
   - Tốc độ mô phỏng (mặc định 1 phút mô phỏng / 10 giây), `⏩ +5 phút`, `🩺 Kích hoạt hội chẩn`, `↺ Reset điểm xuất phát`.
   - "Đổi tab = reset" bật sẵn: mỗi phương án bắt đầu từ cùng một điểm, để người thử không mang câu trả lời từ A sang B.
   - **Log phiên**: tự ghi mọi thao tác (chip đã bấm, tin nhắn, thông báo, ẩn/tắt thông báo, gọi nhân viên, tua nhanh…) kèm giờ thật và giờ mô phỏng. Copy hoặc tải JSON để điền phần OBSERVED trong `log-thu-nghiem.md`.
   - Nên kéo cửa sổ để người thử chỉ thấy khung điện thoại, hoặc gập phần "Mô tả 3 phương án".
6. Nút `⏩ Tua nhanh` trong điện thoại là cho người thử bấm, để họ thấy hàng chờ chạy mà không phải ngồi đợi.

---

## 2. Thiết kế thử nghiệm (Question → Contrast → Evidence)

### QUESTION
> Khi đang chờ khám và không biết gì về hàng chờ, người bệnh muốn AI **đứng ngoài chờ được hỏi**, **chủ động báo**, hay **hỏi lại trước khi đoán**?

Kết quả mong đợi là **quyết định thiết kế tiếp theo**, không phải "validated".

### CONSTANTS (giữ nguyên giữa A/B/C)
| Hằng số | Giá trị |
|---|---|
| Bối cảnh | Đã check-in phòng khám Nội tổng quát, phòng 2.07, số thứ tự **2451** |
| Dữ liệu hàng chờ | Đang khám số 2443, **7 người trước**, cùng chuỗi thời lượng các lượt (có một lượt 16 phút), cùng sự kiện hội chẩn ở phút mô phỏng thứ 12 |
| Mục tiêu người dùng | Quyết định được: ngồi tiếp / đi vệ sinh / đi ăn mà không sợ lỡ lượt |
| Task giao | "Hãy quyết định xem bạn có kịp đi ăn trưa không" |
| Màn hình chung | Banner kỳ vọng, thẻ trạng thái (số người trước, khoảng thời gian, mức tin cậy, lý do), nút gọi nhân viên, disclaimer, footer |
| Logic ước tính | Cùng một hàm `estimate()` và `feasibility()`. AI không tự làm phép tính |

Thẻ trạng thái giống hệt nhau ở cả 3 phương án, để khác biệt duy nhất nằm ở **cơ chế AI**.

### CONTRAST (chỉ đổi cơ chế)
| | **A — User-led (Standard)** | **B — Proactive (Standard++)** | **C — Collaborative (Wild)** |
|---|---|---|---|
| TRIGGER | Người dùng bấm "💬 Hỏi trợ lý" | AI tự đẩy thông báo theo mốc | AI mở lời bằng một câu hỏi |
| AI ROLE | Đứng ngoài; trả lời khi được hỏi; nếu thiếu thông tin thì tự giả định và nói rõ giả định | Báo khi còn 5 người, còn 2 người, khi hội chẩn bắt đầu/kết thúc, khi một lượt kéo dài bất thường (có giải thích lý do, hoặc nói thật là chưa rõ) | **Ask** (mixed-initiative): "Bạn định đi đâu, mất khoảng bao lâu?" rồi mới kết luận KỊP / SÁT GIỜ / KHÔNG KỊP |
| USER ROLE | Tự biết mình cần hỏi gì | Đọc thông báo, Ẩn, hoặc 🔕 Tắt thông báo (HAX G8 dismissal, G17 global control trong ⚙) | Trả lời câu hỏi, rồi **chọn** có muốn được nhắc khi còn 3 người không (opt-in) |
| RECOVERY | Hỏi lại, gọi nhân viên | Tắt/bật lại thông báo, hỏi trong chat, gọi nhân viên | Tự nhập thời gian khác, nhắn "bỏ nhắc", gọi nhân viên |
| Đánh đổi giả định | Phải tự biết mình cần gì; dễ bỏ lỡ lúc hàng chờ đổi | Dễ gây gián đoạn hoặc phiền | Thêm một bước hỏi–đáp trước khi được giúp |

Kiểm tra "ba bản gần giống": bỏ hết phần hình, ba cơ chế vẫn mô tả khác nhau được (chờ hỏi / tự báo / hỏi trước rồi xin phép).

### EVIDENCE (cần quan sát)
- **First action** ở mỗi phương án: bấm gì đầu tiên, có đọc thẻ trạng thái trước không.
- **Hesitation**: dừng ở đâu, đọc lại chỗ nào.
- **Evidence read/ignored**: có đọc khoảng thời gian, nhãn "Ổn định/Dao động", lý do hội chẩn, thẻ KỊP/SÁT GIỜ không.
- **Correction / recovery**: có sửa thời gian chuyến đi, tắt thông báo, gọi nhân viên không.
- **Quyết định cuối** của task (đi ăn hay không) và họ dựa vào đâu.
- **COMPARE**: chọn gì, vì sao, đánh đổi gì, trường hợp nào muốn phương án khác.

Cách ghi chép theo 4 tầng (OBSERVED / nói lúc làm / INTERPRETED / UNPROVEN) nằm trong `log-thu-nghiem.md`.

---

## 3. HCAI: các nguyên tắc thể hiện ở đâu

| Nguyên tắc | Trong prototype |
|---|---|
| **Expectation** (HAX G1/G2) | Banner cố định: "giúp bạn theo dõi lượt… KHÔNG tư vấn triệu chứng, thuốc hay kết quả". Chip gợi ý câu hỏi (demonstrate possible inputs). Nhãn chế độ AI thật / kịch bản mẫu |
| **Không hứa quá khả năng** | Thời gian luôn là **khoảng** làm tròn 5 phút ("khoảng 40–70 phút nữa"), không bao giờ một con số. Disclaimer cố định dưới khung chat |
| **Categorical confidence** | Nhãn **Ổn định / Dao động**, không dùng %. Khi dao động thì liệt kê lý do |
| **Explainability** (G11) | Hội chẩn: "bác sĩ được mời hội chẩn, tạm dừng khoảng 10–15 phút". Lượt kéo dài: "lâu hơn thường lệ, chưa rõ lý do" (khiêm tốn, không bịa). Thẻ KỊP/SÁT GIỜ ghi rõ phép so sánh |
| **Agency = độ chắc × cost-of-error** | Lỡ lượt là lỗi đắt, nên SÁT GIỜ luôn nghiêng về phía an toàn. Nhắc nhở ở C là opt-in |
| **G10 Scope when in doubt** | C hỏi lại khi thiếu thông tin. A/B nói rõ giả định ("Mình giả định đi ăn mất khoảng 40 phút") |
| **Control & handoff** | Nút "🧑‍⚕️ Gọi nhân viên hỗ trợ" luôn hiện. Câu hỏi y khoa thì từ chối nhẹ nhàng kèm nút "Chuyển nhân viên". Thiếu thông tin (ví dụ quy định lỡ lượt) thì nói thẳng là không biết và chỉ sang quầy |
| **Khẩn cấp** | Từ khóa khẩn cấp (đau ngực, khó thở, ngất…) được bắt **ở phía client, không qua LLM**: hiện khối đỏ "Báo ngay nhân viên y tế gần nhất" và câu trả lời cố định. LLM cũng được dặn trả thẻ `[[EMERGENCY]]` như một lớp an toàn thứ hai |

### Vì sao một phần là quy tắc cố định chứ không để AI làm hết
- **Phép tính kịp/không kịp** (`feasibility()`) chạy bằng JS rồi đưa vào context dưới dạng bảng. LLM chỉ diễn đạt, không tự cộng trừ, để tránh trường hợp "nghe hợp lý nhưng sai".
- **Thông báo chủ động ở B** dùng template, để thời điểm và nội dung giống nhau giữa các người thử. Như vậy biến được test là *cơ chế chủ động*, không phải chất lượng câu chữ của LLM.
- **Khẩn cấp** đi theo luật cố định, vì một lần sai ở đây là failure, không phải error.

---

## 4. Giới hạn của prototype

- **Dữ liệu giả lập**: hàng chờ là một object JS (`SCENARIO`), chưa nối HIS/LIS hay hệ thống gọi số thật. Thời lượng các lượt, sự kiện hội chẩn, lượt kéo dài đều là kịch bản cố định.
- **Mô hình ước tính rất thô**: trung bình 6 lượt gần nhất × số người, nới biên theo hệ số và sự kiện. Chưa tính bác sĩ khác nhau, ca ưu tiên/cấp cứu chen ngang, bệnh nhân quay lại sau cận lâm sàng, giờ nghỉ trưa của phòng khám…
- **Một phòng, một luồng**: chưa có trường hợp người bệnh phải đi nhiều phòng (xét nghiệm → khám → trả kết quả).
- **Gọi nhân viên chỉ là giả lập**: không gửi yêu cầu thật.
- **Bộ lọc y khoa / khẩn cấp dựa trên từ khóa tiếng Việt đã bỏ dấu**: có thể bỏ sót cách diễn đạt lạ, hoặc bắt nhầm. Trong sản phẩm thật cần test distribution riêng và có người duyệt.
- **API key nằm ở browser**: chỉ chấp nhận được cho prototype. Sản phẩm thật phải gọi qua backend.
- **Không lưu dữ liệu sức khỏe**: log phiên chỉ ghi thao tác trên prototype, lưu ở `localStorage` của máy người phỏng vấn. Không hỏi và không ghi thông tin bệnh của người thử (theo ràng buộc 6.4 của đề bài).
- **Thông báo "push"** chỉ là toast trong khung điện thoại, không phải push notification của hệ điều hành.
- Chưa đo trên mạng chậm, trên màn hình nhỏ thật, hay với người lớn tuổi ít dùng smartphone. Đây là nhóm cần thử ở vòng sau.
