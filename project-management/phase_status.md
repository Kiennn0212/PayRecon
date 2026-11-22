# Trạng thái các giai đoạn PayRecon

Đọc bảng này khi bắt đầu một task để xác định giai đoạn đang thực hiện. Trạng thái ban đầu của cả chín giai đoạn do PO chỉ định tại TASK-000B. Tên, phạm vi công việc và tiêu chí chi tiết của roadmap mang nhãn `PROPOSED` cho đến khi PO xác nhận.

| Giai đoạn | Tên dự kiến | Trạng thái | Công việc và tiêu chí nghiệm thu |
|---|---|---|---|
| 0 | Khởi tạo và quản trị | `IN_PROGRESS` | [Checklist 0](phase_checklist.md#giai-đoạn-0) |
| 1 | Xác định phạm vi MVP | `NOT_STARTED` | [Checklist 1](phase_checklist.md#giai-đoạn-1) |
| 2 | Đặc tả nghiệp vụ | `NOT_STARTED` | [Checklist 2](phase_checklist.md#giai-đoạn-2) |
| 3 | Đặc tả dữ liệu | `NOT_STARTED` | [Checklist 3](phase_checklist.md#giai-đoạn-3) |
| 4 | Thiết kế giải pháp | `NOT_STARTED` | [Checklist 4](phase_checklist.md#giai-đoạn-4) |
| 5 | Xây dựng MVP | `NOT_STARTED` | [Checklist 5](phase_checklist.md#giai-đoạn-5) |
| 6 | Kiểm thử tích hợp | `NOT_STARTED` | [Checklist 6](phase_checklist.md#giai-đoạn-6) |
| 7 | UAT nghiệp vụ | `NOT_STARTED` | [Checklist 7](phase_checklist.md#giai-đoạn-7) |
| 8 | Hoàn tất MVP | `NOT_STARTED` | [Checklist 8](phase_checklist.md#giai-đoạn-8) |

## Căn cứ cập nhật

- **22/11/2026 · TASK-000B.** PO cho phép tạo bốn tài liệu quản lý và yêu cầu giữ Giai đoạn 0 đang thực hiện. Các mục Git, tài liệu, rà soát trước commit và nghiệm thu được theo dõi riêng trong Checklist 0.
- **22/11/2026 · Nghiệm thu TASK-000B.** Tại mục 1 của chỉ dẫn «TASK-000B — ACCEPTANCE / TASK-000C — PLANNING», PO xác nhận TASK-000B hoàn thành và chấp nhận bốn hồ sơ làm nền tảng theo dõi dự án. Giai đoạn 0 tiếp tục `IN_PROGRESS`. DEC-001 đến DEC-009 tiếp tục `PROPOSED`.
- **22/11/2026 · Nghiệm thu TASK-000C.** Tại chỉ dẫn «TASK-000C — ACCEPTANCE / TASK-000D — PLAN», PO xác nhận TASK-000C `DONE` cho hai README, khung thư mục ban đầu và bản cập nhật `.gitignore`. Giai đoạn 0 tiếp tục `IN_PROGRESS`.
- Khi PO chỉ định thay đổi trạng thái, ghi giai đoạn, trạng thái cũ và mới, ngày và tham chiếu đến chỉ dẫn của PO tại mục này, rồi cập nhật dòng tương ứng trong bảng. Chỉ PO xác nhận `APPROVED` hoặc `DONE` và quyết định chuyển giai đoạn.
- Đối chiếu căn cứ nghiệp vụ tại [Sổ quyết định](decision_log.md), thay đổi phạm vi tại [Nhật ký thay đổi](change_log.md) và thẩm quyền nghiệm thu tại [AGENTS.md](../AGENTS.md).
