# Day 17 Submission - Version B (BTVN / GitHub)
**Student:** Hoàng Kim Trí Thành (2A202600372)
**Date:** 2026-04-24
**Product idea:** AI PT Copilot trên smartphone giúp người mới tập kháng lực sửa form theo thời gian thực để tập an toàn và duy trì kỷ luật.

---

## 1. MVP Boundary Sheet
**Riskiest Assumption:**
> Người dùng mới tập sẽ tiếp tục sử dụng nếu AI có thể đưa ra cue sửa lỗi form đủ rõ ràng và đáng tin trong 10 giây đầu của mỗi set tập.

**In-Scope** (tối đa 3):
- [ ] Real-time form check cho 3 bài tập chính (Squat, Push-up, Hip Hinge) - test giả định: AI có thể tạo giá trị an toàn tức thì trên bài tập có nguy cơ chấn thương cao.
- [ ] Cue feedback bằng voice + text đơn giản ("Lưng đang cong, giữ cột sống trung lập") - test giả định: user hiểu và sửa động tác ngay khi đang tập.
- [ ] Session summary sau buổi tập (3 lỗi phổ biến + 1 hành động ưu tiên cho buổi sau) - test giả định: feedback tổng hợp giúp tăng khả năng quay lại buổi tập tiếp theo.

**Out-of-Scope:**
- Personalized nutrition plan - lý do bỏ: không cần để test core value "tập đúng form, giảm sợ chấn thương".
- Social leaderboard/challenge cộng đồng - lý do bỏ: dễ gây vanity engagement sớm, không giải quyết pain kỹ thuật.
- Full workout program generator 12 tuần - lý do bỏ: scope lớn, phụ thuộc nhiều biến số ngoài MVP.
- Tích hợp wearable (Apple Watch/Garmin) - lý do bỏ: tăng độ phức tạp kỹ thuật mà không giảm rủi ro form ngay lập tức.

**Non-Goals:**
- Không thay thế PT người thật cho giáo án toàn diện hoặc phục hồi chấn thương.
- Không đưa ra chẩn đoán y tế/khuyến nghị điều trị.

---

## 2. PRD Skeleton
### Problem Statement
> Dân văn phòng mới tập kháng lực tại nhà/gym nhỏ đang gặp khó khăn trong việc tự kiểm tra kỹ thuật, dẫn đến sợ chấn thương và bỏ tập sớm, gây mất cả hiệu quả sức khỏe lẫn động lực duy trì.

### Target User
> Dân văn phòng 22-35 tuổi ở đô thị lớn, tập 30-45 phút sau giờ làm, dùng smartphone đặt trước mặt, có động lực cải thiện sức khỏe nhưng thiếu phản hồi kỹ thuật real-time.

### User Stories
**Story 1:**
> As a beginner office worker training alone after work, I want immediate voice cues when my form is unsafe, so that I can finish my set without fear of knee or lower-back injury.

**Story 2:**
> As a beginner office worker with inconsistent routine, I want a short post-workout summary of my top form mistakes, so that I can apply one concrete correction in the next session and maintain training consistency.

### AI-Specific
**Model Selection:**
- Model: On-device pose estimation + lightweight cloud LLM for natural-language coaching summary.
- Lý do chọn: pose estimation cần độ trễ thấp cho real-time correction; cloud LLM chỉ xử lý text summary cuối buổi để tối ưu chi phí.
- Trade-offs chấp nhận: giảm độ phong phú của giải thích realtime để giữ latency dưới 300ms.
- Trade-offs không chấp nhận: feedback chậm hơn 1 giây trong lúc user đang thực hiện rep; hallucination khuyến nghị trái ngược an toàn tập luyện.

**Data Requirements:**
- Nguồn: camera frames từ user session (chỉ xử lý keypoints), thư viện rule form theo bài tập cơ bản, feedback logs do user xác nhận.
- Owner: user sở hữu video gốc; hệ thống chỉ lưu keypoint và event logs đã ẩn danh để cải thiện model.
- Update frequency: rule và threshold cập nhật hàng tuần; model cue text cập nhật theo sprint.

**Fallback UX:**
- Chiến lược: Human-in-the-loop (rủi ro trung bình vì AI có thể hướng dẫn sai kỹ thuật).
- Trigger: confidence score pose < 0.8 trong >= 2 giây, hoặc không theo dõi được 3 mốc xương chính (hông-gối-vai).
- Hành động: dừng cue tự động, hiện thông báo "Góc quay/chiếu sáng chưa đủ. Đặt lại camera theo hướng dẫn 3 bước".
- User options: (1) Recalibrate camera, (2) chuyển "manual mode" chỉ đếm rep, (3) kết nối video review với PT/human reviewer sau buổi tập.

### Success Metrics
- Primary metric: % session có ít nhất 1 cue được user sửa thành công trong cùng session (Corrected-Cue Rate).
- Ngưỡng thành công: >= 60% sau 4 tuần với cohort user mới.
- Timeframe đo lường: theo cohort tuần 1-4 sau onboarding.

### Dependencies & Constraints
- API/Service: smartphone camera SDK, module pose estimation, cloud inference endpoint cho summary.
- Timeline constraint: MVP 6 tuần để có 100 user pilot.
- Budget constraint: ưu tiên model nhẹ, chi phí inference cloud <= 0.03 USD/session.
- Legal/Compliance constraint: xin consent rõ ràng trước khi bật camera; cho phép xóa dữ liệu ngay trong app.

---

## 3. Hypothesis Table
### Hypothesis 1 (cho tính năng In-Scope #1)
> "Chúng tôi tin rằng real-time form check cho 3 bài tập chính sẽ giúp dân văn phòng mới tập giảm nỗi sợ chấn thương và tăng sự tự tin khi tập một mình.
> Chúng tôi sẽ biết mình đúng khi thấy Corrected-Cue Rate đạt >= 60% trong 4 tuần đầu."

Riskiest assumption: User thực sự thay đổi động tác ngay khi nhận cue, không bỏ qua vì đang mất nhịp tập.
Cách test cheapest: Wizard-of-Oz pilot 20 user, PT người thật quan sát video live và gửi cue thủ công theo format dự kiến để đo tỷ lệ "cue -> correction".

### Hypothesis 2 (cho tính năng In-Scope #2)
> "Chúng tôi tin rằng session summary 3 lỗi phổ biến + 1 hành động ưu tiên sẽ giúp user quay lại tập trong vòng 72 giờ.
> Chúng tôi sẽ biết mình đúng khi thấy tỷ lệ return-72h đạt >= 45% ở nhóm nhận summary so với <= 30% ở nhóm không nhận summary trong 3 tuần."

Riskiest assumption: Summary ngắn gọn đủ để tạo hành vi quay lại tập, thay vì user chỉ đọc cho biết.
Cách test cheapest: A/B test bằng bản prototype text summary trên 50 user pilot, chưa cần tự động hóa toàn bộ.

---

## 4. PMF Scorecard
**Aha Moment:**
> User nhận cue trong lúc tập, sửa được form trong cùng 1 set, và nghe cảm nhận "an toàn hơn, dễ tiếp tục tập hơn".

**Actionable Metric:**
> Week-1 Aha Activation Rate = % user mới đạt >= 3 lần "cue hợp lệ -> correction thành công" trong 7 ngày đầu.

**PMF Method:**
> Retention Curve + Aha Moment tracking.
> Ngưỡng thành công: D30 retention > 12% (B2C benchmark) và Aha Activation Rate >= 50% trong 7 ngày đầu.

**Vanity Metrics tôi sẽ không dùng:**
- Số lượt tải app.
- Tổng số đăng ký nếu chưa có hành vi correction.
- Tổng thời gian mở app không gắn với hành vi sửa form.

---

## 5. AI Critique Log
**Điểm AI chỉ ra:**
1. In-Scope ban đầu có "Workout plan generator" là nice-to-have - Action: Accept - Lý do: không cần thiết để test giá trị cốt lõi an toàn kỹ thuật.
2. Fallback UX chưa có trigger định lượng - Action: Accept - Lý do: bổ sung ngưỡng confidence < 0.8 và điều kiện mất mốc xương để engineer implement được ngay.
3. Metric "DAU tăng" là vanity metric - Action: Accept - Lý do: đổi sang Corrected-Cue Rate và Aha Activation Rate để gắn trực tiếp hành vi tạo giá trị.

**Thay đổi lớn nhất giữa Version A và Version B:**
> Thu hẹp MVP còn 3 tính năng phục vụ trực tiếp bài toán "an toàn kỹ thuật", đồng thời chuyển hệ đo lường từ volume metric sang behavior metric để giảm rủi ro tự lừa mình về PMF.

---

## 6. Self-assessment
Mắt xích nào trong [MVP Boundary - PRD - Hypothesis - PMF] bạn đang yếu nhất?
> PMF. Hiện tại chúng tôi mới có giả thuyết mạnh về Aha Moment nhưng chưa đủ mẫu để xác nhận đường cong retention có flatten thật sự.

Open questions bạn muốn giải đáp tiếp:
1. Ngưỡng confidence nào tối ưu theo từng bài tập để cân bằng giữa độ chính xác và độ trễ feedback?
2. Có nên thêm một human coaching touchpoint nào trong tuần đầu để giảm churn trước khi mở rộng tự động hóa?
