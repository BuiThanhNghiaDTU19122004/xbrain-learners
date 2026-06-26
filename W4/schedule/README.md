# Lịch học W4 — 04–08/05

**Phase 1 — Foundation**

**Chủ đề:** Data Pipelines & ML — ETL, analytics, Machine Learning

> **Hình thức:** ONLINE T2–T4, ONSITE T5–T6. Mỗi buổi ~4h (AM + PM). Nhịp: học liệu/Lab T2–T4 (online) → ôn tập/Lab T5 (onsite) → thuyết trình nhóm T6 (onsite).

---

## Nội dung học theo ngày

| Ngày | Hình thức | Nội dung |
|------|-----------|----------|
| T2 (Mon) | ONLINE | Data Engineering on AWS — Foundations (4h)<br>Amazon EMR Getting Started<br>AWS Glue Getting Started<br>Introduction to Amazon Athena |
| T3 (Tue) | ONLINE | Amazon Redshift Getting Started<br>Amazon OpenSearch Service Getting Started<br>Amazon Aurora Getting Started<br>Amazon Kinesis Data Streams — Getting Started<br>Data Modeling for Amazon Neptune<br>Data Modeling for ElastiCache for Redis<br>Amazon Connect Data Streaming Intermediate |
| T4 (Wed) | ONLINE | Amazon DynamoDB — Data Modeling Techniques<br>Introduction to Amazon DynamoDB (Lab)<br>Sensitive Data Detection with Amazon Macie<br>Introduction to ML: Art of the Possible<br>ML Essentials for Business & Technical Decision Makers<br>Machine Learning Exam Basics<br>Developing Machine Learning Solutions |
| T5 (Thu) | ONSITE | Ôn tập, củng cố / Lab practice |
| T6 (Fri) | ONSITE | Thuyết trình nhóm (group presentation) |

> Học liệu: **Digital Course** + **Lab** (AWS Skill Builder / SimuLearn).
## Project — "Build an AI That Actually Answers"

Xây hệ thống AI trả lời câu hỏi về **GeekBrain** (fintech startup, 6 service) dựa trên data package được cấp. Hệ thống phải trả lời ở **4 cấp độ luỹ tiến**:

- **L1 — Retrieval (Simple RAG):** fact nằm trong một tài liệu.
- **L2 — Multi-doc / tổng hợp:** ghép thông tin nhiều nguồn.
- **L3 — Tools:** gọi tool/agent để lấy trạng thái hệ thống live.
- **L4 — Memory/orchestration:** agent có bộ nhớ phiên, điều phối nhiều bước.

Tự build (LangChain/LlamaIndex/raw API) hoặc dùng managed **Amazon Bedrock AgentCore** — yêu cầu & pass condition như nhau.

**"Done" chiều T6:** demo hệ thống trả lời đúng ở các cấp độ; level cao hơn yêu cầu nền tảng level thấp hoạt động.

📄 Chi tiết: [`../W4_project_announcement.md`](../W4_project_announcement.md) · [bản tiếng Việt](../W4_project_announcement_vi.md)
