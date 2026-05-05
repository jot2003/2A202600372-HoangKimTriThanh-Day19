# PITCH MEMO — AI PT Copilot

**Audience đã chọn (Day 19 — Step 1):** Seed VC (giai đoạn pre-seed / seed, tập trung consumer + health-tech).

---

## 1. THE PROBLEM (1–2 câu)

**71% người dùng bỏ app fitness trước tháng thứ 3**; với người tập một mình, vấn đề không phải thiếu bài tập mà là không biết mình đang tập sai hay đúng trong từng set. Nếu phản hồi camera bị sai ở điều kiện nhà chật/thiếu sáng, họ mất niềm tin rất nhanh và bỏ app sớm hơn.

---

## 2. THE INSIGHT (1 câu)

Rào cản lớn nhất không chỉ là "feedback gap" mà là **trust collapse**: niềm tin không giảm đều, mà thường sụp sau 1-2 cue sai, đặc biệt ở rep mệt cuối set; vì vậy chúng tôi tối ưu "khi nào KHONG nên nhắc" trước khi tối ưu nhắc thật nhiều.

---

## 3. THE SOLUTION (3 câu)

- **AI PT Copilot** tập trung vào 3 bài rủi ro cao (Squat, Push-up, Hip Hinge): pose on-device, cue voice/text theo rep, và summary cuối buổi bằng LLM.
- Thay vì cố "coach mọi thứ", chúng tôi ưu tiên trust: hiển thị confidence, cho user bật/tắt cue, và fallback manual mode khi tín hiệu camera kém.
- Lợi thế không nằm ở model đơn lẻ mà ở **hệ dữ liệu trust-calibration**: mỗi cue được ghi nhận thành accepted/ignored, phase mệt của set, và điều kiện camera; từ đó hệ thống học ngưỡng "nên nhắc / nên im lặng" theo từng user, không chỉ đo accuracy trung bình.

---

## 4. WHY NOW (1–2 câu)

On-device CV đã đủ nhanh cho phản hồi theo rep trên smartphone phổ biến; đồng thời người dùng đã quen luyện tập tại nhà sau giờ làm nhưng vẫn thiếu công cụ "an toàn để tin". Kể cả platform ngang thêm camera, lớp **trust-calibration theo lịch sử vận động từng user** vẫn là bài toán dọc cần workflow chuyên biệt.

---

## 5. TRACTION / PROOF (số cụ thể)

- **Hiện trạng trung thực:** chưa có CAC trả phí và chưa có paid retention đủ dài để khẳng định LTV/CAC.
- **Bằng chứng đang có:** bài toán và metric PMF đã định nghĩa rõ từ Day 17: Corrected-Cue Rate, Week-1 Aha Activation, return-72h.
- **Kế hoạch kiểm chứng 6 tuần:** pilot **100-150 user** để đo (1) tần suất bỏ qua cue theo session, (2) Corrected-Cue Rate theo bài tập, (3) tỷ lệ quay lại tuần 1-4, (4) tương quan "false cue sớm -> churn". **Go/No-Go thresholds:** nếu Corrected-Cue >= 60% **và** retention tuần 4 >= 25%, chúng tôi test chuyển đổi trả phí ngay; nếu dưới ngưỡng, không scale paid UA mà sửa trust layer trước.

---

## 6. THE ASK (1–2 câu)

**Gọi 3.000.000.000 VND (Seed)** để hoàn tất MVP trust-first, chạy pilot 100-150 user, và chứng minh willingness-to-pay + retention 4 tuần trước khi scale acquisition. Mốc 12 tháng: chứng minh lớp trust-calibration tạo hành vi giữ chân vượt baseline (đo bằng false-cue impact và retention delta), tức lợi thế đến từ dữ liệu hành vi riêng chứ không phải chỉ "feature camera".

---

*Bản này cố ý chuyển từ "model đẹp trên giấy" sang "giả thuyết rõ + kế hoạch kiểm chứng" theo góp ý VC critique.*
