# Sổ quyết định PayRecon

**TASK-000B đã được PO nghiệm thu ngày 22/11/2026.** Tại mục 1 của chỉ dẫn «TASK-000B — ACCEPTANCE / TASK-000C — PLANNING», PO chấp nhận sổ này làm hồ sơ theo dõi. DEC-001 đến DEC-009 đều ở trạng thái `PROPOSED`, bao gồm việc lựa chọn phạm vi demo 8 tuần hoặc pilot trong lộ trình 16 tuần.

## Tài liệu tham khảo

- **KH8** là `PayRecon_Implementation_Plan_2026.docx`, kế hoạch 8 tuần cho bản demo đối soát giao dịch nội bộ với dữ liệu đối tác.
- **ĐH16** là `PayRecon_Bao_cao_dinh_huong_phat_trien_2026.docx`, báo cáo định hướng sản phẩm với lộ trình 16 tuần cho đối soát đơn hàng và sao kê, gồm discovery, MVP và pilot.

## Quyết định chờ PO

| ID | Câu hỏi cần quyết định | Phương án hoặc điểm BA/PO cần xác minh | Căn cứ tham khảo | Phạm vi ảnh hưởng | Trạng thái | Người duyệt | Ngày duyệt | Bằng chứng quyết định của PO |
|---|---|---|---|---|---|---|---|---|
| DEC-001 | Đầu ra ưu tiên là demo hay pilot? | BA/PO xác định phần nào thuộc demo nội bộ–đối tác theo KH8, phần nào thuộc pilot đơn hàng–sao kê theo ĐH16, có triển khai nối tiếp hay chọn một phạm vi, và ai sẽ nghiệm thu từng đầu ra. | KH8 §1.1–1.3, §2, §6 · ĐH16 §1.1, §4.2, §11 | Nguồn dữ liệu, phạm vi MVP, mốc triển khai và nghiệm thu | PROPOSED | — | — | — |
| DEC-002 | Khi nào dùng được khóa chung và quan hệ 1:1? | Với demo, kiểm tra mỗi bên cung cấp cùng `reference_id`, giữ mã dạng chuỗi kể cả số 0 đầu và chỉ có một bản ghi mỗi phía. Với đơn hàng–sao kê, xác minh mã tham chiếu thực sự xuất hiện ở đâu và cách chuyển ca thiếu mã hoặc nhiều ứng viên sang rà soát. | KH8 §1.3, §7.1–7.2 · ĐH16 §6.2–6.4 | Hợp đồng dữ liệu, khóa ghép, ngoại lệ và UAT | PROPOSED | — | — | — |
| DEC-003 | Số tiền nào có thể so sánh giữa hai nguồn? | Xác định từng cột là số tiền gộp trước phí (gross) hay số tiền thực nhận (net), chiều tiền vào/ra, tiền tệ và sai số được phép. Với VND, kiểm tra cách đọc và lưu số đồng chính xác theo định dạng nguồn. | KH8 §7.1–7.2, §11 · ĐH16 §6.2–6.4, §8.4, phụ lục A | Chuẩn hóa số tiền, kiểm tra chênh lệch và tổng theo tiền tệ | PROPOSED | — | — | — |
| DEC-004 | Khi nào có đủ chứng từ để giải thích phí và điều chỉnh? | Xác minh đối tác có cung cấp mã lô, bảng kê phí, khoản hoàn và điều chỉnh có dấu hay không. BA/PO quyết định cách xử lý thiếu bằng chứng và giai đoạn hỗ trợ đối soát tổng tiền về theo lô. | KH8 §7.1, §11–12 · ĐH16 §4.2, §6.3–6.4 (BR-03, BR-04), §7 (FR-14) | Đối soát settlement, phân bổ phí, hoàn tiền và truy vết chứng từ | PROPOSED | — | — | — |
| DEC-005 | So sánh hai mốc thời gian nào và khi nào báo lệch? | Xác minh thời điểm khách thanh toán, đối tác quyết toán hoặc ngân hàng ghi nhận. KH8 minh họa quy đổi UTC và gắn cờ khi lệch tuyệt đối **lớn hơn** 48 giờ. BA/PO cần xác nhận ngưỡng theo nguồn, giờ chốt kỳ theo `Asia/Ho_Chi_Minh` và cách xử lý tiền về sau kỳ. | KH8 §7.1–7.3 · ĐH16 §6.3–6.5 (BR-05, BR-07), phụ lục A | Nhãn lệch thời gian, khoản chờ tiền về và kỳ báo cáo | PROPOSED | — | — | — |
| DEC-006 | Thế nào là trùng và xử lý theo cấp nào? | KH8 đề xuất từ chối `transaction_id` trùng trong cùng nguồn và gắn `duplicate` khi các giao dịch khác nhau dùng cùng `reference_id`. ĐH16 còn xét nhập lại cùng tệp hoặc cùng dòng. BA/PO chốt cách nhận diện, giữ bản ghi và tính KPI để tránh cộng hai lần. | KH8 §7.1–7.3, §10.1 · ĐH16 §5.2, §6.3–6.5, phụ lục B (UAT-03) | Nhập liệu, đối soát, số tiền và số lượng giao dịch | PROPOSED | — | — | — |
| DEC-007 | KPI dùng đơn vị đếm, mẫu số và thời điểm nào? | Với demo, KH8 lấy số mã khớp chia số mã tham chiếu duy nhất trong một phiên chạy. Với pilot, ĐH16 theo dõi giao dịch đủ điều kiện đã xác nhận, cả theo số lượng và giá trị. BA/PO cần chốt mẫu số, cách xử lý ngoại lệ, kỳ báo cáo và cách tách tiền tệ. | KH8 §7.2–7.3, §8.2 · ĐH16 §9.1–9.2 | Từ điển KPI, báo cáo, dashboard và UAT | PROPOSED | — | — | — |
| DEC-008 | Cây thư mục nào phù hợp với đầu ra đã chọn? | KH8 bố trí `src/payrecon/`, `app/`, `sql/`, `data/sample/` và bộ tài liệu đánh số. ĐH16 gợi ý `docs/ba/`, `docs/data/`, `data/synthetic/` và `dashboards/`. BA/PO chọn vị trí duy nhất cho mỗi loại tài liệu và dữ liệu giả lập, giữ sao kê thật ngoài Git. | KH8 §4–4.1, §5, §13 · ĐH16 §10.2, §16.3 | Vị trí tài liệu, mẫu dữ liệu và mã nguồn cho các task sau | PROPOSED | — | — | — |
| DEC-009 | Công nghệ nào cần cho đầu ra đầu tiên và công nghệ nào để sau? | KH8 nêu Python, CLI, Streamlit và CSV cho demo rồi bổ sung PostgreSQL/Power BI. ĐH16 nêu FastAPI, PostgreSQL, React/Next.js cho sản phẩm và Streamlit cho prototype. Chốt công cụ cùng thời điểm áp dụng sau quyết định về phạm vi. | KH8 §1.3, §3, §6, §12 · ĐH16 §8.1–8.2, §11.2 | Kiến trúc, phụ thuộc, môi trường và kiểm thử | PROPOSED | — | — | — |

## Ghi nhận quyết định về sau

BA/PO xác nhận rõ mã quyết định, phương án, phạm vi và điều kiện áp dụng. Khi có xác nhận, cập nhật trạng thái, người duyệt, ngày duyệt và tham chiếu bằng chứng theo đúng nội dung PO đã duyệt. Phần còn mở tiếp tục mang nhãn `PROPOSED`. Nếu PO thay đổi một quyết định trước đó, giữ nguyên nội dung và bằng chứng cũ, thêm bản ghi có mã mới, dẫn lại mã bị thay thế và ghi rõ ngày bắt đầu áp dụng.

Ghi lần cập nhật vào [nhật ký thay đổi](change_log.md). Trước khi triển khai, đối chiếu quyết định với [trạng thái giai đoạn](phase_status.md), [điều kiện nghiệm thu](phase_checklist.md) và [quy tắc làm việc của dự án](../AGENTS.md).
