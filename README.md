# Một lần đi khám: thiết kế lại khoảnh khắc "chờ đến lượt khám" với AI trên MyVinmec

Bài tập 1 tuần — ứng tuyển Exploration Sprint 6 tuần VinUni VRIC × Vinmec.
**Võ Huyền Khánh Mây — K2**

## Khoảnh khắc đã chọn

**Chờ đến lượt khám** — từ lúc người bệnh check-in xong đến lúc được gọi vào phòng khám (và các quãng chờ kết quả cận lâm sàng ngay sau đó). Tôi chọn hẹp khoảnh khắc này vì: (1) từ trải nghiệm làm CarePath và phỏng vấn người điều phối lịch khám ở một bệnh viện công, tôi biết phần lớn thời gian một lần đi khám không nằm ở lúc khám mà nằm ở lúc chờ; (2) đây là quãng người bệnh mù thông tin nhất — không biết còn bao lâu, không dám đi đâu; (3) nó là bài toán trải nghiệm + vận hành, đúng vùng AI hỗ trợ được mà không chạm vào quyết định y khoa.

## Mục lục repo

| Thư mục | Nội dung | Trạng thái |
|---|---|---|
| [`01-phong-van/`](01-phong-van/) | Ghi chép dùng thử MyVinmec, interview guide, log 3+ cuộc phỏng vấn ẩn danh (P1, P2, P3), tổng hợp insight | Guide hoàn chỉnh; log điền sau mỗi cuộc phỏng vấn thật |
| [`02-journey-map/`](02-journey-map/) | Journey map khoảnh khắc chờ khám, đánh dấu điểm đau | Nháp từ quan sát cá nhân; cập nhật bằng dữ liệu phỏng vấn |
| [`03-need-statement/`](03-need-statement/) | Need statement theo Biodesign + bằng chứng dẫn tới nó | Nháp; chốt sau phỏng vấn |
| [`04-best-practice/`](04-best-practice/) | 3 best practice quốc tế có nguồn + bài học cho Việt Nam/Vinmec | Hoàn chỉnh |
| [`05-prototype/`](05-prototype/) | Prototype web có AI (click được), prompt đã dùng, log thử nghiệm với 2–3 người | App chạy được; log điền sau mỗi vòng thử thật |
| [`06-rui-ro-dao-duc/`](06-rui-ro-dao-duc/) | Rủi ro an toàn, đạo đức, cách giảm thiểu, đường chuyển tuyến khẩn cấp | Hoàn chỉnh |
| [`07-coach-plan/`](07-coach-plan/) | Một trang: "Mình sẽ coach một nhóm K4 làm bài này thế nào" | Hoàn chỉnh |
| [`slides/`](slides/) | Nguồn slide (Marp) → xuất `slides.pdf` ≤10 slide | Xuất PDF ở bước cuối |

## Phương pháp

Bài làm bám các khung đã học trong AI Thực Chiến Track 1 (Day 2, 5, 17, 18):

- **Discovery (Day 17):** phỏng vấn theo Mom Test — hỏi về lần đi khám gần nhất đã xảy ra, không pitch ý tưởng, không hỏi tương lai; thu chuỗi bằng chứng Event → Behavior → Workaround → Consequence.
- **Định hình bài toán (Day 2):** need statement Biodesign (problem – population – outcome, không chứa giải pháp) + Problem Statement chín trường, điểm đau được định lượng (hiện trạng – mục tiêu – cách đo).
- **Experiment (Day 18):** prototype là một test slice của đúng một khoảnh khắc, có nhiều phương án khác nhau về cơ chế (Question → Contrast → Evidence) để người thử so sánh được trade-off thay vì khen xã giao.
- **HCAI (Day 5, 18):** trust = expectation + explainability + control; mức tự chủ của AI đặt theo độ chắc chắn × cái giá khi sai; thiết kế sẵn cho lúc AI sai (giới hạn, hỏi lại, chuyển nhân viên).
- **Thử người dùng (Day 18):** prototype interview 5 nhịp (comfort → context → task → observe → compare), log hành vi quan sát được tách khỏi diễn giải.

## Ràng buộc đạo đức (áp dụng xuyên suốt)

- Mọi người tham gia phỏng vấn/thử nghiệm đều được xin đồng ý trước, ẩn danh (P1, P2, P3…), không ghi âm khi chưa được phép.
- Chỉ hỏi về trải nghiệm dịch vụ; không hỏi chẩn đoán, bệnh án, tình trạng sức khỏe.
- Prototype không đưa lời khuyên y khoa; mọi câu hỏi triệu chứng được chuyển hướng sang nhân viên y tế.

## Ghi rõ phần nào do AI tạo

Theo yêu cầu của đề (mục 6.4), khai báo minh bạch:

- **Do AI (Claude/GPT) hỗ trợ tạo, tôi rà và chỉnh:** khung thư mục; bản nháp đầu của interview guide, journey map giả thuyết, need statement nháp, phần best practice (AI tìm nguồn, tôi kiểm tra từng link), phân tích rủi ro, coach plan, mã nguồn prototype, bản nháp slide.
- **Do tôi tự làm, AI không tạo:** toàn bộ dữ liệu thật — ghi chép dùng thử MyVinmec, nội dung các cuộc phỏng vấn P1/P2/P3, log thử nghiệm prototype với người thật, insight rút ra từ dữ liệu đó, và các quyết định sửa đổi sau mỗi vòng thử.
- AI **không** được dùng để tạo lời thoại, trích dẫn hay dữ liệu phỏng vấn/thử nghiệm giả.
