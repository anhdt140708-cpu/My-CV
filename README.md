# My CV – Đào Thiện Anh

Trang portfolio/CV cá nhân giới thiệu Đào Thiện Anh, sinh viên năm nhất ngành Công nghệ thông tin và định hướng Frontend Developer. Dự án là website tĩnh, được xây dựng để trình bày thông tin cá nhân, kỹ năng, dự án và cách liên hệ.

## Chức năng

- Giới thiệu cá nhân và định hướng nghề nghiệp.
- Trình bày kỹ năng HTML5, CSS3, Flexbox và Grid.
- Hiển thị các dự án tiêu biểu cùng hình ảnh minh họa.
- Điều hướng nhanh đến phần Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Bố cục responsive, ưu tiên thiết bị di động.
- Hiển thị liên kết email và GitHub.

> Biểu mẫu liên hệ hiện chỉ là giao diện HTML, chưa kết nối dịch vụ gửi email hay máy chủ xử lý dữ liệu.

## Công nghệ

- HTML5
- CSS3 (Flexbox, CSS Grid, custom properties và media queries)
- Không sử dụng framework, thư viện JavaScript, cơ sở dữ liệu hoặc quy trình build.
- Docker tùy chọn để phục vụ website qua Nginx.

## Cấu trúc dự án

```text
.
├── index.html
├── README.md
└── assets/
    ├── css/
    │   └── styles.css
    └── img/
        ├── My image.jpg
        └── Ảnh hoàn thành Flexbox Froggy.png
```

## Yêu cầu môi trường

- Trình duyệt hiện đại như Chrome, Firefox, Edge hoặc Safari.
- Không cần cài Node.js hay tải các thư viện phụ thuộc.
- Để chạy máy chủ web cục bộ: Python 3 (không bắt buộc nếu chỉ mở trực tiếp `index.html`).
- Để chạy bằng Docker: Docker Engine và Docker CLI; trên Windows/macOS có thể dùng Docker Desktop.

## Cài đặt

Tải hoặc sao chép mã nguồn về máy, sau đó mở terminal tại thư mục dự án. Nếu dùng Git:

```bash
git clone https://github.com/anhdt140708-cpu/My-CV.git
cd My-CV
```

Nếu đã có thư mục mã nguồn, chỉ cần mở terminal tại thư mục chứa `index.html`.

## Cấu hình

Dự án không có tệp cấu hình môi trường, biến môi trường hay thông tin bí mật cần thiết.

- Nội dung, tiêu đề trang và thông tin liên hệ có thể chỉnh sửa trong `index.html`.
- Kiểu dáng và điểm breakpoint responsive có thể chỉnh sửa trong `assets/css/styles.css`.
- Khi thay ảnh, đặt ảnh trong `assets/img/` và cập nhật đường dẫn `src` tương ứng trong `index.html`.
- Giữ nguyên cấu trúc thư mục tương đối để các liên kết đến CSS và ảnh hoạt động.

## Chạy thử

### Mở trực tiếp

Mở `index.html` bằng trình duyệt. Cách này phù hợp để xem nhanh giao diện; một số chức năng của trình duyệt có thể hoạt động khác khi tệp được mở trực tiếp thay vì qua máy chủ web.

### Chạy máy chủ web cục bộ

Máy chủ Python phục vụ nội dung tĩnh trên cổng `8000`. Chạy lệnh tại thư mục dự án, sau đó truy cập <http://localhost:8000>.

**Windows (PowerShell):**

```powershell
py -m http.server 8000
```

Nếu lệnh `py` không có sẵn nhưng đã cài Python:

```powershell
python -m http.server 8000
```

**macOS:**

```bash
python3 -m http.server 8000
```

**Linux:**

```bash
python3 -m http.server 8000
```

Dừng máy chủ bằng `Ctrl+C` trong terminal.

## Chạy bằng Docker

Docker sẽ chạy Nginx và phục vụ thư mục dự án tại <http://localhost:8080>. Các lệnh dưới đây mount thư mục hiện tại ở chế độ chỉ đọc; không cần tạo Dockerfile.

Trước tiên, bảo đảm Docker Engine/Docker Desktop đang hoạt động và terminal đang ở thư mục chứa `index.html`.

**Windows (PowerShell):**

```powershell
docker run --name my-cv -d -p 8080:80 -v "${PWD}:/usr/share/nginx/html:ro" nginx:alpine
```

**macOS:**

```bash
docker run --name my-cv -d -p 8080:80 -v "$(pwd):/usr/share/nginx/html:ro" nginx:alpine
```

**Linux:**

```bash
docker run --name my-cv -d -p 8080:80 -v "$(pwd):/usr/share/nginx/html:ro" nginx:alpine
```

Mở <http://localhost:8080> để xem trang. Nếu cổng `8080` đang được sử dụng, đổi phần `-p 8080:80` sang một cổng trống, ví dụ `-p 8081:80`, rồi truy cập cổng mới.

Dừng và xóa container sau khi chạy thử:

```bash
docker stop my-cv
docker rm my-cv
```

## Thông tin liên hệ

- **Tác giả:** Đào Thiện Anh
- **Email:** [anhdt140708@gmail.com](mailto:anhdt140708@gmail.com)
- **GitHub:** [github.com/anhdt140708-cpu](https://github.com/anhdt140708-cpu)
