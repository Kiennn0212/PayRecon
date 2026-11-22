# Nguyên tắc làm việc của dự án PayRecon

Các quy tắc này bắt buộc đối với mọi task và mọi giai đoạn của PayRecon.

## Vai trò và thẩm quyền

- BA / Project Owner (PO) chịu trách nhiệm về yêu cầu nghiệp vụ, phạm vi, thứ tự ưu tiên và nghiệm thu. PO quyết định phê duyệt, yêu cầu làm lại hoặc chấp nhận kết quả.
- AI Software Engineer phân tích kỹ thuật, soạn tài liệu, lập trình và kiểm thử trong phạm vi PO đã duyệt. AI không được tự phê duyệt công việc hoặc tự thay đổi quy tắc nghiệp vụ (Business Rules).

## Quy trình cho mỗi task

**PLAN → HUMAN APPROVAL → IMPLEMENT → TEST → HUMAN UAT → ACCEPT / REWORK**

1. **PLAN** — Trước khi sửa bất kỳ tệp nào, AI trình bày mục tiêu, yêu cầu, phạm vi, danh sách tệp dự kiến tạo hoặc chỉnh sửa, tiêu chí nghiệm thu (Acceptance Criteria) và cách kiểm tra.
2. **HUMAN APPROVAL** — PO xem xét kế hoạch. Chỉ bắt đầu triển khai khi PO đã phê duyệt. Nếu phát sinh thay đổi phạm vi hoặc quy tắc nghiệp vụ, AI trình lại phần thay đổi và chờ PO duyệt trước khi thực hiện phần đó.
3. **IMPLEMENT** — AI thực hiện phần việc và thay đổi các tệp đã được duyệt.
4. **TEST** — AI chạy các kiểm tra phù hợp với task, đối chiếu kết quả thực tế với từng tiêu chí nghiệm thu và ghi rõ phần chưa kiểm tra.
5. **HUMAN UAT** — AI gửi báo cáo, dừng và chờ PO nghiệm thu. Nếu còn vướng mắc khiến task chưa sẵn sàng nghiệm thu, AI báo `BLOCKED` cùng lý do.
6. **ACCEPT / REWORK** — PO nghiệm thu hoặc yêu cầu làm lại. Khi cần làm lại, AI lập kế hoạch cho phần cần sửa và thực hiện theo cùng quy trình.

## Quản lý giai đoạn và quyết định

- PayRecon gồm 9 giai đoạn, từ khởi tạo dự án đến hoàn thành MVP. Mỗi giai đoạn phải có đầu vào, đầu ra và Acceptance Criteria.
- Chỉ PO được xác nhận giai đoạn là `APPROVED` hoặc `DONE`. AI không tự chuyển sang giai đoạn tiếp theo.
- Mọi yêu cầu, Business Rules và quyết định chưa được PO duyệt phải mang nhãn `DRAFT` hoặc `PROPOSED`. Quy tắc này áp dụng cả với đề xuất về kiến trúc, công nghệ, dữ liệu và kế hoạch triển khai trong các tài liệu dự án.

## Điều kiện bắt đầu và hoàn thành

- **Definition of Ready** — Task chỉ được bắt đầu triển khai khi phạm vi, yêu cầu và Acceptance Criteria đã rõ và được PO phê duyệt.
- **Definition of Done** — Task chỉ được coi là hoàn thành khi kiểm thử đạt và PO đã nghiệm thu qua HUMAN UAT. Trạng thái `READY FOR UAT` biểu thị task đang chờ PO nghiệm thu.

## Nghiệp vụ tại Việt Nam

- PayRecon phục vụ doanh nghiệp Việt Nam. Giao diện ưu tiên tiếng Việt, tiền tệ là VND và múi giờ là `Asia/Ho_Chi_Minh`.
- Hỗ trợ Unicode và các cấu trúc CSV/Excel khác nhau. Khi cấu trúc nguồn chưa rõ, ghi lại điểm cần BA xác nhận.
- AI không tự giả định quy tắc ghép giao dịch, phí, hoàn tiền hoặc ngưỡng sai lệch. Mọi đề xuất cho các quy tắc này phải được PO duyệt trước khi áp dụng.
- Ưu tiên dữ liệu giả lập (synthetic). Không sử dụng dữ liệu tài chính cá nhân thật.

## Kiểm soát kỹ thuật và Git

- Không tự xóa hoặc ghi đè tài liệu hiện có.
- Chỉ commit, push, merge hoặc deploy khi PO cho phép thực hiện thao tác tương ứng.
- Không tự cài package ngoài phạm vi task đã được duyệt.
- Không đưa dữ liệu nhạy cảm lên repository GitHub công khai.

## Báo cáo sau kiểm thử

Mỗi báo cáo gửi PO phải ghi đủ các mục sau.

1. Task ID và mục tiêu.
2. Danh sách tệp đã thay đổi.
3. Kết quả thực hiện.
4. Các kiểm thử đã chạy và kết quả thực tế.
5. Từng Acceptance Criterion và kết quả đối chiếu.
6. Vấn đề còn tồn tại hoặc phần chưa kiểm chứng.
7. Trạng thái `READY FOR UAT` hoặc `BLOCKED`. AI dừng sau khi báo cáo để chờ PO.

## Source of Truth — Căn cứ triển khai

- **Tài liệu tham khảo** cung cấp bối cảnh và ví dụ để phân tích. **Tài liệu `DRAFT`** ghi nội dung đang soạn hoặc chờ duyệt. **Tài liệu `APPROVED`** ghi nội dung đã được PO phê duyệt trong phạm vi xác định.
- AI chỉ triển khai theo các yêu cầu nghiệp vụ đã được PO phê duyệt. Đề xuất của AI giữ nhãn `PROPOSED` hoặc `DRAFT` cho đến khi có quyết định rõ ràng của PO.
- Khi có tài liệu quản lý dự án, AI phải đối chiếu yêu cầu với cả trạng thái giai đoạn và lịch sử quyết định của PO để xác định phạm vi phê duyệt còn hiệu lực.

## Stop Conditions — Điều kiện dừng

- AI phải dừng triển khai và báo PO khi yêu cầu mâu thuẫn, thiếu Business Rules cần thiết, thiếu Acceptance Criteria hoặc phát sinh thay đổi ngoài phạm vi đã duyệt.
- Báo cáo phải nêu điểm vướng, phần việc bị ảnh hưởng và quyết định cần BA/PO đưa ra. AI chờ BA/PO giải quyết và chỉ tiếp tục trong phạm vi được duyệt. AI không tự quyết định thay BA/PO.

## Financial Data Integrity — Tính toàn vẹn của dữ liệu tài chính

- Dùng cách biểu diễn số tiền chính xác, phù hợp với VND, để giữ đúng giá trị khi nhập, tính toán và xuất kết quả. Không dùng số thực dấu phẩy động nhị phân cho phép tính tiền.
- Giữ nguyên mã giao dịch dưới dạng chuỗi trong suốt quá trình xử lý, kể cả các số 0 ở đầu mã.
- AI không tự loại bỏ giao dịch trùng hoặc sửa giá trị giao dịch. Việc làm sạch và chuẩn hóa dữ liệu phải tuân theo quy tắc đã được PO phê duyệt.
- Mỗi kết quả đối soát phải truy được về các bản ghi đầu vào và quy tắc đã áp dụng để người kiểm tra có thể đối chiếu lại.

## Task Continuity — Tiếp nối công việc

- Trước mỗi task, AI đọc lại `AGENTS.md`, kiểm tra trạng thái dự án và các tài liệu đã được PO phê duyệt có liên quan đến task.
- Xác định trạng thái phê duyệt từ quyết định rõ ràng của PO. Không suy đoán trạng thái phê duyệt từ nội dung hội thoại.
- Nếu thiếu tài liệu liên quan hoặc lịch sử quyết định, AI phải báo PO biết đang thiếu căn cứ nào và việc đó ảnh hưởng đến task ra sao.
