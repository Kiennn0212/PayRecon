# Mục lục tài liệu PayRecon

BA có thể bắt đầu từ [tổng quan PayRecon](../README.md), rồi chọn hồ sơ theo câu hỏi cần trả lời.

| Câu hỏi | Hồ sơ cần tra |
|---|---|
| Dự án đang ở giai đoạn nào? | [Trạng thái giai đoạn](../project-management/phase_status.md) ghi tiến độ và căn cứ cập nhật. Tại TASK-000C, Giai đoạn 0 đang `IN_PROGRESS`. |
| Cần bằng chứng gì để PO nghiệm thu? | [Checklist các giai đoạn](../project-management/phase_checklist.md) ghi đầu vào, đầu ra, tiêu chí và bằng chứng theo từng giai đoạn. |
| Quy tắc tính phí, ghép giao dịch hoặc lựa chọn công nghệ đã được duyệt chưa? | [Sổ quyết định](../project-management/decision_log.md) ghi câu hỏi còn mở, phương án, trạng thái và bằng chứng phê duyệt. |
| PO đã yêu cầu thay đổi điều gì và vì sao? | [Nhật ký thay đổi](../project-management/change_log.md) ghi nội dung trước và sau, phạm vi ảnh hưởng và chỉ dẫn của PO. |
| Ai có thẩm quyền duyệt yêu cầu và khi nào phải dừng để hỏi lại? | [Quy tắc làm việc](../AGENTS.md) quy định thẩm quyền của PO, căn cứ triển khai và quy trình nghiệm thu. |

## Hai tài liệu Word tham khảo

Hai tệp Word được lưu riêng ở thư mục gốc của bản làm việc cục bộ.

- `PayRecon_Implementation_Plan_2026.docx` trình bày Demo MVP 8 tuần, dùng dữ liệu giả lập để đối soát giao dịch nội bộ với bảng quyết toán của đối tác thanh toán.
- `PayRecon_Bao_cao_dinh_huong_phat_trien_2026.docx` trình bày định hướng sản phẩm 16 tuần, từ khảo sát bài toán đối soát đơn hàng với sao kê ngân hàng đến thử nghiệm Pilot.

## Cách xác định yêu cầu được phép triển khai

Tài liệu tham khảo cung cấp bối cảnh và ví dụ. Nhãn `DRAFT` chỉ nội dung đang soạn hoặc chờ duyệt. Nhãn `PROPOSED` chỉ phương án đang trình PO. Trước khi dùng một yêu cầu để triển khai, BA kiểm tra phạm vi `APPROVED` và bằng chứng quyết định của PO trong hồ sơ liên quan.

PO đã nghiệm thu bốn hồ sơ quản lý tại TASK-000B. Tại TASK-000C, cả chín quyết định vẫn là `PROPOSED`. Tra DEC-001 khi cần xác định phạm vi Demo MVP hoặc Pilot, DEC-008 cho cấu trúc sản phẩm và DEC-009 cho lựa chọn công nghệ.
