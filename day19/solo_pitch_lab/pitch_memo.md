# PITCH MEMO — AI PT Copilot

**Audience đã chọn (Day 19 — Step 1):** Seed VC (giai đoạn pre-seed / seed, tập trung B2C consumer & health-tech).

---

## 1. THE PROBLEM (1–2 câu)

Dân văn phòng 22–35 tập kháng lực một mình tại nhà/gym nhỏ **không có phản hồi kỹ thuật real-time**: họ xem video nhưng vẫn không biết form có an toàn hay không — stress, đau lưng/gối sai kỹ thuật, và **~71% bỏ app fitness trước tháng thứ 3** (đặc thù retention B2C fitness). Pain lặp lại **mỗi buổi tập**; chi phí ẩn là chấn thương + bỏ tập = mất tiền subscription/PT và sức khỏe.

---

## 2. THE INSIGHT (1 câu)

**Khoảng trống không phải “thiếu nội dung tập” mà là *feedback gap* — app đo được tọa độ nhưng chưa “hiểu” ý định form trong bối cảnh nhà phố thiếu sáng / góc hẹp**; người dùng cần **sửa lỗi trong đúng set**, không phải bài giải thích dài sau khi đã tập sai.

---

## 3. THE SOLUTION (3 câu)

- **AI PT Copilot** trên smartphone: real-time form check cho **Squat, Push-up, Hip Hinge** bằng **pose on-device** + cue **voice/text** trong lúc tập; sau buổi tập **LLM tóm tắt** 3 lỗi + 1 ưu tiên cho buổi sau (đúng PRD Day 17).
- **Khác ChatGPT / video:** ChatGPT không nhìn thấy cơ thể bạn; video một chiều không cảnh báo khi spine/gối lệch trong rep — Copilot **khóa vào bài + keypoints + rule an toàn** và giữ **latency thấp** (pose local, LLM chủ yếu cho summary).
- **AI:** pose estimation chạy **on-device**; cloud chỉ cho **tóm tắt** và giới hạn **~0,03 USD/buổi** inference để giữ **COGS ~207k VND/khách/tháng** (Base Day 18) thay vì đẩy full video lên cloud.

---

## 4. WHY NOW (1–2 câu)

Smartphone đủ mạnh cho **on-device CV**; niềm tin & adoption AI tại VN cao; **chi phí API foundation model** cho phép tóm tắt buổi tập rẻ hơn trước. Hành vi **tập tại nhà sau giờ làm** (30–45 phút) đã bền — thị trường không cần chờ “AI thần kỳ”, cần **sản phẩm an toàn + minh bạch** trong MVP **6 tuần** (Day 17).

---

## 5. TRACTION / PROOF (số cụ thể)

- **Thị trường (Day 16–18):** TAM **50.000** khách tiềm năng phân khúc đô thị; adoption Base **0,5%/tháng** → **~250 khách mới/tháng** sau MVP; **ARPU Base 499.000 VND/tháng**; model tài chính Base có **LTV/CAC ≥ 3** và **payback ≤ 12 tháng** (Unit Economics **HEALTHY** trong sheet, kể cả kịch bản Pessimistic đã chỉnh để Gross > 0).
- **PMF (Day 17):** North-star pilot — **Corrected-Cue Rate** (tỷ lệ session có ≥1 cue được user sửa trong cùng session) **≥ 60%** sau 4 tuần cohort mới; **Week-1 Aha Activation Rate** (≥3 lần cue→correction trong 7 ngày đầu) **≥ 50%** — gắn hành vi, không vanity DAU.
- **Giai đoạn:** MVP **6 tuần**, mục tiêu **100 user pilot** (đúng ràng buộc timeline PRD).

---

## 6. THE ASK (1–2 câu)

**Gọi 3.000.000.000 VND (Seed)** để: (1) ship MVP **3 bài + voice cue + session summary + consent/xóa dữ liệu** đạt ngưỡng PMF trên, (2) chạy **100 user pilot** + quan sát cohort **Corrected-Cue / return-72h**, (3) **mở rộng GTM** partnership gym/cộng đồng (giảm CAC theo kịch bản Optimistic **650k**). **12 tháng tới:** chứng minh **repeatable acquisition** + retention curve với **churn Base 5,5%/tháng** không vỡ khi scale paid UA.

---

*Bản này giữ đúng 6 section — ~1 trang A4 khi in.*
