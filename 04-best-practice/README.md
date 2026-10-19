# 04 - Best practice quốc tế: trải nghiệm chờ đến lượt khám

Chủ đề: người bệnh ngoại trú chờ đến lượt khám. Ba practice dưới đây được chọn vì mỗi cái trả lời một câu hỏi khác nhau:

| # | Practice | Trả lời câu hỏi |
|---|----------|-----------------|
| 1 | SingHealth Health Buddy (Singapore) | Một hệ thống thật làm gì để người bệnh theo dõi hàng chờ từ xa? |
| 2 | David Maister, "The Psychology of Waiting Lines" (1985) | Vì sao chờ lại khó chịu, và đòn bẩy tâm lý nào làm nó đỡ khó chịu? |
| 3 | Bằng chứng nghiên cứu về việc công bố ước tính thời gian chờ (RCT ở Ả Rập Xê Út) | Công bố ước tính chờ có thật sự làm người bệnh hài lòng hơn không? |

Quy ước trung thực: chỉ ghi số liệu có trong nguồn đã mở được. Chỗ nào chỉ thấy qua kết quả tìm kiếm (không mở được trang gốc) được ghi rõ là "chưa kiểm chứng độc lập". Phần "Bài học cho Việt Nam" là suy luận của tác giả bài tập, không phải fact từ nguồn.

---

## Practice 1. SingHealth Health Buddy: đăng ký same-day và theo dõi hàng chờ từ xa (Singapore)

### Bối cảnh và họ làm gì
Theo trang FAQ chính thức của SingHealth (đã mở được), dịch vụ Health Buddy cho phép bệnh nhân **tái khám có lịch hẹn trong cùng ngày** tự đăng ký trên điện thoại, nhận số thứ tự và phòng khám được phân, rồi theo dõi hàng chờ từ xa:

- Đăng ký chỉ áp dụng cho lịch hẹn **trong cùng ngày**. Bệnh nhân khám lần đầu phải đăng ký tại phòng khám.
- Cửa sổ đăng ký: polyclinic và Sengkang General Hospital mở **60 phút** trước giờ hẹn hoặc giờ đến được khuyên; các bệnh viện khác và trung tâm quốc gia mở **90 phút** trước giờ hẹn. Đóng tại giờ hẹn.
- Bắt đầu từ **6:45 sáng** cho các lịch hẹn từ 7:30 sáng đến 9:30 tối.
- Sau khi đăng ký, ứng dụng hiển thị **số bệnh nhân đang ở trước mình**, tự cập nhật **mỗi 5 phút**, có nút làm mới thủ công.
- Trong ngày hẹn, bệnh nhân nhận **SMS mời đăng ký qua Health Buddy**.
- Lưu ý trung thực của chính SingHealth: hàng chờ **có thể không luôn chính xác vì ca cấp cứu được ưu tiên**; và **đăng ký sớm không giúp vượt lên** những người có lịch hẹn sớm hơn mình.

Một bản tóm tắt qua tìm kiếm (không phải trang gốc) cho biết dịch vụ ở một số phòng khám đang ở giai đoạn thí điểm và, từ 30/6/2025, các e-service của Health Buddy được nhúng vào module Appointment của HealthHub. Phần này chưa kiểm chứng độc lập.

**Điều KHÔNG xác nhận được:** gợi ý ban đầu về "SMS khi còn khoảng 3 người" **không tìm thấy** trong các trang đã mở. Trang đăng ký-theo dõi nói rõ không nêu ngưỡng số người cho SMS; trang `clinic-queue-update-faqs` trả về 404. Vì vậy bài này **không** dùng con số "3 người".

### Vì sao hiệu quả (nối với tâm lý học chờ đợi)
- Hiển thị "còn bao nhiêu người trước bạn" biến một lần chờ **không biết** thành lần chờ **có thể đo được** (Maister: uncertain wait dài hơn known wait).
- Cho phép chờ ở ngoài (cà phê, ngồi xe) thay vì ngồi nhìn cửa phòng khám: giảm lo âu "mình có bị quên không" (Maister: anxiety làm chờ dài hơn).
- Quy tắc "đăng ký sớm không vượt hàng" bảo vệ cảm giác công bằng (Maister: unfair wait khó chịu hơn).
- Việc SingHealth tự nói thẳng "hàng chờ có thể không chính xác vì ca khẩn cấp" chính là một lời giải thích, tương ứng nguyên lý unexplained wait.
(Đây là phần diễn giải của tác giả, nguồn SingHealth không tự nhận là áp dụng Maister.)

### Nguồn
- SingHealth, "Register and Track Queue FAQs" (Health Buddy). Đã fetch thành công: https://www.singhealth.com.sg/patient-services/health-buddy/faqs/register-track-queue-faqs
- SingHealth, "Clinic Queue Updates FAQs". Chỉ thấy qua kết quả tìm kiếm, fetch bị 404: https://www.singhealth.com.sg/patient-services/health-buddy/faqs/clinic-queue-updates-faqs

### Bài học cho Việt Nam và MyVinmec
Áp được ngay:
- Hiển thị **số người trước mình** (không chỉ số thứ tự của mình). "Số 57" vô nghĩa nếu không biết đang gọi số mấy; "còn 6 người" thì hiểu ngay.
- Ghi chú minh bạch ngay trên màn hình: "Số người có thể thay đổi do ca cấp cứu / ca ưu tiên". Người Việt vốn nghi ngờ số thứ tự; một dòng giải thích trước còn hơn để họ tự đoán là bị chèn ngang.
- Nhịp cập nhật vài phút, kèm nút làm mới: tạo cảm giác hệ thống "sống", không phải ảnh tĩnh.

Phải điều chỉnh:
- Singapore giới hạn cho tái khám có hẹn, trong cửa sổ 60-90 phút. Ở Việt Nam, nhiều người đến sớm hàng giờ để "xí chỗ"; cần thiết kế để việc đến sớm không còn lợi thế (hiện rõ giờ hẹn, thứ tự theo giờ hẹn) - nhưng đó là giả thuyết cần kiểm chứng bằng phỏng vấn.
- Người lớn tuổi ít dùng app: cần kênh song song (màn hình tại chỗ, nhân viên hướng dẫn, SMS/Zalo thay vì chỉ app). Con cái đặt hộ có thể nhận thông báo thay.
- Không có bằng chứng trong nguồn rằng mô hình này hoạt động ở Việt Nam; bài học là gợi ý để thử trong prototype, không phải kết luận.

---

## Practice 2. David Maister, "The Psychology of Waiting Lines" (1985)

### Bối cảnh và họ làm gì
Bài viết của David Maister, in năm **1985** trong sách *The Service Encounter* (chủ biên: John A. Czepiel, Michael R. Solomon, Carol F. Surprenant; D.C. Heath / Lexington Books), theo bản đăng trên davidmaister.com (đã fetch thành công). Đây là khung lý thuyết (không phải thử nghiệm y tế) với các "mệnh đề về chờ đợi":

1. Thời gian có việc làm (occupied) cảm giác ngắn hơn thời gian rảnh (unoccupied).
2. Người ta muốn được bắt đầu: chờ trước khi tiếp xúc đầu tiên dài hơn chờ khi dịch vụ đã bắt đầu.
3. Lo âu làm thời gian chờ dài hơn (sợ bị quên, sợ xếp nhầm hàng).
4. Chờ không rõ thời lượng dài hơn chờ biết rõ, hữu hạn.
5. Chờ không được giải thích dài hơn chờ có giải thích.
6. Chờ không công bằng dài hơn chờ công bằng.
7. Dịch vụ càng có giá trị, người ta chờ càng lâu.
8. Chờ một mình dài hơn chờ theo nhóm.

Trích dẫn nguyên văn từ bài: "Waiting in ignorance creates a feeling of powerlessness."

### Vì sao hiệu quả
Maister lập luận rằng thời gian chờ **cảm nhận** quan trọng hơn thời gian chờ **đo được**, và phần lớn sự khó chịu đến từ cảm xúc (lo âu, bất công, mù mờ) chứ không từ số phút. Đây là lý do quản lý thông tin và cảm giác công bằng có thể có tác dụng ngay cả khi chưa rút ngắn được hàng chờ.

### Nguồn
- David Maister, "The Psychology of Waiting Lines", 1985. Đã fetch thành công: https://davidmaister.com/articles/the-psychology-of-waiting-lines/

### Bài học cho Việt Nam và MyVinmec
Dùng làm "ống kính" để đọc ghi chép phỏng vấn và gắn nhãn điểm đau trong journey map:
- Người bệnh nói "chờ lâu" thì tách ra: lâu vì **không biết bao lâu** (4), **không biết vì sao** (5), **thấy người đến sau được gọi trước** (6), hay **sợ bị bỏ sót** (3)?
- Mệnh đề 2 rất hợp bối cảnh bệnh viện: "đã check-in / đã được ghi nhận" là một mốc cần hiển thị rõ (ví dụ "Bạn đã được tiếp nhận, đang chờ bác sĩ").
- Mệnh đề 6 đặc biệt quan trọng ở Việt Nam, nơi niềm tin vào số thứ tự có thể thấp; ca ưu tiên (người già, trẻ nhỏ, cấp cứu, VIP) cần được **giải thích**, không để người bệnh tự suy diễn.
- Lưu ý giới hạn: bài viết là khung quan sát từ ngành dịch vụ nói chung (1985), không dựng trên dữ liệu bệnh viện Việt Nam. Dùng như giả thuyết, kiểm lại bằng phỏng vấn.

---

## Practice 3. Công bố ước tính thời gian chờ: bằng chứng thực nghiệm còn hỗn hợp (RCT ở Ả Rập Xê Út)

Tôi chọn một practice "phản biện" có chủ đích: giả định "cứ cho người bệnh thấy ước tính thời gian chờ thì họ sẽ hài lòng hơn" cần được kiểm chứng, và có RCT cho thấy điều đó chưa chắc đúng.

### Bối cảnh và họ làm gì
**Nghiên cứu A (đã mở được trang tóm tắt):** Alrajhi KN và cộng sự, "Effect of waiting time estimates on patients satisfaction in the emergency department in a tertiary care center", *Saudi Medical Journal*, 2020, tập 41, số 8, trang 883-886, DOI 10.15537/smj.2020.8.25190.
- Thiết kế: thử nghiệm ngẫu nhiên có đối chứng tại King Abdulaziz Medical City, Riyadh, 9/2017-5/2018; bệnh nhân cấp cứu nói tiếng Ả Rập, 18-70 tuổi; **100 bệnh nhân**.
- Nhóm can thiệp nhận ước tính thời gian chờ; nhóm đối chứng thì không. Cả hai trả lời bảng hỏi trước và sau khi gặp bác sĩ.
- Kết quả: điểm hài lòng về thời gian chờ **không khác biệt có ý nghĩa** (can thiệp 5,92/10 ± 3,13; đối chứng 5,45/10 ± 3,38; p = 0,476). **70%** người tham gia **thích** có ước tính thời gian chờ.
- Kết luận của tác giả: ước tính không đổi mức hài lòng, nhưng đa số bệnh nhân muốn có.

**Nghiên cứu B (chưa kiểm chứng độc lập):** theo kết quả tìm kiếm trên DOAJ, Almulhim và cộng sự, *Journal of Family and Community Medicine*, 1/2025, tập 32, số 1, trang 36-43, DOI 10.4103/jfcm.jfcm_173_24: RCT tại King Fahad Hofuf Hospital với 190 bệnh nhân cấp cứu, báo cáo khác biệt hài lòng **không có ý nghĩa thống kê** (P = 0,962). Trang DOAJ trả về 403 khi fetch, nên các chi tiết này chỉ lấy từ đoạn trích kết quả tìm kiếm; cần đọc toàn văn trước khi trích dẫn chính thức.

Ngoài ra, các trang của nhà cung cấp biển hiệu số (OptiSigns, AIScreen) có nêu con số như "giảm thời gian chờ cảm nhận tới 35%", nhưng không dẫn nguồn gốc; **không dùng** trong bài này.

### Vì sao điều này quan trọng (nối với tâm lý học chờ đợi)
- Maister dự đoán chờ biết trước sẽ dễ chịu hơn chờ mù mờ. Hai RCT trên không xác nhận hiệu ứng đó ở thang điểm hài lòng, trong bối cảnh **cấp cứu** (người đang lo bệnh, độ bất định cao, ước tính dễ sai).
- Một cách đọc hợp lý (diễn giải của tác giả, không phải kết luận của nghiên cứu): con số ước tính chỉ là **một** trong nhiều yếu tố; sự hài lòng còn phụ thuộc độ chính xác của ước tính, lo âu, và cảm giác công bằng. Nếu ước tính sai, nó có thể phản tác dụng - đây là giả thuyết, các nguồn đã đọc không kiểm tra điều này.
- Dù vậy, 70% bệnh nhân vẫn muốn có ước tính: nhu cầu được biết là có thật, ngay cả khi điểm hài lòng không tăng.

### Nguồn
- Alrajhi KN, Aljerian NA, Alazaz RN, Araier LB, Alqahtani LS, Almushawwah SO. Effect of waiting time estimates on patients satisfaction in the emergency department in a tertiary care center. Saudi Med J. 2020;41(8):883-886. Đã fetch thành công trang tóm tắt: https://smj.researchcommons.org/journal/vol41/iss8/16 (trang smj.org.sa/node/1983 fetch bị 403; PDF toàn văn https://smj.org.sa/content/41/8/883.full.pdf chỉ thấy qua tìm kiếm).
- Almulhim và cộng sự. J Family Community Med. 2025;32(1):36-43. Chỉ thấy qua tìm kiếm, fetch 403: https://doaj.org/article/d2a9ec5a36e342f29c0113a14d8138c1
- Poster hội nghị (độ tin cậy thấp, chỉ thấy qua tìm kiếm, fetch bị 429): Canadian Journal of Emergency Medicine, "MP27 Publishing emergency department wait times in the waiting room: implementation and evaluation of a codesigned patient-centered solution": https://www.cambridge.org/core/journals/canadian-journal-of-emergency-medicine/article/mp27-publishing-emergency-department-wait-times-in-the-waiting-room-implementation-and-evaluation-of-a-codesigned-patient-centered-solution/367589B9A10C48C73FAE89A87BFA116B

### Bài học cho Việt Nam và MyVinmec
- **Đừng coi "hiện ước tính phút" là phép màu.** Cả hai RCT đều ở khoa cấp cứu Ả Rập Xê Út, không phải phòng khám ngoại trú Việt Nam, nên không thể suy thẳng sang MyVinmec; nhưng chúng là lời cảnh báo để prototype không hứa quá.
- **Ưu tiên thông tin có thể giữ lời hứa:** "còn X người trước bạn", "đã tiếp nhận", "đang chờ kết quả xét nghiệm" đáng tin hơn một con số phút cứng. Nếu hiển thị khoảng thời gian, dùng khoảng (ví dụ 20-40 phút) và cập nhật khi thay đổi, kèm lý do khi trễ.
- **Đo thay vì tin:** trong log thử nghiệm prototype (mục 05), nên hỏi người thử cả hai thứ: họ có *thích* thông tin này không, và họ có *bớt khó chịu/lo* không. Hai RCT cho thấy hai thứ này có thể lệch nhau.
- **Điều chỉnh bối cảnh:** ở phòng khám có hẹn (ít bất định hơn cấp cứu), hiệu ứng có thể khác; đây là điều cần kiểm chứng, không phải kết luận.

---

## Tổng hợp: ba bài học chính cho nhóm làm MyVinmec

1. Cho người bệnh thấy **vị trí của họ trong hàng** (số người phía trước), không chỉ số thứ tự (Practice 1).
2. **Giải thích** khi có chèn hàng hoặc trễ; sự công bằng nhìn thấy được quan trọng không kém tốc độ (Practices 1, 2).
3. **Không hứa số phút chính xác** nếu chưa tin được độ chính xác; và **đo tác động thật** lên cảm giác của người bệnh thay vì giả định (Practice 3).

## Danh sách nguồn

Đã fetch thành công (đọc được nội dung):
- https://www.singhealth.com.sg/patient-services/health-buddy/faqs/register-track-queue-faqs
- https://davidmaister.com/articles/the-psychology-of-waiting-lines/
- https://smj.researchcommons.org/journal/vol41/iss8/16

Chỉ thấy qua kết quả tìm kiếm (fetch lỗi hoặc không thử được; thông tin chưa kiểm chứng độc lập):
- https://www.singhealth.com.sg/patient-services/health-buddy/faqs/clinic-queue-updates-faqs (fetch 404)
- https://www.singhealth.com.sg/patient-care/patient-visitor-info/clinic-queue-update-faqs (fetch 404)
- https://doaj.org/article/d2a9ec5a36e342f29c0113a14d8138c1 (fetch 403)
- https://smj.org.sa/node/1983 (fetch 403)
- https://smj.org.sa/content/41/8/883.full.pdf (chưa fetch)
- https://www.cambridge.org/core/journals/canadian-journal-of-emergency-medicine/article/mp27-publishing-emergency-department-wait-times-in-the-waiting-room-implementation-and-evaluation-of-a-codesigned-patient-centered-solution/367589B9A10C48C73FAE89A87BFA116B (fetch 429)
