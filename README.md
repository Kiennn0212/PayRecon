# PayRecon

PayRecon là dự án đối soát thanh toán dành cho doanh nghiệp Việt Nam. Kế toán cần đối chiếu khoản phải thu trong sổ nội bộ với khoản đối tác ghi nhận hoặc khoản tiền về tài khoản, rồi xác định giao dịch nào còn cần chứng từ để giải thích.

Ví dụ, cửa hàng ghi nhận một đơn hàng 500.000 đồng, còn bảng quyết toán ghi 495.000 đồng. Để giải thích khoản chênh 5.000 đồng, kế toán cần kiểm tra mã giao dịch, số tiền trước và sau phí cùng thời điểm ghi nhận ở từng nguồn. Chỉ riêng hai con số chưa đủ để kết luận có phí hay khách thanh toán thiếu.

## Hiện trạng và phạm vi

**Giai đoạn 0 · Khởi tạo và quản trị · `IN_PROGRESS`.** Repository hiện có tài liệu nghiệp vụ và hồ sơ quản lý. PO đã nghiệm thu bốn hồ sơ của TASK-000B. Phần mềm đối soát chưa được triển khai. [Trạng thái các giai đoạn](project-management/phase_status.md)

Hai phạm vi dưới đây đang chờ BA/Project Owner (PO) quyết định tại **DEC-001**, trạng thái `PROPOSED`.

| Phạm vi tham khảo | Bài toán dự kiến |
|---|---|
| Demo MVP 8 tuần | Minh họa đối soát theo lô giữa giao dịch nội bộ và bảng giao dịch hoặc quyết toán của đối tác trên hai tệp CSV giả lập. |
| Định hướng Pilot 16 tuần | Khảo sát quy trình của cửa hàng, phát triển MVP và thử nghiệm với người dùng quy trình đối chiếu đơn hàng với sao kê chuyển khoản hoặc QR. |

Khóa ghép, cách so sánh số tiền trước và sau phí, mốc thời gian, xử lý trùng và cách tính tỷ lệ khớp đang chờ DEC-002 đến DEC-007. Cấu trúc ứng dụng và công nghệ đang chờ DEC-008 và DEC-009. [Sổ quyết định](project-management/decision_log.md)

## Quy ước dữ liệu

Theo quy ước dự án, giao diện ưu tiên tiếng Việt và dữ liệu văn bản dùng Unicode. Đối với dữ liệu từ CSV hoặc Excel, dự án yêu cầu giữ mã giao dịch dạng chuỗi, kể cả số 0 ở đầu, biểu diễn chính xác số tiền VND và làm rõ mốc thời gian theo múi giờ `Asia/Ho_Chi_Minh`. Mỗi kết quả đối soát cần truy được về bản ghi nguồn và quy tắc đã được PO duyệt.

Khi có dữ liệu mẫu giả lập được PO duyệt, có thể theo dõi tệp CSV/Excel trong `data/sample/`. Git bỏ qua các định dạng này ở nơi khác. Các thư mục riêng tư và thư mục xuất kết quả vẫn được bảo vệ ngay cả khi nằm trong thư mục mẫu. [Quy tắc bỏ qua tệp](.gitignore)

Trước khi đưa tệp lên GitHub, cần rà soát danh sách tệp và nội dung thực tế, kể cả dữ liệu mẫu và `.env.example`. Các quy tắc bỏ qua chỉ xét đường dẫn. Dự án dùng dữ liệu giả lập và loại dữ liệu tài chính cá nhân thật khỏi bộ mẫu.

## Tài liệu để làm việc

- **Tìm nguồn của một yêu cầu.** Tra tên hai tài liệu nội bộ, phạm vi của từng tài liệu và hồ sơ dùng để xác minh quyết định. [Mục lục tài liệu nghiệp vụ](docs/README.md)
- **Bắt đầu một task.** BA/PO xác định phạm vi, phê duyệt và nghiệm thu. AI Software Engineer lập kế hoạch, thực hiện phần đã duyệt và báo cáo kiểm thử. [Quy tắc làm việc](AGENTS.md)
- **Chuẩn bị nghiệm thu.** Xem đầu vào, đầu ra, tiêu chí và bằng chứng cho từng giai đoạn. [Checklist các giai đoạn](project-management/phase_checklist.md)
- **Tra cứu thay đổi.** Kiểm tra yêu cầu trước và sau điều chỉnh, phạm vi bị ảnh hưởng và chỉ dẫn của PO. [Nhật ký thay đổi](project-management/change_log.md)
