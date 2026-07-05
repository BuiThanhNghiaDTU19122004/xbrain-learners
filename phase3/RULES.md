# Thể lệ Phase 3 - TechX Corp Service Takeover

## 1. Bối cảnh & mục tiêu
Phase 3 mô phỏng đúng việc một kỹ sư làm khi vào công ty: **tiếp quản một sản phẩm AI đang chạy production**, vận hành nó, cải tiến nó, và bảo vệ được mọi quyết định của mình.

Khác với Phase 2 (nhận đề bài rồi build), Phase 3 **không phát brief**. Các bạn nhận một hệ thống đang sống - có khách hàng, có SLA, có ngân sách, có nợ kỹ thuật, có sự cố - và phải tự tìm ra việc cần làm, tự ưu tiên, rồi delivery dưới ràng buộc thật.

Mục tiêu cá nhân: chứng minh bạn có thể **own một service** - không chỉ code, mà là judgment, vận hành, đánh đổi business, và giao tiếp.

## 2. Cấu trúc
Ba tầng, mỗi tầng một vai trò:

| Tầng | Đơn vị | Vai trò |
|---|---|---|
| Vận hành / thi đấu | **4 Task Force (TF)** | Mỗi TF cùng vận hành 1 service trên 1 account riêng |
| Kèm cặp | **13 nhóm** (9 CDO + 4 AIO) | Mỗi nhóm **1 mentor kèm cặp**, theo sát cả kỳ |
| Chấm cá nhân | **4 TF** | Mỗi TF **2 mentor chấm**, chấm điểm cá nhân độc lập (double-blind) trên toàn TF |
| Tổng hợp / quyết định | **Ban tổ chức** | Tổng hợp điểm, chọn hire |

**Chia TF** (mỗi TF = 1 nhóm AIO + 2-3 nhóm CDO):

| TF | AIO | CDO |
|---|---|---|
| TF1 | AIO01 | CDO05, CDO09 |
| TF2 | AIO02 | CDO03, CDO06 |
| TF3 | AIO04 | CDO01, CDO02 |
| TF4 | AIO03 | CDO04, CDO07, CDO08 |

Mỗi TF vận hành như một mini product org, chạy song song 2 luồng: **Operate** (giữ đèn sáng - on-call, incident, SLO, fix điểm yếu) và **Build** (ship cải tiến / feature mới trên product). Build gì là do các bạn tự đánh giá hệ thống rồi đề xuất trong backlog - không có checklist phát sẵn. Nhóm CDO nghiêng về platform/hạ tầng (autoscaling, observability, security, cost, reliability qua Helm/IaC/config), nhóm AIO nghiêng về tầng AI (chất lượng, guardrail, eval, chi phí model).

Trong 1 TF: các nhóm CDO lo hạ tầng/platform, nhóm AIO lo tầng AI - cùng giữ cho một service khỏe. Đây là làm việc cross-functional thật, và cũng là một tiêu chí được đánh giá.

## 3. Sân chơi
Ban tổ chức cấp **source code + một image seed** của một sản phẩm AI thương mại TechX Corp. Mỗi TF **tự build image → đẩy lên ECR của account mình → deploy → vận hành**. Việc dựng và đưa hệ thống lên chạy chính là bước tiếp quản đầu tiên. Đây là hệ thống hoàn chỉnh: nhiều microservice, Kubernetes, hàng đợi, cơ sở dữ liệu, một tính năng AI, và đầy đủ observability (metrics, logs, traces, dashboard).

Hệ thống này **không hoàn hảo** - nó có sẵn những điểm chưa tối ưu về chi phí, bảo mật, độ tin cậy, khả năng mở rộng, khả năng truy vết. Nhiệm vụ của các bạn là tìm ra, ưu tiên, và xử lý chúng như một đội vận hành thật.

## 4. Năm trụ + trụ AI
Công việc CDO chia theo **5 trụ**:

1. **Cost** - tối ưu chi phí hạ tầng.
2. **Security** - bảo mật, hardening.
3. **SLA / SRE** - độ tin cậy, xử lý sự cố, giữ SLO.
4. **Scale** - khả năng mở rộng, chịu tải, multi-tenant.
5. **Auditability** - truy vết được ai làm gì, khi nào (K8s audit, cloud trail, change management, log integrity).

Nhóm AIO trong mỗi TF giữ **trụ AI** riêng: vận hành và cải tiến tầng AI (chất lượng, chi phí, bảo mật, độ tin cậy của tính năng AI). Trụ AI không nằm trong 5 trụ CDO dưới đây.

**Phân trụ trong mỗi TF** (Auditability là trụ linh hoạt vì nó nhẹ hơn và xuyên suốt mọi thay đổi):

*TF có 2 nhóm CDO* - mỗi nhóm 2 trụ core, Auditability chung:
| Nhóm | Trụ |
|---|---|
| Nhóm A (winner Phase 2) | 2 trụ core tự chọn (vd Cost + Scale) |
| Nhóm B | 2 trụ core còn lại (Security + SLA) |
| Cả hai | Auditability (luân phiên, mỗi tuần 1 nhóm cầm chính) |

*TF có 3 nhóm CDO* - chia 2+2+1:
| Nhóm | Trụ |
|---|---|
| Nhóm A (winner Phase 2) | 2 trụ core tự chọn (vd Cost + Security) |
| Nhóm B | 2 trụ core còn lại (SLA + Scale) |
| Nhóm C | Auditability (đào sâu 1 mảng) |

**Pick (draft):** thứ tự theo hạng Phase 2, nhóm dẫn đầu chọn trước; snake draft trên 4 trụ core, chọn từng trụ một. Được chọn trụ mình muốn là phần thưởng cho nhóm dẫn đầu.

**Tĩnh để sở hữu, xoay để đánh giá:** home-pillar là chủ sở hữu chính (giữ tính liên tục + trách nhiệm). Nhưng khi **on-call trực, bạn xử lý bất kỳ trụ nào ập tới** (sự cố cost, security, hay audit đều vào người trực). Rotation này đảm bảo mọi người lộ đủ năng lực - đây là cái ban tổ chức dùng để so sánh khi chọn hire.

## 5. Timeline 3 tuần

**Tuần 1 - Tiếp quản & Bảo vệ ưu tiên**
- Onboard: đọc tài liệu, hiểu kiến trúc, SLO, ngân sách, lịch sử sự cố.
- Tự đánh giá hệ thống, dựng **backlog ưu tiên** (theo rủi ro × tác động business).
- Cuối tuần: **Pitch bảo vệ ưu tiên** trước hội đồng (đóng vai PM/CFO/SRE lead) - hội đồng sẽ phản biện. Đây là mốc đánh giá tư duy quan trọng nhất.

**Tuần 2-3 - Vận hành & Cải tiến dưới ràng buộc**
- Trực **on-call** luân phiên, xử lý những gì phát sinh.
- Thực thi backlog đã pitch - nhưng **không đủ thời gian làm hết**, phải chọn.
- Chịu ràng buộc thật: ngân sách có trần, SLO có error budget, stakeholder đòi hỏi trái chiều.
- Mỗi tuần có **Ops Review**: báo cáo trạng thái service (SLO, ngân sách, sự cố, backlog đã xử).

**Kết thúc - Service Health Readout (điểm NHÓM)**
- Mỗi TF trình bày: đã làm gì, đánh đổi gì, vì sao, trạng thái service ra sao, tiếp theo là gì.
- Hội đồng **chỉ nghe và phản biện (bắt bẻ)** - phản biện nhắm vào quyết định và trạng thái service của cả đội. Có thể hỏi thẳng một cá nhân để kiểm chứng chiều sâu, nhưng **không công bố hay chấm điểm cá nhân trong phòng**.
- **Điểm đầu ra của buổi này là điểm NHÓM/TF**, không phải điểm cá nhân. Cách một người phản hồi khi bị bắt bẻ chỉ là một quan sát để **2 mentor chấm của TF** ghi vào scorecard cá nhân (kênh riêng, mục 8) - không thành một con điểm ngay tại pitch.

## 6. Nhịp vận hành
- **Standup mỗi ngày**: báo trạng thái, bàn giao ca on-call. Mentor của nhóm theo sát.
- **Weekly Ops Review**: mốc kiểm tra hằng tuần.
- **Sự cố sẽ đến**: hệ thống sẽ gặp trục trặc do ban tổ chức tạo ra trong quá trình vận hành. Nhiệm vụ là **phát hiện và xử lý**, giữ cho khách hàng ít bị ảnh hưởng nhất.

## 7. Sản phẩm phải nộp (deliverables)
- **Backlog ưu tiên** + bản pitch (Tuần 1).
- **Decision log / ADR ký tên** cho mọi quyết định lớn.
- **Postmortem / COE ký tên** sau mỗi sự cố.
- **Ops Review** hằng tuần.
- **Service Health Readout** cuối kỳ (chấm điểm NHÓM; hội đồng nghe + bắt bẻ, có thể hỏi thẳng cá nhân để kiểm chứng nhưng không chấm điểm cá nhân trong phòng).

## 8. Cách chấm & chọn hire
Không chấm "code được bao nhiêu" mà chấm **6 chiều năng lực**:
1. Judgment & ưu tiên (chọn đúng việc đáng làm).
2. Engineering & Ops excellence (xử lý đúng gốc, không tạo lỗi mới).
3. Product & business trade-off (quy quyết định về chi phí, khách hàng).
4. AI Engineering (AIO) / Reliability (CDO).
5. Communication (postmortem, quản lý stakeholder).
6. Leadership / ownership.

**Hai kênh điểm TÁCH RỜI - không trộn trong phòng pitch:**

| Kênh | Nguồn điểm | Ai chấm | Dùng để |
|---|---|---|---|
| **NHÓM** | Ops Review hằng tuần + Service Health Readout cuối + sức khỏe service đo được (SLO, xử incident, cải tiến) | Hội đồng - chỉ nghe + bắt bẻ | Xếp hạng 4 TF/nhóm |
| **CÁ NHÂN** | Quan sát liên tục 3 tuần: ca on-call, ADR/decision log ký tên, COE, standup, cách xử lý khi bị bắt bẻ | **2 mentor/TF, chấm ĐỘC LẬP** rồi đối chiếu | Quyết định hire |

**Hai vai mentor tách biệt:**
- **Mentor kèm nhóm** (1/nhóm, 13 người): theo sát, kèm cặp, gỡ vướng cho nhóm mình cả kỳ. **Không phải người chốt điểm cá nhân** - chỉ cung cấp quan sát.
- **Mentor chấm** (2/TF, 8 người): chấm điểm cá nhân toàn TF trên **một thang chung** để so sánh công bằng trong TF, dựa trên quan sát cả kỳ + input từ mentor kèm nhóm + on-call/ADR/COE.

- **Điểm cá nhân KHÔNG lấy từ buổi pitch.** Buổi pitch cho ra điểm nhóm; điểm cá nhân đến từ việc-làm-thật cả kỳ.
- **2 mentor/TF chấm độc lập** (double-blind): mỗi mentor điền scorecard riêng, không thấy điểm người kia. Lệch > 1.0 ở một tiêu chí thì họp reconcile; điểm cuối là trung bình sau reconcile. Ban tổ chức tổng hợp.
- **Vì sao tách:** (1) chấm cá nhân ngay trong pitch sẽ đẩy người ta cướp mic, present để ăn điểm; (2) tách vai kèm cặp khỏi vai chấm để mentor kèm nhóm không thiên vị nhóm mình. Cả nhóm cùng lo readout tốt (điểm nhóm), điểm cá nhân do 2 mentor/TF chấm trên thang chung.

**Chọn hire:** xếp hạng cá nhân **trong từng cohort** (CDO so với CDO, AIO so với AIO), phân bổ theo tỉ lệ sĩ số hai cohort. Tổng: **30 vị trí**.

## 9. Luật chơi
- **Tự build từ source ban tổ chức cấp → đẩy image lên ECR của TF → deploy trên account của TF.**
- **Sự cố là để xử lý, không phải để tắt.** Cơ chế tạo sự cố do ban tổ chức kiểm soát. **Nghiêm cấm** can thiệp, vô hiệu hóa, hay đổi hướng cơ chế này. Vi phạm = **loại khỏi vòng đánh giá (disqualify)**.
- **Đường dây đọc flag là hạ tầng được bảo vệ.** flagd và các hook OpenFeature có sẵn trong service lõi chính là cách ban tổ chức bơm sự cố vào hệ thống của bạn. Gỡ bỏ, vô hiệu, hay refactor để service không còn đọc flag incident nữa được xem như đổi hướng cơ chế sự cố - **disqualify** ngang với re-point flagd. Muốn chịu được sự cố thì làm hệ thống bền hơn (fallback, retry, containment), không tháo đường dây đang có. Bạn vẫn được tự thêm flag/feature mới của mình.
- Điểm yếu do cấu hình (thiếu sót thật trong hệ thống) thì **sửa tận gốc**; sự cố do ban tổ chức bơm vào thì **làm hệ thống chịu được** (fallback, retry, containment) chứ không "tắt cho hết lỗi".
- Fair play: mọi quyết định phải truy được về người (ký tên). Không mượn kết quả của TF khác.
- Tôn trọng ràng buộc: không vượt ngân sách, không phá SLO của nhau.

## 10. Kết quả
- **TF vận hành tốt nhất.**
- **Cá nhân xuất sắc nhất** mỗi cohort.
- **30 vị trí hire.**

Phase 3 đo đúng thứ khó dạy nhất và quan trọng nhất khi đi làm: khả năng nhìn ra vấn đề, vận hành dưới áp lực, đánh đổi có lý, và chịu trách nhiệm với quyết định của mình. Chúc các đội giữ được service khỏe và tỏa sáng.
