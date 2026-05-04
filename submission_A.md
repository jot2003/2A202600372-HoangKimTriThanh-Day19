# Day 17 Submission - Version A (Snapshot cuối buổi)
**Student:** Hoàng Kim Trí Thành (2A202600372)
**Date:** 2026-04-24
**Product idea:** AI PT Copilot giúp người mới tập sửa form an toàn qua camera smartphone.

---

## 1. MVP Boundary Sheet
**Riskiest Assumption:**
> User sẽ tin và làm theo feedback form real-time của AI khi tập một mình.

**In-Scope** (tối đa 3):
- [ ] Form check real-time cho Squat, Push-up, Hip Hinge.
- [ ] Voice/text cue sửa lỗi trong lúc tập.
- [ ] Tổng kết 3 lỗi chính sau buổi tập.

**Out-of-Scope:**
- Meal plan/nutrition coaching.
- Social challenge và leaderboard.
- Lịch tập cá nhân hóa dài hạn.
- Tích hợp wearable.

**Non-Goals:**
- Không thay thế PT chuyên nghiệp.
- Không đưa ra chẩn đoán y tế.

---

## 2. PRD Skeleton
### Problem Statement
> Dân văn phòng mới tập không tự tin về kỹ thuật, sợ chấn thương nên dễ bỏ cuộc sớm.

### Target User
> Người làm văn phòng 22-35 tuổi, tập một mình 30-45 phút sau giờ làm, dùng smartphone để tập theo.

### User Stories
**Story 1:**
> As a beginner office worker, I want instant form correction cues, so that I can train more safely.

**Story 2:**
> As a beginner office worker, I want a short error summary after each session, so that I know what to improve next time.

### AI-Specific
**Model Selection:**
- Model: Pose estimation + cloud LLM summary.
- Lý do chọn: cần latency thấp cho real-time, summary thì cần ngôn ngữ tự nhiên.
- Trade-offs chấp nhận: giảm độ chi tiết cue để giữ tốc độ.
- Trade-offs không chấp nhận: cue quá chậm hoặc hướng dẫn sai an toàn.

**Data Requirements:**
- Nguồn: camera keypoints, rule form cơ bản, log feedback.
- Owner: user sở hữu video gốc.
- Update frequency: cập nhật theo sprint.

**Fallback UX:**
- Chiến lược: Human-in-the-loop.
- Trigger: confidence thấp hoặc mất tracking mốc xương.
- Hành động: dừng auto cue, yêu cầu user căn chỉnh camera.
- User options: recalibrate / manual rep mode / gửi review sau buổi tập.

### Success Metrics
- Primary metric: Corrected-Cue Rate.
- Ngưỡng thành công: >= 50% trong 4 tuần.
- Timeframe đo lường: cohort 4 tuần đầu.

### Dependencies & Constraints
- Camera SDK, pose model, cloud summary service.
- MVP trong 6 tuần.
- Cần consent camera và có cơ chế xóa dữ liệu.

---

## 3. Hypothesis Table
### Hypothesis 1
> "Chúng tôi tin rằng real-time form check sẽ giúp người mới tập an toàn hơn.
> Chúng tôi sẽ biết mình đúng khi Corrected-Cue Rate >= 50% trong 4 tuần."

Riskiest assumption: User không bỏ qua cue.
Cách test cheapest: Wizard-of-Oz với PT gửi cue thủ công trên nhóm user nhỏ.

### Hypothesis 2
> "Chúng tôi tin rằng session summary ngắn gọn sẽ tăng khả năng user quay lại tập.
> Chúng tôi sẽ biết mình đúng khi return-72h của nhóm có summary cao hơn nhóm không có summary."

Riskiest assumption: Summary đủ để thay đổi hành vi quay lại.
Cách test cheapest: A/B test text summary trên pilot users.

---

## 4. PMF Scorecard
**Aha Moment:**
> User sửa được form ngay trong set nhận cue đầu tiên.

**Actionable Metric:**
> % user đạt >= 3 lần cue->correction trong 7 ngày đầu.

**PMF Method:**
> Retention Curve + Aha Moment tracking.
> Ngưỡng tạm thời: D30 > 10%.

**Vanity Metrics tôi sẽ không dùng:**
- Downloads.
- Sign-ups.
- Pageviews.

---

## 5. AI Critique Log
**Điểm AI chỉ ra:**
1. Scope có nguy cơ ôm đồm - Action: Partial.
2. Fallback UX chưa cụ thể trigger - Action: Accept.
3. PMF metric còn chung chung - Action: Accept.

**Thay đổi lớn nhất giữa Version A và Version B:**
> Sẽ thu hẹp scope và nâng cấp metric theo hành vi core value.

---

## 6. Self-assessment
Mắt xích yếu nhất:
> PMF metric và bằng chứng retention dài hạn.

Open questions:
1. Confidence threshold nào hợp lý cho từng bài tập?
2. Mức độ can thiệp human coaching tối ưu trong tuần đầu là bao nhiêu?
