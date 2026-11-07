# Vòng nhận kết quả và giao việc tiếp

## Nhận theo dòng kết quả

Không cần đợi đủ 20 gói. Với mỗi gói, giữ bản gốc và hash, đọc báo cáo, baseline, file thay đổi, dependency, lệnh kiểm thực chạy và phần chưa chạy. Ghi quyết định tiếp nhận riêng; không sửa báo cáo gốc để biến thành PASS.

| Trạng thái worker | Cách xử lý |
|---|---|
| READY_FOR_INTEGRATION | Review patch và kiểm tương thích; chưa mặc nhiên được chấp nhận. |
| REFERENCE_RESULTS | Tái sử dụng test/fixture hoặc phát hiện sau khi đối chiếu current source. |
| REUSE_EXISTING | Đóng phần tương đương nếu bằng chứng còn hợp lệ. |
| NEEDS_INPUT | Bổ sung đúng dữ liệu thiếu; không lặp cùng prompt với cùng input. |

## Đối chiếu và tích hợp

Hash ZIP đổi chưa đủ để kết luận mọi kết quả cũ vô dụng. Đối chiếu file và dependency liên quan: phần không đổi có thể tái sử dụng; phần đổi cần rebase có mục tiêu. Không overlay hai sibling patch hoặc thay toàn bộ file dùng chung khi chỉ cần một sửa nhỏ.

Một người sở hữu mỗi vùng product source trong một đợt. Giữ coordinator và nhóm tích hợp hiện hành; các phiên Web đóng góp patch/test riêng. QA độc lập trên candidate kết hợp kiểm phần bị ảnh hưởng và đường đi giữa các thành phần. Dùng môi trường giả cho hệ thống ngoài; không giả module nội bộ để ép kết quả xanh.

Quyết định tiếp nhận dùng ACCEPTED, REUSED, NEEDS_INPUT, REBASE_NEEDED, QA_FAILED hoặc SUPERSEDED. Tái sử dụng cấu trúc quản lý công việc hiện có; mẫu INTAKE.json chỉ là record nhỏ, không cần dịch vụ quản lý mới.

## Giao đợt tiếp theo

- Task được chấp nhận thì đóng.
- Task thiếu input nhận revision mới cùng ID; giữ lịch sử đã thử.
- Task bị QA phát hiện lỗi nhận đúng repro và acceptance criterion.
- Task bị source mới thay thế được đánh dấu SUPERSEDED; không sửa lại bản cũ.
- Khi nhiều gói cùng thiếu dữ liệu, xuất một snapshot/contracts dùng chung rồi cấp delta cần thiết.
- Khi hàng chờ tích hợp tăng, ưu tiên giải quyết hàng chờ trước khi mở thêm task.
- Khi đầu vào và khả năng nhận kết quả đủ, bổ sung các việc độc lập tiếp theo.
- Khi hết khoảng trống offline hữu ích, chuyển sang đợt nghiệm thu tương ứng; không tạo test hoặc nghiên cứu chỉ để duy trì số phiên.

## Đo tiến độ

Tách ba loại bằng chứng: phần code/wiring đã xong; luồng đã kiểm offline trên candidate chung; luồng đã được xác minh ở môi trường chạy tương ứng. Không cộng tổng số test từ nhiều ZIP thành một tỷ lệ hoàn thiện.

Một kết quả giúp giảm việc khi đóng được một gap, cung cấp test hữu ích được chấp nhận hoặc loại bỏ một điều chưa biết. Số gói trả về không tự thể hiện số ngày tiết kiệm.

Các kiểm tra quyền thực thi, một writer và cách xử lý kết quả chưa rõ phải giữ theo contract hiện hành. Kết quả mô phỏng không tự cấp quyền chạy thật.

