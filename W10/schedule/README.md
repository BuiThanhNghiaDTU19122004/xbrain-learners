# Lịch học W10 — 15–19/06

**Phase 2 — Chuyên ngành**

- **CDO** — Reliability Engineering / Security & Hardening
- **AIO** — Auto-remediation & E2E

> **Nhịp học chuẩn:** Self study (T2–T4) → Online training Tech/Soft skills (T4) → Offline training (T5) → Lab practice → Presentation (T6). Mỗi buổi ~4h (AM + PM). Link TEAMS & giờ cụ thể được công bố đầu tuần.

---

## Nội dung tự học (Self study)

| Ngày | CDO | AIO |
|------|-----|-----|
| D1 | **RBAC + Admission Policy (OPA/Gatekeeper)** — Role, RoleBinding, ClusterRole; Service Accounts; `kubectl auth can-i`; OPA Rego; Gatekeeper (ConstraintTemplate vs Constraint); ValidatingAdmissionPolicy (K8s 1.30+); Audit vs Enforce | **Auto-remediation & Safety Guardrails** |
| D2 | **Secrets Rotation + Supply Chain Security** — AWS Secrets Manager; External Secrets Operator (ESO); Trivy image scanning; Cosign signing; Admission webhook signature verification; CVE exception policies | **Closed-loop Architecture + Workflow Orchestration** |
| D3 | **Platform Integration + Runbook + Cost Guard** — tích hợp components W8 → W10; ResourceQuota & LimitRange; Chaos testing; operational runbook; AWS Cost Anomaly Detection | **E2E AIOps Platform Design + Cross-team Spec** |

## Online training (Tech)
- **CDO:** TBD.
- **AIO:** E2E platform walkthrough; closed-loop demo; human-in-the-loop.

## Online training (Soft skills)
- **Customer Presentation Skills** — Gia Hưng
- **Incident Response & Post-Incident Review** — Nam Hồng

## Lab
- **CDO:** 6-risk cluster cleanup + cluster-level enforcement.
- **AIO:** Build closed-loop POC (detect → enrich → decide → dry-run → verify) + cross-team spec.
