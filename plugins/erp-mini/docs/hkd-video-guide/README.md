# Sổ HKD — bộ ảnh và lời đọc tiếng Việt cho người mới

**Đây là bộ ghi hình minh họa, không phải dịch vụ dev được cung cấp qua GitHub.** Địa chỉ `http://localhost:4337` trong bộ ghi thuộc máy ghi hình tại thời điểm chụp, không tự chạy trên máy người xem. Để thực hành, làm theo [hướng dẫn cài đặt plugin và paired host](../../README.md#start-from-two-standalone-clones), dùng URL được host in ra và tự đăng ký quản trị viên/passkey. Giữ nhất quán hostname khi dùng passkey; không chia sẻ tài khoản demo.

Bộ ghi ngày **17/10/2026** gồm **54 ảnh PNG gốc theo thứ tự**, hướng dẫn từng trường, lời đọc riêng cho từng ảnh và các tệp xuất thật. Đây là dữ liệu đào tạo giả lập; không phải kết luận phương pháp hay mức thuế áp dụng cho hộ của bạn. Không cần nhập bộ tài khoản TT133/TT99 để dùng Sổ HKD.

## 1. Mở đúng tệp

| Cần làm gì | Tệp |
| --- | --- |
| Xem nhanh tất cả cảnh | [Bảng ảnh thu nhỏ](contact-sheet.png) — chỉ để chọn cảnh, không dùng làm nguồn video |
| Tạo site, tài khoản/passkey, vào workspace và chọn hồ sơ | [Chương 01, cảnh 001–011](chapters/01-bat-dau-va-thiet-lap.md) |
| Ghi đầu kỳ, kho, tiền, doanh thu, chi phí, thuế và sửa sai | [Chương 02, cảnh 012–036](chapters/02-thu-nhap-va-sua-sai.md) |
| Xử lý lỗi, đối soát lệnh, xuất sổ, điện thoại và hai phương pháp khác | [Chương 03, cảnh 037–054 và hỏi nhanh](chapters/03-loi-xuat-so-va-phuong-phap-khac.md) |
| Thu âm/tạo giọng đọc theo đúng ảnh | [Lời đọc 54 cảnh](voiceover-vi.md) |
| Nhập kế hoạch cảnh vào bảng tính hoặc phần mềm dựng | [Danh sách cảnh CSV UTF-8](shot-list.csv): mã ảnh, thao tác, kiểm tra, lời đọc, gợi ý dựng, giây ước lượng |
| Quy tắc dựng, ảnh dài, giới hạn hộp thoại hệ điều hành | [Ghi chú dựng video](recording-notes.md) |
| Kiểm tra kết quả đã thực sự chạy | [Bằng chứng và giới hạn](verification.md), [dữ liệu kiểm tra JSON](verification.json) |
| Tra kích thước, nguồn chụp và checksum từng ảnh | [Manifest ảnh](capture-manifest.json) |
| Đọc tệp xuất đủ 30 dòng | [CSV S2b tháng 2](exports/S2b-HKD-2026-2.csv), [PDF hai trang](exports/S2b-HKD-2026-2.pdf) |

Ảnh gốc nằm trong `images/`, tên bắt đầu `001-` đến `054-`. Trong mỗi chương, một cảnh có **mục tiêu → thao tác → kiểm tra → lời đọc**. Đừng bỏ phần kiểm tra trước thiết lập bất biến, ghi sổ và hủy chứng từ.

## 2. Người học chọn một nhánh, không làm cả ba trên một hồ sơ

Thực hiện **001–009** chung để đến Sổ HKD. Sau đó **dừng và xác định phương pháp thực tế trước khi tạo hồ sơ năm**:

| Nhánh phù hợp đã được xác định | Đi tiếp từ cảnh | Nội dung |
| --- | --- | --- |
| TNCN trên thu nhập tính thuế | **010–046** | Hồ sơ tháng; S2b, S2c, S2d, S2e; S3a nếu có thuế khác; sửa sai và xuất sổ |
| TNCN theo tỷ lệ trên doanh thu | **047–050**, bỏ qua thiết lập thu nhập 010 | Hồ sơ quý; doanh thu và các căn cứ/tỷ lệ; S2a |
| Không thuộc diện nộp GTGT, TNCN theo căn cứ thực tế | **051–053**, không tạo các hồ sơ ở hai nhánh trên trước | Hồ sơ năm; S1a chỉ thể hiện doanh thu, không phải chứng nhận được miễn |

Các cảnh 047 và 051 là **hai cài đặt demo độc lập**, cùng năm 2026; không phải nút đổi phương pháp của hồ sơ đã xác nhận. Một hồ sơ năm bất biến không thể sửa bằng cách tạo thêm hồ sơ cùng năm hoặc chọn năm khác cho giao dịch cũ. Nếu đã chọn sai, dừng ghi và nhờ người vận hành xử lý đúng dữ liệu; không xóa hoặc đặt lại hệ thống đang dùng.

Cảnh 037–046 minh họa xử lý sự cố/xuất sổ trên dữ liệu thu nhập. Nguyên tắc giữ lệnh gốc và xuất đủ ảnh chụp cũng áp dụng khi dùng mẫu sổ phù hợp nhánh khác; không nhập các phiếu kho/tiền/chi phí của nhánh thu nhập vào phương pháp không có chúng. Không cần đủ 30 dòng mới xuất được sổ.

## 3. Cách dùng để làm video có giọng đọc

1. Chọn phạm vi video theo bảng trên hoặc chia nhỏ theo `recording-notes.md`.
2. Nhập PNG gốc đúng mã cảnh. Dùng `contact-sheet.png` để chọn nhanh, không thay cho ảnh gốc.
3. Lấy đoạn cùng mã trong `voiceover-vi.md`; bảng thao tác chi tiết nằm trong chương tương ứng. Lời đọc giải thích cả **vì sao** và **đối chiếu số nào**, không chỉ đọc nhãn nút.
4. Thu âm hoặc tạo giọng đọc, nghe và chỉnh cách đọc số, tên sổ, ngày tháng. Tổng toàn bộ 54 đoạn khoảng **43 phút theo tốc độ ước lượng**; không có audio đã thu hay video đã dựng.
5. Căn ảnh theo âm thanh thực. Cột thời lượng là ước lượng từ 150 đơn vị tách bằng khoảng trắng/phút cộng hai giây chuyển cảnh, **không phải timecode/SRT đã đồng bộ**.
6. Với ảnh báo cáo dài, lia/phóng vùng đang nói trong khung 16:9; không ép cả trang khiến chữ nhỏ. Ảnh điện thoại 046 là 780 × 1.688 pixel, mô phỏng viewport 390 CSS pixel ở mật độ 2×.
7. Không chèn hộp passkey/xác nhận/in giả như giao diện thật. Bộ ảnh không chụp hộp thoại của hệ điều hành. Nếu quay bổ sung, che thông tin riêng và không ghi lại khóa hoặc mã khôi phục.

## 4. Các số phải đối chiếu trong ví dụ

Tất cả tiền là **đồng nguyên**. Tỷ lệ 17%, 1%, 0,5% và mức thuế tuyệt đối chỉ là số minh họa, không phải khuyến nghị cho người xem.

| Giai đoạn | Kết quả trong demo |
| --- | --- |
| Kho trước phiếu nhập tháng 1, cảnh 014 | Đầu 10 kg / 1.000.000; xuất 5 kg trị giá 500.000; còn 5 kg / 500.000 |
| Kho sau nhập thêm 10 kg / 2.000.000, cảnh 016/029/030 | Bình quân định kỳ `(1.000.000 + 2.000.000) / (10 + 10) = 150.000/kg`; xuất 750.000; tồn 15 kg / 2.250.000 |
| S2b tháng 1 | Doanh thu 3.000.000; GTGT minh họa 30.000 |
| S2c trước sửa DV-001 | Được trừ 1.150.000; thu nhập 1.850.000; TNCN minh họa 314.500 |
| S2c sau hủy DV-001 và ghi DV-001-DC | Được trừ 1.200.000; thu nhập 1.800.000; TNCN minh họa 306.000 |
| Tiền tháng 1 | Tiền mặt `2.000.000 + 3.000.000 − 500.000 − 2.000.000 = 2.500.000`; ngân hàng `0 + 1.000.000 = 1.000.000` |
| S3a tháng 1 | Nghĩa vụ minh họa `100 × 1.000 = 100.000`, không phải xác nhận đã nộp tiền |
| S2b tháng 2, CSV/PDF mẫu | 30 dòng, trang màn hình 25 + 5; doanh thu 300.000; GTGT 3.000; xuất đủ 30 dòng từ trang 2 |
| S2a quý 1 trên demo riêng | Doanh thu 1.000.000; GTGT 10.000; TNCN 5.000 |
| S1a cả năm trên demo riêng | Doanh thu 500.000; không trình bày GTGT/TNCN thành số 0 để suy ra được miễn |

Bình quân kho là **bình quân cả kỳ**, không phải bình quân di động. Xuất kho không tự tạo chi phí S2c. Ghi doanh thu, thu tiền, ghi chi phí và chi tiền là các nghiệp vụ riêng. Sửa phần được trừ không có nghĩa chi tiền lần nữa. Khi kết quả gửi lệnh chưa rõ, không ghi thay bằng lệnh mới.

## 5. Tự chuẩn bị môi trường thực hành

Làm theo [hướng dẫn cài đặt hai repository](../../README.md#start-from-two-standalone-clones) và hướng dẫn local setup của paired theme được liên kết ở đó. Build plugin trước host, dùng dependency và lockfile riêng, cùng dữ liệu synthetic tách biệt khỏi hệ thống đang vận hành. Ghi lại URL thực tế host in ra; không giả định cổng trong ảnh còn phục vụ hoặc có dữ liệu demo sẵn.

Các cổng 4323–4326 là nguồn ghi của các fixture riêng; 4337 là cài đặt sạch được bàn giao trên máy ghi hình ngày 17/10/2026. Đây là bằng chứng lịch sử, không phải hướng dẫn tìm một thư mục private có sẵn trên máy người đọc. Không có runtime, `node_modules`, tài khoản, khóa hoặc cơ sở dữ liệu trong thư mục hướng dẫn này.

Chỉ dùng lệnh status/logs/stop từ đúng thư mục host do bạn vận hành. Không dừng ứng dụng khác để giải phóng cổng, không xóa dữ liệu hoặc tạo lại khóa chỉ để làm giống ảnh. Nếu giao diện khác ảnh, đối chiếu phiên bản đang chạy trước khi ghi dữ liệu thật.


## 6. Phạm vi và nguồn

Đã chạy luồng trình duyệt thực với dữ liệu giả lập, đối chiếu báo cáo và tệp xuất. **Không tái hiện được lỗi ứng dụng trong các đường đã chạy; không sửa mã nguồn ứng dụng trong lần ghi này.** Lỗi allow-list lúc chuẩn bị fixture được xử lý bằng dependency vật lý riêng cho từng host, không nới bảo vệ Vite. Chi tiết và lưu ý công cụ nằm trong `verification.md`.

Nguồn hợp đồng HKD cố định theo bản ghi: [accounting.md — HKD](https://github.com/ZeroHostCMS/zhst-community-plugins/blob/c99dc944188d3f0f608007b406bf11f9d1132208/plugins/erp-mini/docs/accounting.md#hkd-tt1522025). Các thay đổi nền đã được merge qua [plugin PR #13](https://github.com/ZeroHostCMS/zhst-community-plugins/pull/13) và [theme PR #8](https://github.com/ZeroHostCMS/zhst-community-themes/pull/8). Trạng thái đó không chứng minh CI của PR tài liệu này hoặc cho phép triển khai production.

CSV/PDF không thay bản sao lưu đầy đủ. Không có xác nhận pháp lý, nộp tờ khai, thanh toán nhà cung cấp thật, kiểm thử thiết bị vật lý hoặc triển khai production trong bộ ghi này. Đối chiếu lại ứng dụng/quy định hiện hành trước khi phát hành video cho người dùng thật.
