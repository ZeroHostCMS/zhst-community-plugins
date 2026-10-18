# Ghi chú dựng video từ bộ ảnh Sổ HKD

Đây là tài liệu đào tạo bằng **dữ liệu giả lập**, không phải hồ sơ thuế của một hộ đang hoạt động. Các tỷ lệ, mức thuế, căn cứ tính thuế và phần chi phí được trừ trong ví dụ chỉ phục vụ thao tác. Người sử dụng phải xác định chúng từ hồ sơ và quy định áp dụng cho mình; không sao chép các tỷ lệ trong video vào sổ thật.

## Cách dựng dễ hiểu cho người lần đầu sử dụng

1. Đọc lời thoại trong `voiceover-vi.md` hoặc lấy cột lời đọc của `shot-list.csv`. Giữ đúng mã ảnh ở đầu mỗi đoạn để không ghép nhầm màn hình.
2. Dùng ảnh gốc trong `images/`, không dùng ảnh thu nhỏ của trang xem trước. Ảnh không bị chèn mũi tên, che trường hoặc sửa số liệu; có thể thêm điểm nhấn ở phần mềm dựng phim.
3. Mỗi cảnh nên đi theo nhịp **đang ở đâu → cần làm gì → nhập gì → vì sao → kiểm tra kết quả nào**. Không đọc hết biểu mẫu một cách liên tục khi người xem chưa tìm được vị trí cần thao tác.
4. Khi nhắc một nút hoặc trường, phóng vùng đó lên rồi giữ vài giây. Với bảng rộng, giải thích trước rằng cần cuộn ngang; không cắt ảnh đến mức người xem tưởng các cột khác không tồn tại.
5. Tách rõ ảnh biểu mẫu **trước khi bấm ghi** với ảnh báo cáo **sau khi ghi thành công**. Một ảnh đã điền đủ thông tin không chứng minh chứng từ đã được lưu.
6. Trước thiết lập hồ sơ bất biến, ghi sổ hoặc hủy chứng từ, dừng ngắn để người xem đọc phần kiểm tra. Không tăng tốc đoạn nhắc kiểm tra chứng từ gốc và kỳ ghi sổ.
7. Hộp thoại passkey, xác nhận và in của trình duyệt/hệ điều hành không nằm trong ảnh chụp nội dung trang. Không chèn một hộp thoại giả rồi giới thiệu là giao diện phần mềm. Nếu quay bổ sung trên máy thật, che thông tin cá nhân và không quay mã khôi phục, khóa hoặc QR đăng nhập.
8. Thu âm hoặc tạo giọng đọc trước, nghe lại rồi căn thời lượng mỗi ảnh theo âm thanh thật. Thời lượng gợi ý trong danh sách cảnh chỉ để lập kế hoạch, **không phải timecode đã đồng bộ** và không phải tệp phụ đề SRT hoàn chỉnh.
9. Giữ cách đọc số nhất quán: `3.000.000 đồng` đọc “ba triệu đồng”; `17%` đọc “mười bảy phần trăm”; `S2c-HKD` có thể đọc “sổ S hai c dành cho hộ kinh doanh”. Đọc rõ dấu trừ và phép chia ở đoạn bình quân gia quyền, thay vì chỉ đọc con số cuối.
10. Trước phát hành, đối chiếu lại bản ứng dụng đang triển khai. Bộ ảnh là một lần ghi quy trình cụ thể; nếu nhãn nút, mẫu sổ hoặc quy định thay đổi, quay lại cảnh tương ứng thay vì sửa lời đọc để khẳng định ảnh cũ vẫn đúng.

## Chia thành các video ngắn

- **Bắt đầu:** vào workspace, tạo tài khoản/passkey, tìm Sổ HKD và kiểm tra hồ sơ năm trước khi xác nhận.
- **Phương pháp thu nhập:** đầu kỳ kho/quỹ, phát sinh, doanh thu–thu tiền, chi phí–chi trả, bình quân kho, xem các sổ S2b/c/d/e và S3a.
- **Sửa sai và xử lý sự cố:** hủy có lý do, ghi chứng từ thay thế, số dư không đủ, thiếu đầu kỳ, kết quả lệnh chưa rõ và đối soát lệnh gốc.
- **Đọc và lưu sổ:** ảnh chụp dữ liệu, phân trang, xuất toàn bộ CSV, bản in, dùng điện thoại.
- **Hai phương pháp còn lại:** ví dụ riêng về S2a theo doanh thu và S1a cho hồ sơ đã được người vận hành xác định thuộc phương pháp miễn thuế.

Không giới thiệu ba hồ sơ minh họa là ba năm liên tiếp hoặc ba lần đổi chế độ trong một hộ. Chúng được ghi trên **ba cài đặt demo riêng**, cùng năm 2026, để người mới không hiểu nhầm rằng có thể mở năm khác nhằm sửa phương pháp đã chọn sai.

Các cổng 4323–4326 trong metadata là nguồn ghi hình đã tắt, không phải liên kết thực hành đang phục vụ. Dev bàn giao tại **http://localhost:4337** là cài đặt sạch, không chứa các chứng từ demo. Khi hướng dẫn người học tự làm, dùng các khung 001–009 chung, rồi **chọn đúng một nhánh trước khi xác nhận hồ sơ năm**: thu nhập 010–046; doanh thu 047–050; S1a 051–053. Không yêu cầu người học tạo cả ba hồ sơ cùng năm trên một cài đặt.

## Kích thước và nguồn ảnh

- Phần lớn ảnh desktop rộng 1.920 pixel; chiều cao được tăng ở biểu mẫu/sổ dài để giữ được nội dung. Khi dựng 16:9, phóng vùng đang giải thích và lia dọc, không ép cả sổ dài vào một khung làm chữ không đọc được. Kích thước pixel thực có trong `capture-manifest.json`.
- Khung 046 là mô phỏng điện thoại rộng 390 CSS pixel, ảnh 780 × 1.688 pixel ở mật độ 2×. Bảng đã cuộn sang phải để chứng minh các cột còn lại nằm trong vùng cuộn, không phải mất cột hoặc tràn toàn trang. Đây không phải kiểm tra trên điện thoại vật lý.
- Khung 014 được tái hiện trên một cài đặt synthetic riêng chỉ có đầu kỳ và phiếu xuất, để chụp rõ giá trị trước phiếu nhập. Không tua ngược hay sửa lịch sử của demo chính. Khung 016 được căn lại sau các nghiệp vụ không liên quan kho; lượng, giá trị và các dòng kho tháng một không đổi.
- Khung 045 là nội dung in thật của ứng dụng ở chế độ print-media; lời gọi hộp in hệ điều hành được giữ tạm trong lúc chụp nội dung trang. Mẫu PDF đi kèm là bản xuất thực gồm hai trang. Không giới thiệu ảnh này như ảnh hộp thoại in của hệ điều hành.
- Các dòng FEB-002 đến FEB-030 được tạo bằng API đã xác thực để có dữ liệu phân trang; giao diện không có thao tác “nhập hàng loạt 29 dòng” được quay ở đây. Một chứng từ BH-REC-001 được ghi qua UI trong bài đối soát. Không cần có đủ 30 dòng mới xuất được sổ.


## Điều phải giữ nguyên trong lời đọc

- Sổ HKD là luồng riêng, không cần import bộ tài khoản TT133/TT99. Không tự lấy dữ liệu CRM, tự ghi tiền hoặc tự sinh chi phí từ phiếu xuất kho.
- Hồ sơ năm bất biến; đầu kỳ từng mặt hàng/quỹ phải khai rõ, kể cả bằng 0. Chuyển kỳ trong năm và mở năm mới là hai việc khác nhau; không có tự động chuyển số dư sang hồ sơ năm mới.
- Thuế suất/căn cứ/chi phí được trừ do người vận hành xác định. Có số trên báo cáo không đồng nghĩa cơ quan thuế đã chấp nhận, tờ khai đã nộp hoặc tiền thuế đã trả.
- Khi chưa biết lệnh đã được ghi hay chưa, giữ tab/phiên và nội dung gốc. Không xóa bộ nhớ trình duyệt, đổi tài khoản/tài nguyên hoặc ghi lại thành lệnh mới để “cho chắc”.
- CSV và bản in phục vụ đối chiếu/lưu sổ; chúng không thay bản sao lưu đầy đủ. Sao lưu/khôi phục cần người vận hành có thẩm quyền và bộ dữ liệu/khóa/mã ứng dụng tương ứng.

Nguồn nghiệp vụ và giới hạn tại lần ghi: [hướng dẫn accounting/HKD — bản nguồn cố định trên GitHub](https://github.com/ZeroHostCMS/zhst-community-plugins/blob/c99dc944188d3f0f608007b406bf11f9d1132208/plugins/erp-mini/docs/accounting.md#hkd-tt1522025). Liên kết này dùng được cả khi xem ZIP độc lập ngoài workspace.
