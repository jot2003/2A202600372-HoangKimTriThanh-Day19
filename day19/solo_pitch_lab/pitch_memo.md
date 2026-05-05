# PITCH MEMO — AI PT Copilot

**Audience đã chọn (Day 19 — Step 1):** Seed VC (giai đoạn pre-seed / seed, tập trung consumer + health-tech).

---

## 1. THE PROBLEM (1–2 câu)

Trong thử nghiệm nội bộ, chỉ cần **1-2 cue sai ở 2 session đầu** là user bắt đầu bỏ qua hầu hết feedback còn lại; vấn đề cốt lõi không phải thiếu bài tập, mà là mất niềm tin vào phản hồi camera khi tập một mình. Đây là lý do churn cao ở nhóm user mới dù content đầy đủ.

---

## 2. THE INSIGHT (1 câu)

Rào cản lớn nhất không chỉ là "feedback gap" mà là **trust collapse** có thể đo được: nếu false cue xuất hiện sớm, tỷ lệ ignore cue tăng mạnh ở các rep sau; vì vậy chúng tôi tối ưu "khi nào KHONG nên nhắc" trước khi tối ưu nhắc thật nhiều.

---

## 3. THE SOLUTION (3 câu)

- **AI PT Copilot** tập trung vào 3 bài rủi ro cao (Squat, Push-up, Hip Hinge): pose on-device, cue voice/text theo rep, và summary cuối buổi bằng LLM.
- Thay vì cố "coach mọi thứ", chúng tôi ưu tiên trust: hiển thị confidence, cho user bật/tắt cue, và fallback manual mode khi tín hiệu camera kém.
- Lợi thế không nằm ở model đơn lẻ mà ở **hệ dữ liệu trust-calibration**: mỗi cue được ghi nhận thành accepted/ignored, phase mệt của set, và điều kiện camera; từ đó hệ thống học ngưỡng "nên nhắc / nên im lặng" theo từng user, không chỉ đo accuracy trung bình.

---

## 4. WHY NOW (1–2 câu)

On-device CV đã đủ nhanh cho phản hồi theo rep trên smartphone phổ biến; đồng thời người dùng đã quen luyện tập tại nhà sau giờ làm nhưng vẫn thiếu công cụ "an toàn để tin". Kể cả platform ngang thêm camera, họ vẫn thiếu **ngưỡng trust theo từng cá nhân**; switching sang app khác sẽ reset lịch sử calibration tích lũy.

---

## 5. TRACTION / PROOF (số cụ thể)

- **Hiện trạng trung thực:** chưa có CAC trả phí và chưa có paid retention đủ dài để khẳng định LTV/CAC.
- **Bằng chứng đang có:** bài toán và metric PMF đã định nghĩa rõ từ Day 17: Corrected-Cue Rate, Week-1 Aha Activation, return-72h.
- **Kế hoạch kiểm chứng 6 tuần:** pilot **100-150 user** để đo (1) tần suất bỏ qua cue theo session, (2) Corrected-Cue Rate theo bài tập, (3) tỷ lệ quay lại tuần 1-4, (4) tương quan "false cue sớm -> churn".
- **Vì sao chọn ngưỡng:** Corrected-Cue **>= 60%** bám ngưỡng PMF Day 17; retention tuần 4 **>= 25%** là mốc tối thiểu để test trả phí ở B2C fitness early cohort.
- **Go/No-Go:** đạt cả 2 ngưỡng thì test paywall; không đạt thì dừng scale paid UA và ưu tiên giảm false cue ở 2 session đầu.
- **Monetization proxy trước paid launch:** theo dõi tỷ lệ click "unlock pro coaching", completion fake-paywall, và ý định trả phí sau 2 tuần.

---

## 6. THE ASK (1–2 câu)

**Gọi 3.000.000.000 VND (Seed)** để hoàn tất MVP trust-first, chạy pilot 100-150 user, và chứng minh willingness-to-pay + retention 4 tuần trước khi scale acquisition. Mốc 12 tháng: chứng minh lớp trust-calibration tạo hành vi giữ chân vượt baseline (đo bằng false-cue impact và retention delta), tức lợi thế đến từ dữ liệu hành vi riêng chứ không phải chỉ "feature camera".

---

*Bản này cố ý chuyển từ "model đẹp trên giấy" sang "giả thuyết rõ + kế hoạch kiểm chứng" theo góp ý VC critique.*
