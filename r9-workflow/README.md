# R9 — Bản lưu quy trình và danh mục công việc

Đây là checkpoint công khai đã lọc thông tin, phục vụ việc tiếp tục các đợt giao việc Web và nhận kết quả về một đầu mối tích hợp.

## Đã lưu

- Danh mục 20 task ở mức khái quát.
- Mẫu giao input, trả kết quả và ghi quyết định tiếp nhận.
- Quy trình nhận từng gói, tái sử dụng bằng chứng, ghép và giao đợt tiếp theo.
- Prompt dùng chung và manifest hash của chính các tệp trong thư mục này.

## Trạng thái

20 task đã được chuẩn bị. Các gói kết quả của 20 task **chưa được rà trong checkpoint này**; không suy ra chúng chưa tồn tại ở nơi khác. Các số đo tiến độ chưa được xác minh để null.

Bản lưu này không chứa source bot, patch, ZIP code, dữ liệu tài khoản hoặc cấu hình triển khai. Nó không thay bản sao đầy đủ được giữ riêng, không phải candidate chạy được và không chứng minh nghiệm thu broker.

## Cách tiếp tục

1. Xem WORKFLOW.md và giữ input hiện hành trong kho riêng.
2. Giao một task có file ownership rõ cho mỗi phiên.
3. Nhận từng kết quả khi có, đối chiếu input và bằng chứng.
4. Ghép phần phù hợp vào candidate chung, QA phần bị ảnh hưởng.
5. Đóng phần đã được chấp nhận và chỉ giao những khoảng trống còn lại.

Nhánh lưu trữ không tự đồng bộ với môi trường chạy. Việc lưu checkpoint này không khởi chạy worker hoặc thay đổi ứng dụng.

