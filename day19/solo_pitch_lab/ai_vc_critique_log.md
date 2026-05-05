# AI VC Critique Log — Day 19 Solo Pitch Lab

**Sinh viên:** Hoàng Kim Trí Thành — **MSSV:** 2A202600372  
**Sản phẩm:** AI PT Copilot  
**Audience:** Seed VC  
**Prompt dùng:** §4.1 — AI VC Critique Prompt (Sequoia Partner persona)

---

## A. Pitch gốc (trước critique — Step 2–3)

### Pitch Memo — bản nháp đầu

```text
PITCH MEMO — AI PT Copilot

1. THE PROBLEM
   Người mới tập kháng lực cần feedback form khi tập một mình.

2. THE INSIGHT
   Video không thay thế được coach nhìn bạn trong buổi tập.

3. THE SOLUTION
   App dùng camera để xem form và nhắc lỗi. Có AI. Khác video là interactive.

4. WHY NOW
   AI đang phát triển mạnh và mọi người có smartphone.

5. TRACTION / PROOF
   Đã có PRD Day 17 và mô hình tài chính Day 18 với các chỉ số lành mạnh.

6. THE ASK
   Cần vốn seed để làm pilot và scale.
```

### Twitter Pitch — bản nháp đầu (quá dài)

```text
71% user bỏ app fitness trước T3 — không thiếu clip tập, thiếu phản hồi form trong set. AI PT Copilot: pose on-device + cue Squat/Push-up/Hip Hinge <300ms, LLM tóm tắt buổi tập. Base: TAM 50k đô thị, ARPU 499k, LTV/CAC healthy (Day 18). Seed 3 tỷ VNĐ → 100 user pilot + Corrected-Cue ≥60% để chứng minh PMF.
```

*(Đếm: 307 ký tự — **FAIL** giới hạn 280.)*

---

## B. Phản hồi AI (full feedback — Step 4)

*Ngữ cảnh: Prompt §4.1 — nhập Pitch Memo nháp + Twitter Pitch nháp. Dưới đây là nội dung phản hồi mô phỏng theo đúng 5 mục yêu cầu trong prompt (tiếng Anh như prompt).*

### AI VC — Critique

**1. THE 8-SECOND TEST**

You open with nothing numeric in the memo’s first section and no sharp hook in the memo structure. In the Twitter pitch the **71%** line is strong — *that* earns another sentence. But the Pitch Memo Problem section is generic (“people need feedback”) which I’ve heard 200 times this week. **Verdict:** Twitter passes the 8-second test better than the memo; align memo hook with that stat.

**2. THE INSIGHT TEST**

The stated insight (“video isn’t a coach”) is **obvious**. Every fitness app founder says this. A non-obvious angle would be **specific**: e.g. feedback gap vs counting reps, on-device latency + privacy in VN apartment lighting, or why **in-set** correction changes retention vs post-hoc clips. Right now: **generic**.

**3. THE OPENAI THREAT**

“If OpenAI shipped form-check next week…” — your memo doesn’t defend **why** a general model beats you. Plausible answer: **3 lifts + rule library + domain edge cases in tight spaces**, **on-device** to avoid sending video, **workflow** embedded in the workout — but you didn’t write any of that. **Moat looks weak** on paper.

**4. THE NUMBERS TEST**

You claim “healthy unit economics” but don’t quote **ARPU, CAC, TAM adoption, or payback** in the memo. If those numbers are in Day 18, **put 2–3 in the memo** or VCs assume they’re hand-wavy. “Corrected-Cue ≥60%” is good **if** you explain what it is in one phrase.

**5. THE WEAKEST LINE**

> *“Cần vốn seed để làm pilot và scale.”*

**Rewrite direction:** Amount + **exact 12-month milestones** (users, metric, GTM). Seed investors fund a **plan**, not a verb “scale.”

---

## C. Quyết định Accept / Reject / Partial

| Điểm critique | Quyết định | Lý do ngắn |
|---------------|------------|-----------|
| 8 giây đầu: memo yếu, Twitter mạnh hơn | **Accept** | Cần thống nhất hook số liệu (71%) vào Problem / mở memo. |
| Insight còn obvious | **Accept** | Viết lại insight theo “feedback gap” + bối cảnh VN + in-set vs clip. |
| OpenAI threat chưa có câu trả lời | **Partial** | Đúng là cần moat rõ hơn; nhưng “OpenAI làm form-check” chưa bằng **bundle 3 bài + on-device + rule an toàn** — bổ sung 2 câu trong Solution/Traction, không lạm jargon. |
| Thiếu số trong memo | **Accept** | Trích TAM 50k, ARPU 499k, LTV/CAC healthy, pilot 100 user từ Day 17–18. |
| Ask mơ hồ | **Accept** | Ghi rõ **3 tỷ VNĐ**, 100 pilot, Corrected-Cue, 12 tháng. |
| Twitter >280 ký tự | **Accept** | Cắt bớt từ thừa, giữ 71% + differentiator + 1 proof + ask. |

---

## D. Pitch sau chỉnh (final — Step 5)

**Nguồn bản đầy đủ:** xem `pitch_memo.md` và `twitter_pitch.md` trong cùng thư mục (đã sửa theo các mục **Accept** và phần **Partial** ở trên).

### Twitter Pitch — final (256 ký tự)

```
71% user bỏ app fitness trước T3—thiếu phản hồi form trong set, không thiếu clip. AI PT Copilot: pose on-device, cue Squat/Push-up/Hinge <300ms, LLM tóm tắt buổi. TAM 50k, ARPU 499k, unit economics lành. Seed 3 tỷ→100 user pilot, target Corrected-Cue ≥60%.
```

### Thay đổi chính so với bản nháp

- Memo: 6 section đúng format Sequoia; Problem có **tần suất + số**; Insight **phản trực giác**; Solution **3 câu** với on-device + COGS; Proof gắn **Day 17–18**; Ask **số tiền + 12 tháng**.
- Twitter: **<280** ký tự; bỏ trùng lặp; giữ hook **71%**.
- Không copy-paste rewrite của AI nguyên văn — chỉ dùng làm gợi ý (theo §3.5).

---

## E. Tự kiểm 7 mục (§3.6)

- [x] Mở đầu ≤8s: số **71%** + thiếu phản hồi form trong set  
- [x] ≥1 insight phản trực giác: **feedback gap** (không phải “thiếu video”)  
- [x] ≥2 số cụ thể: **71%**, **TAM 50k**, **ARPU 499k**, **100 user**, **60%**, **3 tỷ** (≥2 thỏa)  
- [x] Differentiator: on-device + 3 lift + LLM summary vs ChatGPT/video  
- [x] Ask: **3 tỷ VNĐ**, pilot **100 user**, metric **Corrected-Cue**, **12 tháng**  
- [x] Script đọc to:** ~45–60 giây** (đo trong `twitter_pitch.md`)  
- [x] Audience Seed: vision + TAM/early proof + runway hợp lý  

---

## F. Checklist nộp (§5.4) — tự xác nhận

| # | Mục | Trạng thái |
|---|-----|------------|
| 1 | `pitch_memo.md` — 6 section | ✅ |
| 2 | `twitter_pitch.md` — <280 + script | ✅ |
| 3 | `ai_vc_critique_log.md` — gốc, feedback, quyết định, final | ✅ |
| 4 | Đọc to <60s | ✅ (luyện theo script) |
| 5 | 7 mục self-eval | ✅ |
| 6 | ZIP + LMS | Sinh viên nén & nộp trên LMS (ngoài repo) |

---

## G. Checkpoint buổi sáng (§5.1–5.2) — tóm tắt đã làm

### §5.1 — Stakeholder map (cuối Block 1)

| Câu hỏi | Trả lời ngắn (bài AI PT Copilot) |
|--------|-----------------------------------|
| **Lead VC lý tưởng (tên cụ thể)** | Ví dụ hướng research: **Do Ventures** hoặc quỹ seed Việt Nam có deal health/consumer — **bắt buộc** đối chiếu portfolio thật trước khi ghi tên vào slide. |
| **Foundation Model dependency + Plan B** | Core loop: **pose on-device** (không gửi video lên cloud). Summary: API LLM — **multi-vendor** (OpenAI / Anthropic); fallback: model nhỏ/local hoặc template tóm tắt nếu khóa API. |
| **Early Adopter community cụ thể** | **r/bodyweightfitness**; nhóm Facebook fitness VN / **Yêu Gym**; cohort VP 22–35 tập tại nhà (khớp Day 16 access path). |

### §5.2 — User hook (cuối Block 2)

- **Archetype:** The Skeptic.  
- **Hook (≤25 từ):** *Senior dev tập một mình: app phải hiện confidence + cho tắt cue — nếu không, nghi AI bịa và gỡ app trong 30 giây.*

---

## H. Round 2 critique (phản hồi AI thực tế từ user) + cập nhật quyết định

### Tóm tắt phản hồi Round 2 (partner-style)

- **8-second test:** pass "barely"; phải mở bằng spike **71% churn** thay vì mở bằng mô tả user chung.
- **Insight test:** "feedback gap" bị xem là generic; cần lớp sâu hơn: **trust under imperfect sensing**.
- **OpenAI threat:** on-device + rule-based chưa phải moat; cần trả lời rõ vì sao user không chuyển sang platform.
- **Numbers test:** chê over-modeled (TAM/adoption/ARPU/LTV-CAC) khi chưa có paid dữ liệu.
- **Weakest line:** "Unit economics healthy" làm giảm độ tin cậy ở giai đoạn pre-seed.

### Cập nhật Accept / Reject / Partial sau Round 2

| Điểm critique | Quyết định | Hành động đã làm |
|---------------|------------|------------------|
| Lead with 71% | **Accept** | Đổi opening trong `pitch_memo.md` và `twitter_pitch.md` để vào thẳng hook 71%. |
| Insight generic | **Accept** | Reframe insight thành **trust gap dưới sensing không hoàn hảo**. |
| Moat yếu trước OpenAI | **Partial** | Không claim moat "bất khả xâm phạm"; chuyển thành thesis về trust loop + dữ liệu correction theo bối cảnh VN cần kiểm chứng. |
| Over-modeled numbers | **Accept** | Bỏ claim chắc chắn về LTV/CAC trong memo; ghi rõ "chưa có CAC/paid retention thực tế". |
| Unit economics healthy (tone overclaim) | **Accept** | Thay bằng framing trung thực: round này để validate willingness-to-pay + retention 4 tuần trước scale. |

### Delta của bản final sau Round 2

- `pitch_memo.md`: từ "projection-driven" sang "validation-driven", giữ 6 sections nhưng giảm overclaim.
- `twitter_pitch.md`: đổi sang trust-first thesis, vẫn dưới 280 ký tự.
- Mục tiêu pitch: tăng độ tin cậy với Seed VC bằng honesty + test plan rõ, thay vì cố chứng minh mọi thứ đã solved.

---

## I. Round 3 critique (meaningfully better, but still breakable)

### Điểm chính AI vặn ở Round 3

- Hook 71% tốt hơn nhưng vẫn còn "internet-known", chưa phải dữ liệu riêng của team.
- Insight trust gap được đánh giá tốt, nhưng cần "operationalize": định nghĩa trust decay bằng biến đo cụ thể.
- OpenAI threat vẫn mong manh nếu chỉ nói local context/trust loop chung chung.
- Numbers honest hơn nhưng thiếu "execution thresholds" rõ để quyết định scale hay không.
- Câu "chạy trước platform ngang" bị đánh giá phòng thủ.

### Quyết định Round 3

| Điểm critique | Quyết định | Hành động đã làm |
|---------------|------------|------------------|
| Hook còn category-level | **Partial** | Giữ 71% để pass 8-second test, đồng thời chuyển trọng tâm sang giả thuyết đo được: trust collapse sau 1-2 cue sai. |
| Insight chưa đủ predictive | **Accept** | Sửa insight trong `pitch_memo.md` thành "optimize when NOT to cue", không chỉ nói feedback gap. |
| Moat chưa sắc | **Accept** | Nâng thesis thành dữ liệu **trust-calibration** (accepted/ignored, fatigue phase, camera condition) + ngưỡng theo user. |
| Numbers underpowered | **Accept** | Bổ sung pilot 100-150 user + Go/No-Go rõ: Corrected-Cue >= 60% và W4 retention >= 25% mới scale. |
| Strategic line yếu | **Accept** | Thay wording defensiveness bằng "vertical layer theo lịch sử vận động từng user" ngay trong WHY NOW + ASK. |

### Trạng thái sau Round 3

- `pitch_memo.md`: đã có hypothesis đo được + ngưỡng quyết định scale.
- `twitter_pitch.md`: cập nhật theo trust-collapse thesis, vẫn <280 ký tự.
- Bản pitch hiện tại phù hợp mục tiêu Day 19: rõ audience, có critique loop, có decision logic và hướng kiểm chứng thực nghiệm.
