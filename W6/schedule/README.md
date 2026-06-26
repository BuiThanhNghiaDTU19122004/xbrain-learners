# Lịch học W6 — 18–22/05

**Phase 1 — Foundation**

**Chủ đề:** Operations & Security — CloudWatch, auto-scaling, cost, KMS, security

> **Hình thức:** ONLINE T2–T4, ONSITE T5–T6. Mỗi buổi ~4h (AM + PM). Nhịp: học liệu/Lab T2–T4 (online) → ôn tập/Lab T5 (onsite) → thuyết trình nhóm T6 (onsite).

---

## Nội dung học theo ngày

| Ngày | Hình thức | Nội dung |
|------|-----------|----------|
| T2 (Mon) | ONLINE | SimuLearn: Auto-Healing & Scaling Applications (Lab)<br>SimuLearn: Highly Available Web Applications (Lab)<br>Amazon S3 Cost Optimization<br>Deep Dive: Amazon EBS Cost Optimization<br>SimuLearn: Cloud Economics (Lab)<br>AWS Storage Gateway Deep Dive: Volume Gateway |
| T3 (Tue) | ONLINE | AWS Storage Gateway Deep Dive: S3 File Gateway<br>AWS Backup Primer<br>Amazon CloudWatch Getting Started<br>AWS Organizations Getting Started<br>Securing & Protecting Your Data in Amazon S3<br>Protecting Your Instance with Security Groups |
| T4 (Wed) | ONLINE | AWS Security Best Practices: Monitoring & Alerting<br>Introduction to the AWS Cloud Adoption Framework (CAF)<br>SimuLearn: Core Security Concepts (Lab)<br>Performing a Basic Audit of your AWS Environment (Lab)<br>Introduction to AWS Key Management Service (Lab)<br>SimuLearn: Design Modern Data Architectures with Agentic AI (Lab) |
| T5 (Thu) | ONSITE | Ôn tập, củng cố / Lab practice |
| T6 (Fri) | ONSITE | Thuyết trình nhóm (group presentation) |

> Học liệu: **Digital Course** + **Lab** (AWS Skill Builder / SimuLearn).
## Project — "Operations Hardening & Cost-Aware Cloud"

W6 không thêm tầng năng lực mới — lấy đúng app đã build từ W1→W5, redeploy chiều T2 và hỏi: **vận hành được không?** Nguyên tắc tuần: **demonstrable, not documented**.

**4 lớp vận hành phải show trực tiếp:**
- **Cost Visibility & Attribution** — tag được activate trong Billing console, quy về từng workload.
- **Cost Control & Action** — automation thực sự đã dừng resource lãng phí.
- **Monitoring** — CloudWatch alarm có data để đánh giá (không kẹt INSUFFICIENT_DATA).
- **Self-Healing Security Guard** — đã trigger vi phạm và xem auto-remediation tự sửa.

**"Done" chiều T6:** recap ngắn về project (app, domain, thiết kế carry-forward) + walkthrough trực tiếp 4 must-have trên app vừa redeploy.

📄 Chi tiết: [`../W6_project_announcement.md`](../W6_project_announcement.md) · [bản tiếng Việt](../W6_project_announcement_vi.md)
