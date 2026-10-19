---
marp: true
theme: default
size: 16:9
paginate: true
style: |
  section { font-size: 28px; }
  section.center { text-align: center; justify-content: center; }
  .todo { color: #b45309; font-weight: bold; }
  blockquote { font-size: 1.15em; }
---

<!-- Slide 1: Tiêu đề -->
<!-- _class: center -->

# Chờ đến lượt khám, người bệnh biết mình đang ở đâu?

Thiết kế trợ lý AI báo tiến độ hàng chờ trên MyVinmec

**Võ Huyền Khánh Mây** · K2 · lab coach, đang làm AI cho bài toán y tế (khóa luận, CarePath)

Bài tập 1 tuần · Vinmec Exploration Sprint

---

<!-- Slide 2: Khoảnh khắc chọn -->
# Khoảnh khắc: chờ đến lượt khám

- Chọn **một** khoảnh khắc, không ôm cả hành trình
- Đây là chỗ người bệnh mất nhiều thời gian nhất, và ít biết chuyện gì đang xảy ra
- Hẹp thì làm sâu được: 3 phỏng vấn, 3 phương án, thử với người thật trong một tuần
- Gần với điều mình thấy ở CarePath: khám chỉ vài phút, phần lớn là chờ

<span class="todo">[KIỂM TRA SAU PHỎNG VẤN: lý do chọn còn đúng với P1–P3 không]</span>

---

<!-- Slide 3: Method -->
# Mình đã làm gì

- **Dùng thử MyVinmec**, ghi lại làm gì, thấy gì, vướng ở đâu
- **3 phỏng vấn ẩn danh (P1–P3)** theo Mom Test: hỏi chuyện đã xảy ra, không hỏi ý kiến
- **Journey map** và need statement theo Biodesign
- **Prototype 3 phương án A / B / C** (model GPT, dữ liệu giả lập)
- **Thử với 2–3 người**, ghi log, sửa sau mỗi lượt

---

<!-- Slide 4: Journey map -->
# Journey map và điểm đau

<span class="todo">[CHÈN HÌNH JOURNEY MAP SAU KHI CÓ DỮ LIỆU P1–P3]</span>

- Điểm đau 1: <span class="todo">[ĐIỀN SAU: điểm đau nhiều người kể nhất]</span>
- Điểm đau 2: <span class="todo">[ĐIỀN SAU]</span>
- Cảm xúc chỉ vẽ theo điều người kể, chỗ không có dữ liệu để trống

---

<!-- Slide 5: Insight -->
# Insight từ 3 phỏng vấn (OBSERVED)

<span class="todo">[ĐIỀN SAU: chỉ điền điều đã thấy, nghe, có nguồn P#]</span>

- <span class="todo">[O1: ai làm gì, khi nào, hậu quả gì. Nguồn P#]</span>
- <span class="todo">[O2]</span>
- <span class="todo">[O3]</span>

Chỉ nói "trong 3 cuộc, n người kể...". Không nói "người bệnh Việt Nam...".

---

<!-- Slide 6: Need statement -->
<!-- _class: center -->

# Need statement

> **Cách để người bệnh ngoại trú biết mình đang ở đâu và còn chờ khoảng bao lâu, vì sao, cho người bệnh đang chờ khám gặp sự bất định về lượt của mình.**

<span class="todo">[CHỐT LẠI SAU P1–P3; ghi 1 trích dẫn làm căn cứ]</span>

Không nêu giải pháp.

---

<!-- Slide 7: Prototype -->
# Prototype: 3 phương án khác nhau về cơ chế

| | Cơ chế |
|---|---|
| **A user-led** | Người bệnh hỏi, trợ lý trả lời |
| **B proactive** | Trợ lý tự nhắn khi có thay đổi |
| **C collaborative** | Trợ lý gợi ý, người bệnh duyệt rồi mới làm |

- Mọi phương án: hiện **khoảng** thay vì số phút, có nút khẩn cấp cố định
- Dữ liệu giả lập, không có dữ liệu bệnh nhân thật

<span class="todo">[CHÈN ẢNH MÀN HÌNH A / B / C]</span>

---

<!-- Slide 8: Kết quả thử -->
# Thử với người dùng và mình sửa gì

<span class="todo">[ĐIỀN SAU KHI CÓ LOG THỬ THẬT]</span>

- Người thử làm gì, khựng ở đâu: <span class="todo">[...]</span>
- Phương án nào họ dùng đúng, phương án nào hiểu sai: <span class="todo">[...]</span>
- Mình sửa: <span class="todo">[trước → sau]</span>
- Giới hạn: n = 2–3, đủ cho quyết định thiết kế tiếp theo, **không phải "validated"**

---

<!-- Slide 9: Best practice + rủi ro -->
# Bài học cho Vinmec và rủi ro chính

**Best practice quốc tế** <span class="todo">[ĐIỀN SAU: 3 nguồn từ 04-best-practice, mỗi nguồn 1 dòng bài học]</span>

**Rủi ro chính, cách giảm**
- Báo thừa giờ thì người bệnh đi xa, lỡ lượt: hiện **khoảng, thiên dè dặt**, không số giả chính xác
- Hỏi triệu chứng: từ chối và chuyển người thật; từ khoá khẩn cấp hiện **khối đỏ** + vị trí quầy
- Người không dùng app: bảng gọi số và nhân viên vẫn giữ song song
- Dữ liệu: bản thử chỉ mock; bản thật không gửi thông tin định danh vào API bên thứ ba

---

<!-- Slide 10: 6 tuần + coach -->
# Nếu có 6 tuần ở Vinmec, và mình coach K4 thế nào

**Mình làm tiếp (Tuần 1–6)**
- Quan sát và phỏng vấn ngay tại khoa, thêm điều dưỡng và nhân viên quầy
- Đo thời gian chờ thật (khử định danh) để kiểm tra ước tính
- Thử vòng 1 và 2 với người dùng Vinmec; đo lỡ lượt, không chỉ "hài lòng"

**Mình coach K4**
- Kickoff thứ Hai chốt khoảnh khắc và "thế nào là xong"; thứ Tư kiểm log thật; thứ Sáu checkpoint
- Hỏi thay vì đưa đáp án; chấm chéo theo mẫu feedback có dòng cụ thể (từ đội QA 12 người)
- Soi trích dẫn tròn trịa và log toàn lời khen
