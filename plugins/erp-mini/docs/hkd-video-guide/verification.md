# Bằng chứng chạy thực và giới hạn — 17/10/2026

## Phạm vi đã chạy

- Dev Astro/EmDash với plugin ERP mini đã build, trên các bản sao synthetic độc lập. Đăng ký tài khoản/passkey bằng trình duyệt tự động và virtual authenticator cho các bản ghi demo; dev bàn giao 4337 không được nhận chủ bằng tài khoản tự động.
- 54 ảnh màn hình ứng dụng thực; đã giải mã toàn bộ PNG bằng Chromium và khớp kích thước thực với manifest, không chỉ kiểm phần mở rộng tệp. Các ảnh gốc giữ nội dung trang; bảng ảnh thu nhỏ là bản ghép có ghi rõ chỉ để chọn cảnh.
- Hướng dẫn từng bước và 54 lời đọc tương ứng, tổng 6.056 đơn vị tách bằng khoảng trắng. Khoảng 43 phút là dự toán đọc, không phải độ dài âm thanh đã ghi.
- Không có thay đổi mã nguồn ứng dụng trong nhiệm vụ này. Không chạy lại full suite hoặc CI để tuyên bố xanh; bằng chứng dưới đây là các smoke scenario thực đã quan sát.

## Kết quả nghiệp vụ

| Đường chạy | Quan sát thực |
| --- | --- |
| Thu nhập/tháng 2026 | Thiết lập bất biến, đầu kỳ kho/quỹ gồm ngân hàng 0, thu/chi, doanh thu, chi phí, thuế khác, xem S2b/c/d/e và S3a |
| Bình quân kho trước/sau phiếu nhập | Trước nhập: xuất 500.000, tồn 5 kg/500.000. Sau nhận đủ hàng trong kỳ: xuất định giá lại 750.000, tồn 15 kg/2.250.000. Khung trước nhập tái hiện trên fixture riêng, không rewinding lịch sử chính |
| Hủy và thay DV-001 | Bản gốc còn trong lịch sử ở trạng thái đã hủy. Phần được trừ từ 400.000 thành 450.000; S2c tổng được trừ 1.200.000, thu nhập 1.800.000, TNCN minh họa 306.000. Tiền/kho/GTGT không bị ghi lại |
| Quỹ tiền sau sửa | Tiền mặt 2.500.000; Ngân hàng DEMO 1.000.000; S3a nghĩa vụ 100.000. Đối chiếu bằng báo cáo thực/API cùng installation |
| Chi vượt quỹ | CHI-LOI-001 bị từ chối `HKD_NEGATIVE_MONEY`; UI hiện thông điệp tiếng Anh giải thích số dư theo thời gian bị âm. Không có chứng từ này trong lịch sử cuối |
| Quỹ ngân hàng chưa mở đầu | THU-LOI-001 bị từ chối `HKD_OPENING_REQUIRED`; không ghi vào lịch sử. Không coi lỗi này là tín hiệu tạo doanh thu hoặc bỏ kiểm tra đầu kỳ |
| Mất phản hồi sau commit thật | Chặn phản hồi bằng CDP sau khi server đã ghi BH-REC-001. UI giữ nội dung và khóa ghi mới; tải lại cùng phiên vẫn giữ chính xác lệnh. Bấm đối soát trả đúng biên nhận gốc, sequence 16, chỉ một bản ghi và registry được xóa sau xác nhận |
| Phân trang cố định | S2b tháng 2 có 30 dòng; trang 1 gồm 25, trang 2 gồm 5; cùng ảnh chụp đến sequence 45. Tổng cả kỳ 300.000 doanh thu, GTGT 3.000 |
| CSV thực từ trang 2 | Tải file qua nút UI; CSV có đủ 30 số chứng từ phân biệt, đến FEB-030, tổng 300.000/3.000 và danh tính/phần ký. Không chỉ xuất 5 dòng đang xem |
| Nội dung in/PDF thực | Print document chứa đủ 30 dòng, tổng và chữ ký. PDF đính kèm có hai trang; toàn bộ mã chứng từ và phần ký được kiểm tra qua nội dung, trang đầu được render để kiểm bố cục |
| Điện thoại mô phỏng | Viewport 390 CSS px; chiều rộng document 390, không tràn toàn trang. Bảng viewport 308, nội dung 1.353, cuộn phải 1.045; ảnh gốc 780 × 1.688 ở 2× |
| Doanh thu/quý, cài đặt riêng | S2a quý 1: doanh thu 1.000.000, GTGT 10.000, TNCN 5.000 theo các căn cứ/tỷ lệ minh họa đã nhập |
| S1a/năm, cài đặt riêng | Doanh thu 500.000; bảng/tổng hợp không trình bày GTGT/TNCN thành 0 để giả kết luận miễn |
| Dev sạch 4337 | Setup-status `needsSetup: true`, chưa nhận chủ. Cả sáu action HKD trả HTTP 401 / `AUTH_REQUIRED` với khách chưa đăng nhập; `.env` hiện tại có quyền 0600 |

Dữ liệu kiểm tra cấu trúc nằm trong [verification.json](verification.json). Các lỗi nghiệp vụ ở hai dòng từ chối là **kết quả mong đợi**, không phải bug được che hoặc bỏ qua. Không có pageerror JavaScript trong lượt đối chiếu cuối demo thu nhập.

## Vấn đề phát sinh trong môi trường/công cụ

1. **Fixture Vite ban đầu:** dùng symlink node_modules chung làm host riêng không hydrate vì allow-list 403. Đã bỏ symlink do nhiệm vụ tạo và cài dependency vật lý riêng bằng npm cho từng host. Không sửa logic ứng dụng hoặc nới allow-list để che lỗi môi trường.
2. **Cổng dev:** 4322 thuộc một ứng dụng khác nên bản sạch được cấu hình lại và chạy trên 4337, không dừng ứng dụng đó. Các daemon ghi hình 4323–4326 đã dừng qua CLI đúng thư mục của chúng. Instance 4321, dữ liệu và khóa gốc không bị thay đổi.
3. **An toàn công cụ đọc:** một lần đọc giới hạn dòng của `.env` đã trả thừa dòng chứa khóa tạo riêng cho demo sạch. Sự cố đã được báo cho công cụ. Khi đó bản sạch chưa có quản trị viên/dữ liệu thật; daemon được dừng, khóa đó được thay bằng khóa mới trước bàn giao, không in khóa mới ra kết quả và đặt quyền 0600. Bộ ảnh/tài liệu/ZIP không chứa khóa hoặc `.env`; không phải sự cố với key của instance 4321.
4. **QA ảnh:** một lần tạo browser context để làm bảng ảnh bị timeout và mất biến runtime của công cụ; đã báo công cụ và làm lại riêng bước giải mã/ghép ảnh bằng tab do nhiệm vụ sở hữu. Đây không phải lỗi ứng dụng; các ảnh và bằng chứng nghiệp vụ đã lưu không bị thay thế bằng mock.

## Giới hạn không được suy rộng

- Các cài đặt cùng năm 2026 là riêng biệt; không chứng minh đổi phương pháp của hồ sơ đã khóa. Dev sạch không tự có sẵn demo.
- Các dòng FEB-002…FEB-030 được tạo bằng API đã xác thực để có dữ liệu phân trang; không có UI nhập hàng loạt được quay. BH-REC-001 đi qua UI và tình huống mất phản hồi thật.
- Hộp thoại passkey, xác nhận và in native của hệ điều hành không nằm trong PNG trang. Khung 045 là print-media content thật; lời gọi in được giữ tạm để chụp nội dung, sau đó phục hồi. Không phải ảnh hộp thoại in.
- Mobile là mô phỏng trong Chromium, không phải iPhone/Android vật lý. Chưa kiểm tra screen reader hoặc mọi trình duyệt.
- Không có audio/video/SRT đã đồng bộ. Không có dữ liệu khách hàng, nhà cung cấp thanh toán/hóa đơn thật hoặc kiểm chứng production, capacity, CI hiện thời hay chứng nhận tuân thủ thuế.
- CSV và PDF chỉ là tệp đối chiếu/lưu sổ, không thay backup đầy đủ hồ sơ, sự kiện, biên nhận, CMS/media/key/code. Không triển khai hoặc kích hoạt production trong nhiệm vụ này.
