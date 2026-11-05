# BÁO CÁO KIỂM THỬ SẢN PHẨM

## 1. Thông tin chung

| Thông tin | Chi tiết |
|---|---|
| **Tên dự án** | My CV – Đào Thiện Anh |
| **Phiên bản** | v1.0 |
| **Ngày kiểm thử** | 05/11/2026 |
| **Người thực hiện** | AI hỗ trợ rà soát tĩnh và kiểm tra giao diện trên trình duyệt |
| **Người đánh giá/nghiệm thu** | Chưa xác nhận |
| **Phạm vi** | Rà soát `index.html`, `assets/css/styles.css`, `README.md`; kiểm tra giao diện trên trình duyệt tại ba viewport |
| **Phương pháp** | Kiểm tra tĩnh và chụp ảnh trang chạy trong trình duyệt ở viewport 390×844, 768×1024 và 1440×1000 |
| **Ngoài phạm vi** | Chưa kiểm thử trên thiết bị vật lý hoặc nhiều trình duyệt; chưa đo hiệu năng, kiểm thử triển khai hay quét bảo mật tự động |

> **Lưu ý:** Ảnh responsive là ảnh chụp trình duyệt khi đặt kích thước viewport tương ứng, không phải ảnh chụp từ điện thoại/máy tính bảng vật lý. Các mục chưa chạy trên thiết bị thật hoặc môi trường triển khai không được xem là đã kiểm thử thực tế.

## 2. Bảng tổng quan trạng thái

| # | Nhóm tiêu chí | Trạng thái | Tóm tắt |
|---:|---|---|---|
| 1 | Tính đúng đắn và mức độ đáp ứng yêu cầu chức năng | Cần cải thiện | Các khu vực nội dung và điều hướng chính đã có; biểu mẫu chưa gửi dữ liệu, liên kết chi tiết dự án chưa hoàn chỉnh. |
| 2 | Giao diện, trải nghiệm người dùng và khả năng tương thích | Cần cải thiện | Đã kiểm tra bố cục responsive trên ba viewport và lưu ảnh; chưa xác nhận trên thiết bị vật lý/nhiều trình duyệt, nhãn biểu mẫu chưa liên kết đúng với trường nhập. |
| 3 | Khả năng vận hành, xử lý lỗi và hiệu năng cơ bản | Cần cải thiện | Có hướng dẫn chạy website tĩnh; chưa thực hiện chạy thử, đo hiệu năng hoặc kiểm tra xử lý lỗi thực tế. |
| 4 | Bảo mật, quản lý cấu hình và dữ liệu | Cần cải thiện | Không thấy luồng lưu trữ/gửi dữ liệu phía máy chủ trong phạm vi rà soát; chưa kiểm tra cấu hình bảo mật ở môi trường triển khai. |
| 5 | Chất lượng mã nguồn, cấu trúc repository và tài liệu bàn giao | Cần cải thiện | Cấu trúc đơn giản và README có hướng dẫn; còn vấn đề về ngữ nghĩa HTML, CSS nội tuyến và liên kết placeholder. |
| 6 | Khả năng triển khai, kiểm thử và cung cấp minh chứng | Cần cải thiện | Đã có ảnh responsive; README mô tả cách chạy cục bộ và Docker. Chưa có kết quả kiểm thử chức năng, bộ kiểm thử tự động hoặc minh chứng nghiệm thu triển khai. |

## 3. Chi tiết kiểm tra

### 3.1. Tính đúng đắn và mức độ đáp ứng yêu cầu chức năng

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
|---|---|---|
| Nội dung giới thiệu, kỹ năng, dự án và liên hệ hiện diện | Đạt | Các khu vực `about`, `skills`, `projects`, `contact` có trong `index.html`. |
| Điều hướng nội bộ đến các mục chính | Đạt | Các liên kết điều hướng sử dụng fragment tương ứng với ID của từng khu vực. |
| Hiển thị ảnh đại diện và ảnh dự án | Cần cải thiện | Đường dẫn ảnh được khai báo trong HTML; chưa xác minh tải thành công trên trình duyệt và máy chủ triển khai. |
| Liên kết email và GitHub | Đạt | Có liên kết `mailto:` và URL GitHub trong phần liên hệ. Chưa kiểm tra thao tác mở ứng dụng email/trang ngoài thực tế. |
| Gửi thông tin từ biểu mẫu liên hệ | Chưa đạt | Các trường và nút gửi không nằm trong phần tử `<form>`; nút `type="submit"` vì vậy không gửi dữ liệu đến dịch vụ nào. README cũng nêu biểu mẫu chưa kết nối máy chủ hoặc dịch vụ email. |
| Liên kết xem chi tiết dự án | Chưa đạt | Các nút “Xem chi tiết” đang dùng `href="#"`, chưa dẫn đến trang hoặc tài nguyên dự án. |

### 3.2. Giao diện, trải nghiệm người dùng và khả năng tương thích

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
|---|---|---|
| Bố cục thích ứng theo kích thước màn hình | Đạt | Đã mở trang trong trình duyệt ở viewport mobile 390×844 (lưới dự án 1 cột), tablet 768×1024 (2 cột) và desktop 1440×1000 (3 cột). Ảnh minh chứng: [Mobile](./screenshots/responsive-mobile.png), [Tablet](./screenshots/responsive-tablet.png), [Desktop](./screenshots/responsive-desktop.png). |
| Điều hướng bằng bàn phím và trạng thái focus | Cần cải thiện | CSS có `:focus-visible`; tuy nhiên quy tắc nội tuyến `input:focus { outline: none !important; }` loại bỏ outline của trường nhập. Cần xác minh chỉ báo focus đủ rõ và nhất quán. |
| Nhãn trường nhập gắn với input | Chưa đạt | `label` khai báo `for="email"`/`for="name"` nhưng các `input` tương ứng không có `id`. |
| Ngữ nghĩa và khả năng truy cập của nội dung | Cần cải thiện | Trang có `lang="vi"`, cấu trúc tiêu đề và landmark chính; ảnh dự án dùng alt chung chung (“Ảnh minh họa”), chưa mô tả nội dung ảnh cụ thể. |
| Kiểm tra trên thiết bị vật lý và nhiều trình duyệt | Cần cải thiện | Đã có ảnh từ một phiên trình duyệt ở ba kích thước viewport; chưa kiểm tra trên điện thoại/máy tính bảng vật lý, Chrome/Firefox/Edge/Safari độc lập hoặc đo độ tương phản màu. |

### 3.3. Khả năng vận hành, xử lý lỗi và hiệu năng cơ bản

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
|---|---|---|
| Có hướng dẫn chạy website | Đạt | `README.md` hướng dẫn mở trực tiếp, dùng máy chủ Python và chạy bằng Docker/Nginx. |
| Khởi chạy và tải đầy đủ tài nguyên | Cần cải thiện | Chưa thực thi các hướng dẫn; chưa xác minh mã phản hồi, tải CSS/ảnh hoặc lỗi đường dẫn khi chạy qua HTTP. |
| Xử lý thao tác gửi biểu mẫu | Chưa đạt | Biểu mẫu chưa gắn với `<form>` và chưa có xử lý phía máy khách/máy chủ; thao tác gửi không hoàn thành luồng liên hệ. |
| Hiệu năng tải trang cơ bản | Cần cải thiện | Chưa đo thời gian tải, kích thước ảnh, chỉ số hiệu năng hoặc hành vi trên mạng chậm. |
| Xử lý lỗi khi tài nguyên hoặc máy chủ không khả dụng | Cần cải thiện | Chưa kiểm tra trường hợp ảnh/CSS bị thiếu, máy chủ dừng hoặc cổng triển khai bị chiếm. |

### 3.4. Bảo mật, quản lý cấu hình và dữ liệu

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
|---|---|---|
| Quản lý cấu hình và bí mật | Đạt | README cho biết dự án không cần biến môi trường hay thông tin bí mật; trong phạm vi rà soát, không thấy cấu hình bí mật trong HTML/CSS. Đây không thay thế cho quét toàn bộ lịch sử Git hoặc môi trường triển khai. |
| Thu thập, truyền và lưu trữ dữ liệu biểu mẫu | Cần cải thiện | Không thấy luồng gửi/lưu dữ liệu hoạt động trong mã đã rà soát. Cần xác định rõ có giữ biểu mẫu hay chỉ cung cấp liên kết email; nếu triển khai gửi dữ liệu, cần đánh giá quyền riêng tư và bảo vệ dữ liệu. |
| Tài nguyên và mã bên thứ ba | Đạt | Không thấy thư viện JavaScript hoặc script bên thứ ba được nạp trong `index.html`. |
| Liên kết mở tab mới | Cần cải thiện | Liên kết GitHub có `target="_blank"` nhưng chưa khai báo `rel`; nên bổ sung `rel="noopener noreferrer"` để thể hiện rõ chính sách mở liên kết an toàn và tương thích. |
| Cấu hình bảo mật khi triển khai | Cần cải thiện | Chưa kiểm tra HTTPS, security headers, cấu hình Nginx hoặc quyền truy cập trên máy chủ đích. |

### 3.5. Chất lượng mã nguồn, cấu trúc repository và tài liệu bàn giao

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
|---|---|---|
| Tổ chức mã nguồn và tài nguyên | Đạt | HTML, CSS và ảnh được tách thành các tệp/thư mục dễ nhận biết; cấu trúc được mô tả trong `README.md`. |
| Tính nhất quán giữa tài liệu và triển khai | Cần cải thiện | README mô tả website là trang tĩnh và biểu mẫu chưa kết nối dịch vụ, phù hợp với mã hiện tại; cần cập nhật tài liệu khi hoàn thiện luồng liên hệ hoặc liên kết dự án. |
| Ngữ nghĩa cấu trúc biểu mẫu | Chưa đạt | `<fieldset>` đang được đặt trực tiếp bên trong `<ul>` thay vì một `<li>`; các nhãn chưa gắn với input và biểu mẫu thiếu phần tử `<form>`. |
| Tách biệt HTML và CSS | Cần cải thiện | `index.html` chứa một khối `<style>` bên cạnh stylesheet riêng; nên chuyển quy tắc trình bày vào `assets/css/styles.css` để dễ bảo trì. |
| Tính hoàn thiện của nội dung dự án | Cần cải thiện | Liên kết `href="#"` và mô tả/alt chung chung làm giảm tính hoàn thiện của portfolio. |
| Lint, kiểm tra tự động và quy trình build | Cần cải thiện | README cho biết không có framework hoặc quy trình build; chưa có bằng chứng về HTML/CSS validator, lint hoặc kiểm thử tự động. |

### 3.6. Khả năng triển khai, kiểm thử và cung cấp minh chứng

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
|---|---|---|
| Có hướng dẫn triển khai/chạy cục bộ | Đạt | `README.md` có các bước chạy bằng Python và Docker/Nginx cùng địa chỉ truy cập dự kiến. |
| Triển khai thực tế | Cần cải thiện | Chưa thực hiện triển khai hoặc xác minh website trên URL/máy chủ bàn giao. |
| Kịch bản kiểm thử và kết quả | Cần cải thiện | Đã rà soát tĩnh và kiểm tra hiển thị responsive qua ba viewport; chưa có biên bản chạy kiểm thử chức năng, tương thích trên thiết bị thật, hiệu năng hay bảo mật. |
| Minh chứng kiểm thử responsive | Đạt | Đã lưu ảnh chụp viewport trình duyệt tại `docs/screenshots/responsive-mobile.png`, `docs/screenshots/responsive-tablet.png` và `docs/screenshots/responsive-desktop.png`; ảnh được liên kết ở mục 3.2. |
| Minh chứng cho kiểm thử khác | Cần cải thiện | Chưa đính kèm log chạy, kết quả validator, kiểm thử chức năng, hiệu năng, bảo mật hoặc triển khai. |
| Khả năng tái lập kiểm thử | Cần cải thiện | Có hướng dẫn chạy, nhưng chưa có bộ test hoặc checklist thao tác kèm kết quả thực thi để người khác tái lập nghiệm thu. |

## 4. Đánh giá tổng kết và đề xuất

### Nhận định chung

Sản phẩm đã có nền tảng portfolio tĩnh với các khu vực nội dung chính, điều hướng nội bộ và quy tắc CSS responsive. README cung cấp hướng dẫn chạy cục bộ và Docker. Đã kiểm tra hiển thị trên trình duyệt bằng ba viewport và lưu ảnh minh chứng; đây chưa phải kiểm thử trên thiết bị vật lý hoặc nghiệm thu ở môi trường bàn giao. Một số chức năng và chi tiết hoàn thiện còn thiếu, đặc biệt là biểu mẫu liên hệ và liên kết dự án. Vì vậy, sản phẩm **chưa đủ minh chứng để xác nhận sẵn sàng bàn giao**.

### Vấn đề cần xử lý trước khi bàn giao

1. **Ưu tiên cao — Làm rõ chức năng liên hệ:** Nếu cần gửi thông tin, bọc các trường trong `<form>`, gắn nhãn bằng `id`/`for`, bổ sung xử lý gửi an toàn và thông báo thành công/lỗi; nếu không triển khai gửi dữ liệu, bỏ nút gửi gây hiểu nhầm và chỉ giữ liên kết email.
2. **Ưu tiên cao — Hoàn thiện dự án:** Thay các `href="#"` bằng URL/tài nguyên thật hoặc bỏ liên kết “Xem chi tiết” khi chưa có trang đích.
3. **Ưu tiên trung bình — Sửa cấu trúc và khả năng truy cập:** Đặt biểu mẫu đúng cấu trúc ngữ nghĩa, gắn nhãn với trường nhập, mô tả alt ảnh có ý nghĩa và không loại bỏ chỉ báo focus của input.
4. **Ưu tiên trung bình — Kiểm thử giao diện thực tế:** Bổ sung kiểm tra trên thiết bị vật lý và các trình duyệt mục tiêu; kiểm tra điều hướng bàn phím, độ tương phản và việc tải ảnh/CSS.
5. **Ưu tiên trung bình — Thu thập minh chứng:** Chạy thử theo README, lưu log, ghi kết quả từng kịch bản và kiểm tra URL triển khai trước khi nghiệm thu. Ảnh responsive ở các viewport đã được đính kèm.
6. **Ưu tiên thấp — Hoàn thiện cấu hình triển khai:** Xác minh HTTPS và security headers trên máy chủ thực tế; bổ sung `rel="noopener noreferrer"` cho liên kết mở tab mới.

### Điều kiện đề xuất để nghiệm thu

- Các vấn đề ưu tiên cao được xử lý hoặc có xác nhận rõ ràng về phạm vi không hỗ trợ.
- Các luồng điều hướng, liên kết, hình ảnh và biểu mẫu (nếu giữ lại) được chạy thử thành công.
- Giao diện được xác nhận trên trình duyệt và thiết bị mục tiêu; ảnh viewport hiện có không thay thế kiểm thử trên thiết bị vật lý.
- Có URL hoặc hướng dẫn triển khai cuối cùng, kèm minh chứng và kết quả kiểm tra được người đánh giá xác nhận.