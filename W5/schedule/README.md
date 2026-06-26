# Lịch học W5 — 11–15/05

**Phase 1 — Foundation**

**Chủ đề:** Networking — VPC hardening, API Gateway, EFS, Serverless, Backup

> **Hình thức:** ONLINE T2–T4, ONSITE T5–T6. Mỗi buổi ~4h (AM + PM). Nhịp: học liệu/Lab T2–T4 (online) → ôn tập/Lab T5 (onsite) → thuyết trình nhóm T6 (onsite).

---

## Nội dung học theo ngày

| Ngày | Hình thức | Nội dung |
|------|-----------|----------|
| T2 (Mon) | ONLINE | Configuring & Deploying VPCs with Multiple Subnets<br>Introduction to Amazon VPC (Lab)<br>AWS Network Connectivity Options<br>AWS Network — Monitoring & Troubleshooting<br>SimuLearn: Connecting VPCs (Lab)<br>Introduction to Amazon API Gateway (Lab) |
| T3 (Tue) | ONLINE | Amazon Bedrock AgentCore Gateway Tutorial (3h)<br>Amazon EFS Primer<br>SimuLearn: File Systems in the Cloud (Lab)<br>AWS Backup Getting Started |
| T4 (Wed) | ONLINE | AWS File Storage Services Getting Started<br>Architecting Serverless Applications<br>Scaling Serverless Architectures<br>Serverless Analytics |
| T5 (Thu) | ONSITE | Ôn tập, củng cố / Lab practice |
| T6 (Fri) | ONSITE | Thuyết trình nhóm (group presentation) |

> Học liệu: **Digital Course** + **Lab** (AWS Skill Builder / SimuLearn).
## Project — "The Network Fortress"

Tuần **hardening**: bọc một lớp bảo vệ quanh ứng dụng đang chạy. Mỗi tuần account workshop reset → redeploy stack trên account sạch, nhưng giữ nguyên kiến trúc/business domain/quyết định thiết kế từ W1.

**5 must-have:** network observable; security control enforce ở boundary; file layer chia sẻ được (EFS); API surface chuẩn (API Gateway có throttling); và **mọi resource có state phải có backup đã test restore thật**.

**"Done" chiều T6:** app deploy end-to-end chạy được, diagram khớp với thực tế trên console, có xử lý một feedback từ tuần trước.

📄 Chi tiết: [`../W5_project_announcement.md`](../W5_project_announcement.md) · [bản tiếng Việt](../W5_project_announcement_vi.md)
