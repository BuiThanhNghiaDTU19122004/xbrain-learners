# Lịch học W7 — 28–30/05 (Capstone Hackathon)

**Phase 1 — Foundation · Capstone Hackathon**

**Chủ đề:** Ship Production-Ready AI in 48 Hours — dồn toàn bộ kỹ năng W1–W6 để ship một **AI SaaS Platform** chạy thật, deploy public, trên AWS account **cá nhân**.

> **Hình thức:** Tuần cuối **không có course/lab mới** — cả tuần là một hackathon.
> Build Day (28–29/5): **online / remote — tự quản 48h** (sprint đêm / chia ca / song song… tuỳ nhóm).
> Demo Day (30/5): **ONSITE** — trainer mở URL của nhóm và tương tác trực tiếp.
> 💰 **$100 HARD CAP** mỗi nhóm (tiền thật) · **Deadline cứng duy nhất = sáng T6 (30/5) 09:00 có URL chạy + slide sẵn.**

---

## Nội dung theo ngày

| Ngày | Hình thức | Nội dung |
|------|-----------|----------|
| 25–27/5 | Optional / remote | **Chuẩn bị (optional):** mở AWS account cá nhân (mỗi member 1 account, bật MFA root), chọn domain, chốt kiến trúc + chia vai. **KHÔNG dựng infra tốn tiền** giai đoạn này. |
| T4 (Wed 28/5) | Online / remote | **Build Day 1 (gợi ý):** Pre-flight check (Budget Alert $80 + confirm SNS, Cost Anomaly, tag resource) → architecture sign-off → deploy hạ tầng → happy path chạy được cuối ngày. |
| T5 (Thu 29/5) | Online / remote | **Build Day 2 (gợi ý):** tích hợp AI end-to-end + monitoring/cost + 1 năng lực optional + polish + Evidence Pack + **quay demo video dự phòng** + chuẩn bị slide. |
| T6 (Fri 30/5) | ONSITE | **Demo Day:** tất cả các nhóm báo cáo (slot ~40p/nhóm: Architecture Walkthrough + Live Demo + Individual QnA). |

> 📝 Build Day 1/Day 2 chỉ là **checkpoint gợi ý** cho nhóm chưa có plan. Nhóm có plan riêng cho 48h thì làm theo plan đó — chỉ deadline T6 09:00 là cứng.

---

## Đề bài — chọn 1 trong 3 domain

Mọi nhóm xây **cùng một stack kỹ thuật**; chỉ khác user story & loại tài liệu hệ thống xử lý.

- **A — EduTech · "AI Study Buddy":** upload PDF/slide → AI tóm tắt / flashcard / quiz / chat với nội dung. *Core challenge:* document intelligence (bảng, hình, layout nhiều cột, slide ảnh).
- **B — FinTech · "AI Money Coach":** upload sao kê (PDF/CSV) → AI phân loại giao dịch / phân tích chi tiêu / chatbot ngân sách.
- **C — ProductivityTech · "AI Document Hub":** multi-tenant — upload hợp đồng/tài liệu → AI search / Q&A / tóm tắt.

### 7 năng lực BẮT BUỘC (mọi nhóm phải demo đủ)
1. **User Interface** — public URL (HTTPS)
2. **Application Compute** — backend xử lý request + gọi AI + thao tác dữ liệu
3. **AI / ML Feature** — ≥1 tính năng AI chạy end-to-end (Bedrock InvokeModel hoặc KB+Agent…)
4. **Data Persistence** — lưu & đọc lại state qua các session
5. **Object Storage** — S3 cho file/blob
6. **Network Foundation** — tài nguyên cô lập đúng (DB **không** public)
7. **Identity & Access** — IAM least-privilege cho mọi service (login người dùng là tuỳ chọn)

> Nguyên tắc: **không chỉ định service** — nhóm tự chọn service đã học W1–W6 và phải giải thích được **lý do**.

### 3 năng lực TÙY CHỌN (kéo điểm cao hơn — làm tốt 1 cái hơn làm dở 3 cái)
8. **Full Observability** — CloudWatch dashboard + custom metric + alarm + Log Insights
9. **Advanced Cost Insights** — Cost Explorer + phân tích cost theo feature + Cost Anomaly alert
10. **Advanced Security** — chọn 1 hướng: Encryption (KMS) · Audit (CloudTrail/Config/Security Hub/GuardDuty) · Secrets · Network (WAF/Shield/Flow Logs)

### Bar cần đạt
> "Trainer, click this link. Log in with this test account. Upload this sample file. Watch the AI process it. We built it in 48 hours, on our own AWS account, for under \$100."

📄 Đề bài đầy đủ & rubric: [`../W7_project_announcement.md`](../W7_project_announcement.md) · Thể lệ (VI): [`../W7_hackathon_rules.txt`](../W7_hackathon_rules.txt) · Hướng dẫn: [`../W7_learner_guide.md`](../W7_learner_guide.md) · Ước tính chi phí: [`../W7_cost_estimates.md`](../W7_cost_estimates.md) · Starter apps: [`../starter_apps/`](../starter_apps/)
