# Nhật ký thay đổi phạm vi và yêu cầu

Mỗi yêu cầu thay đổi có một mã `CHG`. Ghi nội dung trước và sau, lý do, phạm vi ảnh hưởng, chỉ dẫn của PO và tình trạng áp dụng. Với thay đổi còn chờ quyết định, ghi `PROPOSED` và để trống căn cứ phê duyệt. Khi có kết quả triển khai hoặc nghiệm thu, bổ sung mốc mới kèm bằng chứng để giữ lịch sử.

## Yêu cầu thay đổi

| Mã | Ngày đề nghị | Người đề nghị | Nội dung trước | Điều chỉnh và lý do | Phạm vi ảnh hưởng | Căn cứ và tình trạng áp dụng |
|---|---|---|---|---|---|---|
| CHG-001 | 22/11/2026 | BA/PO | Kế hoạch TASK-000B mô tả Giai đoạn 0 qua bốn hồ sơ quản lý và tiêu chí về mã, trạng thái, nguồn đề xuất. | Theo dõi cả Git/GitHub, AGENTS.md và .gitignore, README, cấu trúc repository, rà soát dữ liệu nhạy cảm, nghiệm thu và quyền commit đầu tiên. Ghi tiến độ theo bằng chứng cho từng việc. | Checklist Giai đoạn 0 | TASK-000B, chỉ dẫn HUMAN APPROVAL / IMPLEMENTATION của PO, mục 1. Đã cập nhật hồ sơ và được PO nghiệm thu trong TASK-000B. |
| CHG-002 | 22/11/2026 | BA/PO | Kế hoạch chia 9 giai đoạn, một số nhóm việc chỉ thể hiện dưới tên chung như thiết kế, xây dựng và bàn giao. | Giữ 9 giai đoạn và thể hiện rõ phân tích phạm vi, đặc tả dữ liệu và quy tắc, giao diện, Technical Setup, Reconciliation Engine, Dashboard/Reporting, kiểm thử tích hợp, UAT, Deployment, Documentation và Portfolio. | Checklist Giai đoạn 1–8 và cách đọc roadmap | TASK-000B, chỉ dẫn HUMAN APPROVAL / IMPLEMENTATION của PO, mục 2. Đã cập nhật hồ sơ và được PO nghiệm thu trong TASK-000B. |
| CHG-003 | 22/11/2026 | BA/PO | Giai đoạn 0 là `IN_PROGRESS`. TASK-000D đã bàn giao kết quả push, chờ PO nghiệm thu. | PO đã kiểm tra commit trên GitHub và nghiệm thu TASK-000D. Giai đoạn 0 chuyển sang `DONE` theo quyết định `APPROVED / DONE`. | Trạng thái quản lý Giai đoạn 0. Các giai đoạn 1–8 vẫn `NOT_STARTED`, DEC-001 đến DEC-009 vẫn `PROPOSED`. | «TASK-000D — FINAL ACCEPTANCE / PHASE 0 CLOSURE». Commit được PO chấp nhận là `ddcb202764ee487dd806b13de81f811c89fab799`. |

CHG-001 và CHG-002 điều chỉnh **nội dung tài liệu quản lý**. Người thực hiện các công việc sản phẩm sau này cần kiểm tra quyết định của PO cho từng phạm vi tương ứng. Chín quyết định khởi tạo từ DEC-001 đến DEC-009 đang ở trạng thái `PROPOSED`.

**Mốc nghiệm thu ngày 22/11/2026.** Tại mục 1 của chỉ dẫn «TASK-000B — ACCEPTANCE / TASK-000C — PLANNING», PO chấp nhận bốn hồ sơ sau bàn giao. Mốc này kết thúc phần việc tài liệu của CHG-001 và CHG-002. Giai đoạn 0 tiếp tục `IN_PROGRESS`.

Đối chiếu [Checklist các giai đoạn](phase_checklist.md), [Sổ quyết định](decision_log.md), [Trạng thái giai đoạn](phase_status.md) và [quy trình phê duyệt](../AGENTS.md).
