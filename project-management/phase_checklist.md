# Checklist các giai đoạn PayRecon

[Bảng trạng thái](phase_status.md) ghi tiến độ hiện tại. Checklist ghi công việc, đầu vào, đầu ra, tiêu chí nghiệm thu và bằng chứng cho từng giai đoạn. PO đã nghiệm thu Giai đoạn 0. Phân bổ công việc và tiêu chí chi tiết của các giai đoạn 1–8 vẫn là `PROPOSED`. PO sẽ xác định phạm vi Demo MVP/Pilot qua DEC-001 trong [Sổ quyết định](decision_log.md).

## Giai đoạn 0

**Khởi tạo và quản trị.** Đầu vào gồm kết quả phân tích TASK-000, hai tài liệu Word, hiện trạng Git, [AGENTS.md](../AGENTS.md) và chỉ dẫn triển khai TASK-000B của PO.

| Công việc | Kết quả nghiệm thu | Bằng chứng |
|---|---|---|
| Phân tích hiện trạng và rà soát hai tài liệu định hướng, triển khai | Đạt | PO xác nhận kết quả phân tích TASK-000 khi giao TASK-000B. Hai phạm vi 8 tuần và 16 tuần đã được nhận diện. |
| Khởi tạo Git | Đạt | Nhánh `main` có commit đầu tiên với thông điệp `chore: initialize PayRecon project governance`. |
| Kết nối GitHub | Đạt | Push lên `Kiennn0212/PayRecon` thành công. Nhánh `main` cục bộ theo dõi `origin/main`. Hash trên GitHub khớp với commit cục bộ khi bàn giao. |
| Thiết lập AGENTS.md và .gitignore | Đạt | Hai tệp có ở thư mục gốc. TASK-000A đã thiết lập quy tắc làm việc. TASK-000 đã kiểm tra quy tắc bỏ qua DOCX gốc, dữ liệu cục bộ và ngoại lệ cho `.env.example`. |
| Thiết lập bốn hồ sơ quản lý dự án | Đạt · TASK-000B `DONE` | Ngày 22/11/2026, PO chấp nhận bốn hồ sơ làm nền tảng theo dõi dự án tại mục 1 của chỉ dẫn «TASK-000B — ACCEPTANCE / TASK-000C — PLANNING». |
| Tạo README.md | Đạt · TASK-000C `DONE` | PO chấp nhận README gốc và mục lục tài liệu trong `docs/` tại chỉ dẫn «TASK-000C — ACCEPTANCE / TASK-000D — PLAN» ngày 22/11/2026. |
| Thiết lập cấu trúc repository ban đầu | Đạt · TASK-000C `DONE` | PO đã nghiệm thu hai README, thư mục `docs/` và phần cập nhật `.gitignore`. Bốn hồ sơ `project-management/` đã được nghiệm thu tại TASK-000B. Cấu trúc ứng dụng tiếp tục chờ DEC-008. |
| Rà soát tài liệu và dữ liệu nhạy cảm trước khi commit | Đạt | TASK-000D đã rà soát nội dung và diff của tám tệp được PO duyệt. Không phát hiện dữ liệu tài chính cá nhân hoặc bí mật cấu hình. Cây tệp trên GitHub khớp cả tám tệp và không chứa hai DOCX nội bộ. |
| Nghiệm thu khởi tạo và phê duyệt commit đầu tiên | Đạt · TASK-000D `DONE` | PO cho phép tạo commit tại «TASK-000D — HUMAN APPROVAL: INITIAL COMMIT», sau đó cho phép push. Sau khi kiểm tra kết quả trên GitHub, PO nghiệm thu commit và đóng giai đoạn. |

**Đầu ra đã bàn giao.** Repository GitHub có khung thư mục ban đầu, hai README, `AGENTS.md`, `.gitignore` và bốn hồ sơ quản lý.

**Kết quả nghiệm thu.** Cả chín công việc trên đều đạt. PO đã kiểm tra README, cấu trúc repository và chấp nhận danh sách tám tệp sau rà soát dữ liệu nhạy cảm.

**Quyết định của PO ngày 22/11/2026.** Theo «TASK-000D — FINAL ACCEPTANCE / PHASE 0 CLOSURE», TASK-000D là `DONE` và Giai đoạn 0 là `APPROVED / DONE`. PO đã chấp nhận commit `ddcb202764ee487dd806b13de81f811c89fab799` trên `origin/main`. [Xem commit đã nghiệm thu trên GitHub](https://github.com/Kiennn0212/PayRecon/commit/ddcb202764ee487dd806b13de81f811c89fab799)

## Giai đoạn 1

**Xác định phạm vi MVP**

- **Đầu vào** — Hai tài liệu 8 tuần và 16 tuần, kết quả TASK-000 và câu hỏi tại DEC-001.
- **Công việc và đầu ra** — Phân tích nghiệp vụ đối soát của doanh nghiệp Việt Nam, mô tả người sử dụng, quy trình hiện tại, vấn đề cần giải quyết và ranh giới Demo MVP/Pilot.
- **Tiêu chí nghiệm thu dự kiến** — PO xác nhận người dùng, mục tiêu, đầu ra thuộc MVP và những việc để sau. Phạm vi được chọn có căn cứ tại DEC-001.
- **Bằng chứng nghiệm thu** — Chờ bản phạm vi và xác nhận của PO.

## Giai đoạn 2

**Đặc tả nghiệp vụ**

- **Đầu vào** — Phạm vi đã duyệt và các câu hỏi nghiệp vụ DEC-002 đến DEC-007.
- **Công việc và đầu ra** — Đặc tả Business Rules và tình huống nghiệm thu cho khóa ghép, gross/net, phí, thời điểm, trùng giao dịch và KPI.
- **Tiêu chí nghiệm thu dự kiến** — Mỗi quy tắc dùng để triển khai dẫn đến quyết định của PO, có ví dụ đầu vào, kết quả mong đợi và cách nhận biết ngoại lệ.
- **Bằng chứng nghiệm thu** — Chờ bộ quy tắc, tình huống đã rà soát và xác nhận của PO.

## Giai đoạn 3

**Đặc tả dữ liệu**

- **Đầu vào** — Phạm vi, Business Rules đã duyệt và mô tả các nguồn dữ liệu trong phạm vi.
- **Công việc và đầu ra** — Lập từ điển dữ liệu và đặc tả đầu vào. Ghi cấu trúc CSV/Excel theo nguồn, mã giao dịch dạng chuỗi, ngữ nghĩa số tiền và phí, mốc thời gian, múi giờ và cách truy về bản ghi gốc.
- **Tiêu chí nghiệm thu dự kiến** — BA đối chiếu được ý nghĩa từng trường giữa hai nguồn. Quy tắc kiểm tra, chuẩn hóa, biểu diễn VND chính xác và xử lý thời gian được kiểm chứng bằng ví dụ giả lập theo quy tắc đã duyệt.
- **Bằng chứng nghiệm thu** — Chờ đặc tả dữ liệu, ví dụ và xác nhận của PO.

## Giai đoạn 4

**Thiết kế giải pháp**

- **Đầu vào** — Yêu cầu nghiệp vụ, dữ liệu và tiêu chí nghiệm thu đã duyệt.
- **Công việc và đầu ra** — Thiết kế hệ thống, luồng dữ liệu và giao diện tiếng Việt cho việc nhập dữ liệu, xem kết quả và rà soát ngoại lệ. Trình phương án cấu trúc và công nghệ tại DEC-008, DEC-009.
- **Tiêu chí nghiệm thu dự kiến** — Mỗi lựa chọn có căn cứ, phạm vi áp dụng và quyết định của PO. Các luồng giao diện truy được về tình huống nghiệp vụ.
- **Bằng chứng nghiệm thu** — Chờ thiết kế, bản phác thảo giao diện và quyết định của PO.

## Giai đoạn 5

**Xây dựng MVP**

- **Đầu vào** — Thiết kế, phạm vi chức năng, công nghệ và các task đã duyệt.
- **Công việc và đầu ra** — Thiết lập môi trường kỹ thuật (Technical Setup), phát triển bộ máy đối soát (Reconciliation Engine), dashboard và báo cáo (Reporting) theo phạm vi đã chốt.
- **Tiêu chí nghiệm thu dự kiến** — Có thể dựng lại môi trường theo hướng dẫn. Mỗi quy tắc đã triển khai có ca kiểm thử. Chỉ số trên dashboard và báo cáo khớp kết quả đối soát trên cùng đầu vào và cách tính đã duyệt.
- **Bằng chứng nghiệm thu** — Chờ kết quả thiết lập, kiểm thử chức năng và xác nhận của PO.

## Giai đoạn 6

**Kiểm thử tích hợp**

- **Đầu vào** — Các chức năng đã xây dựng, bộ tình huống được duyệt và dữ liệu kiểm thử giả lập.
- **Công việc và đầu ra** — Chạy luồng nhập → đối soát → dashboard → báo cáo, ghi kết quả thực tế và danh sách lỗi.
- **Tiêu chí nghiệm thu dự kiến** — Đối chiếu được từng kết quả với bản ghi đầu vào và quy tắc áp dụng. Sai lệch giữa kết quả thực tế và kỳ vọng được ghi rõ để xử lý trước UAT.
- **Bằng chứng nghiệm thu** — Chờ báo cáo kiểm thử tích hợp và kết quả xử lý lỗi.

## Giai đoạn 7

**UAT nghiệp vụ**

- **Đầu vào** — Bản đã kiểm thử tích hợp, kịch bản nghiệp vụ, Acceptance Criteria và lỗi còn mở.
- **Công việc và đầu ra** — BA/PO thực hiện UAT, ghi kết quả từng tình huống, vấn đề còn tồn tại và yêu cầu làm lại nếu có.
- **Tiêu chí nghiệm thu dự kiến** — Mỗi tình huống có kết quả thực tế, kết quả mong đợi và đánh giá của BA/PO. PO quyết định nghiệm thu hoặc yêu cầu làm lại.
- **Bằng chứng nghiệm thu** — Chờ biên bản UAT và quyết định của PO.

## Giai đoạn 8

**Hoàn tất MVP**

- **Đầu vào** — Kết quả UAT, danh sách tồn đọng, phạm vi bàn giao và quyết định của PO về triển khai.
- **Công việc và đầu ra** — Chuẩn bị bàn giao, triển khai (Deployment) khi được PO cho phép, hoàn thiện tài liệu sử dụng và vận hành (Documentation), chuẩn bị Portfolio với dữ liệu giả lập và kết quả đã kiểm chứng.
- **Tiêu chí nghiệm thu dự kiến** — PO xác nhận kết quả triển khai trong phạm vi cho phép, tài liệu bàn giao, bằng chứng dùng cho Portfolio và cách xử lý tồn đọng.
- **Bằng chứng nghiệm thu** — Chờ hồ sơ bàn giao và quyết định kết thúc MVP của PO.

Thay đổi về cách chia giai đoạn, phạm vi hoặc tiêu chí được theo dõi trong [Nhật ký thay đổi](change_log.md).
