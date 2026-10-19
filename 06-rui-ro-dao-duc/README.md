# 06 – Rủi ro an toàn, đạo đức và cách giảm thiểu

Phạm vi: khoảnh khắc "chờ đến lượt khám"; prototype là màn hình MyVinmec giả lập có trợ lý AI báo tiến độ hàng chờ (3 phương án: A user-led, B proactive, C collaborative, model GPT). Tài liệu chia 4 nhóm: (a) người tham gia nghiên cứu, (b) sản phẩm nếu triển khai thật, (c) đường chuyển tuyến khẩn cấp, (d) giới hạn của chính bài này.

Khung phân tích ở nhóm (b) lấy từ Day 5 và Day 18: trust calibration, agency = độ chắc × cost-of-error, precision/recall xem ai gánh hậu quả, error vs failure, graceful handoff.

---

## (a) Rủi ro với người tham gia nghiên cứu

Người tham gia là người quen kể về lần đi khám của họ. Hai rủi ro thực tế nhất: bị nhận ra danh tính, và vô tình kể sang chuyện bệnh.

| Rủi ro | Cách giảm thiểu | Làm khi nào |
|---|---|---|
| Họ không biết mình đang được hỏi để làm gì, hoặc thấy khó từ chối vì là người quen | Đọc lời mở đầu (mục đích, hỏi về trải nghiệm dịch vụ chứ không hỏi bệnh, được bỏ qua câu bất kỳ, được dừng bất cứ lúc nào). Xin đồng ý miệng ngay trước khi hỏi và ghi "đã đồng ý" ở đầu log. Nói rõ đồng ý hay không đều không ảnh hưởng gì giữa hai bên | Đầu mỗi cuộc, và đầu mỗi lượt thử prototype |
| Lộ danh tính qua log, trích dẫn, slide | Chỉ dùng P1, P2, P3. Không ghi tên, nơi làm, tên bác sĩ, tên khoa cụ thể, ngày giờ chính xác. Trích dẫn nào có chi tiết nhận ra được (ví dụ nghề nghiệp hiếm, địa chỉ) thì sửa thành mô tả chung và đánh dấu `[đã lược]`. Không chụp ảnh người, giấy tờ y tế, màn hình có thông tin cá nhân | Lúc ghi log, rà lại lần nữa trước khi đưa vào repo |
| Không ghi âm khi chưa được phép | Mặc định chỉ ghi chép tay hoặc gõ. Chỉ ghi âm khi họ đồng ý rõ ràng; nếu ghi âm thì xoá file gốc sau khi gỡ băng và ẩn danh log | Trước cuộc phỏng vấn |
| Người kể lấn sang bệnh án, chẩn đoán, thuốc, kết quả xét nghiệm | Mình không hỏi về sức khoẻ. Khi họ tự kể: nói nhẹ "chuyện sức khoẻ riêng của bạn mình xin không ghi lại, mình quay về đoạn chờ ở viện nhé", dừng gõ ngay, không ghi vào log, không hỏi thêm. Nếu đã lỡ ghi thì xoá dòng đó trước khi lưu và ghi chú "[đã lược nội dung sức khoẻ theo yêu cầu quy trình]" | Ngay trong cuộc |
| Họ đổi ý sau cuộc phỏng vấn | Cho họ cách liên hệ lại. Khi họ yêu cầu xoá: xoá log, trích dẫn và mọi chỗ đã dùng trong repo, slide trong cùng ngày, và báo lại là đã xoá. Phần tổng hợp insight nào dựa vào P# đó thì cập nhật lại | Bất kỳ lúc nào |
| Thử prototype với người đang gặp vấn đề sức khoẻ thật (đang đau, đang chờ khám thật, lo lắng rõ) | Hỏi trước khi bắt đầu: "Hôm nay bạn đang thấy ổn để làm thử khoảng 15 phút chứ?". Nếu họ đang không ổn thì dừng phiên thử, đổi người hoặc đổi ngày, không thuyết phục. Chỉ tuyển người đang khoẻ để thử, không thử tại phòng chờ thật | Trước mỗi phiên thử |
| Người thử tưởng AI trong prototype là tư vấn y tế thật | Banner cố định trên màn hình: "Bản thử nghiệm, dữ liệu giả lập, không dùng để quyết định gì về việc khám chữa bệnh". Nói lại bằng lời đầu phiên | Trong prototype và đầu phiên |
| Ghi log thử có lưu cả đoạn chat người thử gõ | Hướng dẫn người thử chỉ chơi với tình huống đã cho sẵn (kịch bản giả lập). Nếu họ gõ thông tin cá nhân thật vào ô chat thì xoá khỏi log | Lúc thử và lúc ghi log |

Dữ liệu lưu: chỉ trong repo, không có tên thật. Không đưa audio, ảnh người, tên thật lên repo công khai.

---

## (b) Rủi ro của sản phẩm nếu triển khai thật

### b1. Ước tính thời gian chờ sai: ai gánh?

Đây là rủi ro chính của một trợ lý báo tiến độ hàng chờ, vì người bệnh **hành động** theo con số (đi ăn, đi vệ sinh, ra xe, gọi người nhà).

Hai kiểu sai, hậu quả không đối xứng:

| | Báo **thừa** giờ (nói 40 phút, thực tế 15 phút) | Báo **thiếu** giờ (nói 15 phút, thực tế 40 phút) |
|---|---|---|
| Tương ứng | False positive theo nghĩa "báo còn lâu" | False negative theo nghĩa "báo sắp tới" |
| Người bệnh làm gì | Đi xa chỗ chờ, ra ngoài ăn, về xe | Ngồi canh quầy, từ chối đi vệ sinh, hỏi nhân viên liên tục |
| Hậu quả | **Lỡ lượt**: bị bỏ qua hoặc xếp lại, mất thêm thời gian, có khi nhân viên phải gọi nhiều lần. Người bệnh gánh | Mất lòng tin vào app, bực bội, thêm áp lực cho quầy. Người bệnh gánh một phần, nhân viên gánh phần còn lại |
| Có sửa được không | Khó: lỡ rồi thì mất lượt | Dễ hơn: chờ thêm, nhưng đã mất lòng tin |
| Cost-of-error | **Cao** | Thấp đến vừa |

Câu hỏi chọn ngưỡng theo Day 18: "bỏ lọt" hay "báo nhầm" cái nào đắt hơn? Ở đây, bỏ lỡ lượt đắt hơn, nên **thiên về báo dè dặt**: khi AI không chắc, thà nói "có thể sắp tới lượt" còn hơn nói "bạn còn rảnh 30 phút".

Giảm thiểu trong thiết kế:

- **Hiện khoảng thay vì số**: "khoảng 15–30 phút" thay vì "22 phút". Khoảng phải được tính ở phía an toàn: cận dưới thấp hơn thực tế dự đoán một chút, để người bệnh không đi quá xa.
- **Khi độ chắc thấp, nói "chưa rõ"** và hành xử khác (xem b2), theo ý Day 5 về categorical confidence: cao thì báo khoảng hẹp, vừa thì báo khoảng rộng kèm "có thể thay đổi", thấp thì không đưa số và nói rõ lý do.
- **Không bao giờ nói "bạn có thể rời chỗ" như một cam kết.** Nếu có tính năng này thì dùng mức Ask thay vì Act (theo thang Inaction / Ask / Act): "Bạn muốn mình nhắc khi còn khoảng 3 người trước bạn không?", và luôn kèm "ở lại gần khu chờ sẽ an toàn hơn".
- **Nhắc trước khi sắp tới lượt**, không chỉ khi đã tới lượt. Gọi tên tại quầy vẫn là kênh chính thức và vẫn hoạt động song song.
- **Lỡ lượt không bị phạt**: nếu người bệnh vắng mặt khi được gọi, quy trình mặc định là gọi lại / xếp ưu tiên quay lại, không bị xếp xuống cuối. Đây là yêu cầu vận hành, không phải việc của app, cần Vinmec xác nhận.
- Đo sai số sau khi pilot (I1 trong `03-need-statement/`), đặt ngưỡng sai số do người bệnh chấp nhận chứ không do mình tự đặt. Nếu sai số quá lớn so với khoảng đang hiện, ưu tiên rút lại tính năng ước tính và chỉ giữ phần "bạn đang ở vị trí thứ mấy".

### b2. Overtrust: UI hứa điều AI không giữ được

Nguyên tắc: *"Don't let your UI write a check that your AI can't cash"*.

| Điều không làm | Làm thay vào |
|---|---|
| Hiện "còn 17 phút" (giả chính xác) | "Khoảng 15–30 phút. Ước tính, có thể thay đổi nếu có ca khẩn cấp" |
| Đếm ngược từng giây hoặc đồng hồ | Cập nhật theo nấc, ghi giờ cập nhật lần cuối ("cập nhật 2 phút trước") |
| Giọng điệu chắc chắn ("Bạn sẽ được gọi lúc 10:20") | "Dự kiến", "thường là" |
| Ẩn lý do khi ước tính đổi | Khi ước tính tăng lên thì nói vì sao (ví dụ: "phòng khám đang có ca cần thêm thời gian"), ngôn ngữ đơn giản, không đổ lỗi cho ai |
| Không cho người bệnh sửa/phản hồi | Nút "Không đúng với tình hình thực tế" tại chỗ; ghi nhận và nói điều gì sẽ đổi |
| Tự ra quyết định thay họ | Trợ lý chỉ **báo và gợi ý**; quyết định rời chỗ hay không vẫn là của người bệnh |

Trong ba phương án prototype, phương án B (proactive, AI chủ động nhắn) có cost-of-error cao nhất, vì tin nhắn chủ động tự mang trọng lượng "hệ thống biết rõ". Nếu thử vòng 1 cho thấy người thử tin theo B quá mức (ví dụ rời chỗ ngay khi nhận tin), mình sẽ chuyển B xuống mức Ask thay vì Act. Đây là điều cần xem ở `05-prototype/log-thu-nghiem.md`.

### b3. Người bệnh hỏi về triệu chứng, thuốc, bệnh

Trợ lý được dựng cho một việc: báo tiến độ chờ. Nó không phải trợ lý y tế.

- Phạm vi nói rõ ngay từ đầu (Trụ A, HAX G1/G2): "Mình giúp bạn theo dõi lượt chờ. Mình không tư vấn về sức khoẻ."
- Prompt hệ thống có danh sách cấm: không chẩn đoán, không nhận xét kết quả, không gợi ý thuốc, không nói "bạn không sao đâu".
- Khi gặp câu hỏi ngoài phạm vi: từ chối ngắn, không giải thích dài, **kèm handoff**: "Câu này cần người có chuyên môn trả lời. Bạn hỏi điều dưỡng ở quầy [tên khu] nhé" + nút gọi/chỉ đường tới quầy. Đây là 3 việc bắt buộc của graceful handoff: nói rõ giới hạn, không để người dùng cụt đường, trả quyền cho người thật.
- Từ khoá triệu chứng kích hoạt đường khẩn cấp ở nhóm (c), không phải câu từ chối thường.
- Đo bằng test: bộ câu hỏi thử nghiệm đối kháng (hỏi triệu chứng theo nhiều cách nói, tiếng lóng, viết tắt, không dấu) chạy trước mỗi lần đổi prompt/model, đạt 100% từ chối + handoff mới được phát hành. Trong bài này mình chưa chạy được bộ đủ lớn, xem nhóm (d).

### b4. Nhóm yếu thế

Người cao tuổi không quen dùng app, người không có smartphone hoặc hết pin, người không đọc thạo chữ nhỏ, người đi một mình: họ có thể là nhóm chịu cảnh chờ mơ hồ nặng nhất, nhưng lại là nhóm ít dùng được giải pháp số nhất.

- **Song song, không thay thế**: bảng gọi số, loa gọi tên, nhân viên hướng dẫn tại quầy vẫn giữ nguyên. Không chuyển việc "biết lượt của mình" hoàn toàn sang app.
- **Không để trải nghiệm của họ tệ đi**: không được xếp thứ tự hay dành nguồn lực quầy dựa trên việc người bệnh có dùng app hay không. Nhân viên quầy không được coi "đã báo trên app rồi" là đã báo.
- Cho phép **người nhà** nhận thông báo thay (chỉ khi người bệnh đồng ý), vì nhiều người cao tuổi đi cùng con cháu.
- Chữ to, tương phản cao, ngôn ngữ đơn giản; thử với ít nhất một người lớn tuổi trước khi pilot (trong bài này chưa làm được, xem nhóm (d)).
- Màn hình hiện số chờ công cộng (nếu có) chỉ dùng mã lượt, không dùng tên.
- Chỉ số theo dõi sau pilot: so sánh thời gian chờ và tỷ lệ lỡ lượt giữa người dùng app và người không dùng app. Nếu nhóm không dùng app tệ đi, coi là lỗi của thiết kế.

### b5. Dữ liệu cá nhân

| Giai đoạn | Cách xử lý |
|---|---|
| Bài tập này | Prototype **chỉ dùng mock data** (tên giả, số thứ tự giả, lịch giả). Không có dữ liệu người bệnh thật nào, không nhập thông tin người thử vào hệ thống |
| Sprint / pilot (theo quy định 6 tuần) | Chỉ dùng dữ liệu tự mô phỏng, công khai, hoặc đã khử định danh trong sandbox của Vinmec khi được duyệt. Làm theo khoá đào tạo bắt buộc của Vinmec và NDA |
| Bản triển khai thật | **Tối thiểu hoá dữ liệu**: trợ lý chỉ cần mã lượt, vị trí trong hàng, trạng thái phòng khám; không cần tên, ngày sinh, chẩn đoán. **Không gửi thông tin định danh vào API LLM của bên thứ ba.** Phần suy luận chạy trong hạ tầng của bệnh viện (on-premise hoặc sandbox đã được duyệt) hoặc nhà cung cấp đã qua thẩm định bảo mật của Vinmec. Log hội thoại có thời hạn lưu và quyền xoá |

Ghi chú về cách làm của mình: prototype dùng API model GPT chỉ vì đây là bản thử với dữ liệu giả. Khi chuyển sang bối cảnh Vinmec thật, lựa chọn model và nơi chạy phải theo quy định của Vinmec, không theo sự tiện lợi của mình.

---

## (c) Đường chuyển tuyến khẩn cấp

Người đang ngồi chờ là người đang có vấn đề sức khoẻ. Một số người sẽ xấu đi **ngay trong lúc chờ**, và họ có thể nhìn vào điện thoại trước khi nhìn lên nhân viên. Màn hình đó không được làm họ mất thêm giây nào.

Nguyên tắc: **ưu tiên an toàn hơn mọi chức năng báo chờ.** Chuyển tuyến khẩn cấp luôn thắng.

| Tình huống | Hành động của hệ thống |
|---|---|
| Người dùng bấm nút "Tôi cảm thấy không ổn" (luôn hiện cố định trên màn hình chờ) | Hiện ngay **khối đỏ** chiếm đầu màn hình: "Hãy báo ngay cho nhân viên y tế gần nhất." + vị trí quầy/điều dưỡng gần nhất (tên khu, tầng, chỉ đường ngắn) + nút gọi nội bộ/tổng đài trực. Dừng hiển thị ước tính chờ |
| Trong chat hoặc câu hỏi có từ khoá: đau ngực, khó thở, chóng mặt, ngất, tức ngực, tê yếu nửa người, chảy máu, co giật, ra nhiều máu, đau dữ dội, ... (cả bản không dấu và cách nói đời thường) | **Dừng chức năng chờ.** Hiện khối đỏ như trên. Câu duy nhất AI nói: không đánh giá, không hỏi dồn, không trấn an kiểu "chắc không sao". Chỉ: "Bạn cần gặp người có chuyên môn ngay. Hãy báo nhân viên gần bạn hoặc đến quầy [..]" |
| Người dùng nhắn bằng giọng hoảng sợ, hoặc nói người thân đang ngất/khó thở | Giống dòng trên, thêm: "Nếu bạn đang đi cùng người cần giúp, hãy gọi người xung quanh/nhân viên ngay" |
| Triệu chứng nghe không rõ mức độ (đau bụng, buồn nôn, sốt) | Không đoán mức nặng nhẹ. Nói: "Mình không đánh giá được tình trạng sức khoẻ. Hãy báo điều dưỡng ở quầy [..] để được kiểm tra." + nút chỉ đường. Không tiếp tục báo ước tính chờ trong lượt hội thoại đó |
| AI không hiểu ý hoặc độ chắc thấp trong tình huống có dấu hiệu sức khoẻ | Mặc định coi là có thể khẩn cấp: chuyển người thật, không hỏi lại nhiều lần |
| Mất mạng, app lỗi, trợ lý không phản hồi | Màn hình hiển thị cố định dòng "Cần hỗ trợ khẩn: báo nhân viên tại quầy [..] hoặc số trực [..]" không phụ thuộc AI. Chức năng khẩn không đi qua LLM |
| **Khi thử prototype**: người thử nói đang đau, mệt, chóng mặt, lo lắng thật | Dừng phiên thử ngay, hỏi thăm, hướng họ tới nhân viên y tế/số cấp cứu phù hợp nơi đang ở, không tiếp tục ghi nhận. Ghi vào log chỉ "phiên dừng vì lý do an toàn", không ghi chi tiết sức khoẻ |
| **Khi phỏng vấn**: người được hỏi bỗng thấy không khoẻ | Dừng ngay, ưu tiên giúp họ; không cố hoàn thành cuộc phỏng vấn |

Thiết kế kỹ thuật cho đường khẩn:

- **Phát hiện từ khoá bằng luật xác định (rule-based) chạy trước LLM**, không phụ thuộc việc model có "hiểu" hay không. Danh sách từ khoá thiên về nhạy (nhận nhầm còn hơn bỏ sót): trong bài này, bỏ lọt đắt hơn báo nhầm, theo đúng cách chọn ngưỡng recall ưu tiên ở Day 18; báo nhầm chỉ tốn một lần người bệnh nhìn thấy khối đỏ và gặp điều dưỡng, chấp nhận được.
- Có đường kháng nghị cho báo nhầm: nút "Mình không cần hỗ trợ khẩn" quay lại màn hình chờ, nhưng nút "Tôi cảm thấy không ổn" luôn còn.
- Số điện thoại và vị trí quầy trong prototype là **giả lập**; ở bản thật phải lấy từ Vinmec và kiểm tra bởi bộ phận có trách nhiệm trước khi phát hành. Mình không tự đặt số điện thoại y tế.
- Nhật ký các lần kích hoạt khẩn được xem lại hàng tuần bởi người có trách nhiệm, vì đó là nơi lộ lỗ hổng sớm nhất.

Giới hạn: bản prototype của bài này chỉ mô phỏng giao diện của đường khẩn cấp, chưa có hệ thống phát hiện đủ mạnh để tin trong thực tế.

---

## (d) Giới hạn trung thực của bài này

- **Dữ liệu là mock.** Số thứ tự, thời gian chờ, tình huống trong prototype là mình dựng. Không có dữ liệu hàng chờ thật nào.
- **Ước tính chưa validate.** Bài này không chứng minh được rằng ước tính trong prototype đúng. Khoảng thời gian trong prototype lấy từ quy tắc mình đặt, không phải đo từ hệ thống thật.
- **Mẫu rất nhỏ**: 3 cuộc phỏng vấn (người quen, thuận tiện, kể lại từ trí nhớ) và 2–3 người thử. Chỉ đủ để rút ra **quyết định thiết kế tiếp theo** và biết cần hỏi gì ở vòng sau; **không đủ để nói "đã kiểm chứng" (validated)**, không nói được tỷ lệ hay mức phổ biến.
- **Thiếu góc nhìn** nhân viên y tế (điều dưỡng, nhân viên quầy), người cao tuổi, người không dùng smartphone. Đây là nhóm quan trọng nhất cho phần (b4) và mình chưa tiếp cận được trong thời gian làm bài.
- **Chưa có thử nghiệm đối kháng** quy mô lớn cho từ chối câu hỏi y khoa và nhận diện từ khoá khẩn cấp. Hai phần này mới là thiết kế, chưa được chứng minh đủ an toàn.
- **Người thử có thể lịch sự**: người quen thường khen. Log thử ghi hành vi quan sát được, tách khỏi lời khen.
- **Phần do AI hỗ trợ**: AI giúp rà cấu trúc và liệt kê tình huống rủi ro; việc chọn ưu tiên và phán đoán an toàn là của mình. Mọi điểm trong tài liệu này cần được bác sĩ/điều dưỡng và bộ phận an toàn thông tin của Vinmec rà lại trước khi dùng thật.

Kết luận gói gọn: bài này đủ để chỉ ra **rủi ro nào cần được thiết kế chặn trước** và **cần đo gì ở sprint**, chưa đủ để nói sản phẩm này an toàn.
