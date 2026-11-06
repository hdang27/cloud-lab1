# Hướng dẫn hoàn thành & Triển khai Lab 01 (Phương án B: GitHub Pages)

Tài liệu này tổng hợp toàn bộ các bước triển khai, vị trí điền thông tin cá nhân và **câu trả lời mẫu cho Task 4 (Q1–Q5)** để bạn đưa vào file báo cáo PDF (`Lab01_Report_<MSSV>.pdf`).

---

## 1. Vị trí cần điền thông tin cá nhân trong `index.html`

Mở file [index.html](file:///d:/UTE/cloud%20computing/cloud-lab1/index.html) bằng VS Code hoặc text editor, tìm các cụm sau để thay thế bằng thông tin của bạn:

1. **Họ và tên**: 
   - Tìm: `[Họ và Tên của bạn / Your Full Name]`
   - Thay bằng: Họ và tên sinh viên của bạn (ví dụ: `Lê Hải Đăng` hoặc `Nguyễn Văn A`).
2. **Mã số sinh viên (MSSV)**:
   - Tìm: `[Mã số sinh viên / Student ID]`
   - Thay bằng: Mã số sinh viên của bạn (ví dụ: `22110...`).
3. **GitHub Username (cho đường dẫn repo và URL website)**:
   - Tìm: `[YOUR_GITHUB_USERNAME]` hoặc `YOUR_GITHUB_USERNAME`
   - Thay bằng username GitHub của bạn (ví dụ nếu username là `haidang00`, đường dẫn sẽ là `https://haidang00.github.io/cloud-lab1/` và `https://github.com/haidang00/cloud-lab1`).

---

## 2. Hướng dẫn từng bước triển khai lên GitHub Pages (Option B)

### Bước 1: Tạo Repository trên GitHub
1. Đăng nhập tài khoản GitHub tại [github.com](https://github.com).
2. Tạo một repository mới (New repository) với:
   - **Repository name**: `cloud-lab1` (bắt buộc đúng tên theo yêu cầu bài lab).
   - **Visibility**: Chọn **Public** (công khai).
   - Không cần tích chọn Initialize with README / .gitignore (vì ta sẽ đẩy code từ máy lên).
   - Bấm **Create repository**.

### Bước 2: Đẩy source code từ máy lên GitHub
Mở terminal (PowerShell hoặc Git Bash) tại thư mục `d:\UTE\cloud computing\cloud-lab1` và chạy các lệnh sau:

```bash
cd "d:\UTE\cloud computing\cloud-lab1"
git init
git add .
git commit -m "feat: initial commit for Lab 01 static cloud website"
git branch -M main
git remote add origin https://github.com/<YOUR_GITHUB_USERNAME>/cloud-lab1.git
git push -u origin main
```
*(Thay `<YOUR_GITHUB_USERNAME>` bằng username GitHub của bạn).*

### Bước 3: Bật tính năng GitHub Pages
1. Trên giao diện GitHub của repository `cloud-lab1`, vào tab **Settings** (Cài đặt).
2. Ở thanh bên trái, tìm mục **Pages** (dưới nhóm *Code and automation*).
3. Tại phần **Build and deployment**:
   - **Source**: Chọn `Deploy from a branch`.
   - **Branch**: Chọn nhánh `main` và thư mục `/ (root)`.
   - Bấm **Save**.
4. Chờ khoảng 1–2 phút cho GitHub Actions hoàn tất việc deploy. F5 lại trang Settings -> Pages sẽ thấy banner màu xanh:
   `Your site is live at https://<YOUR_GITHUB_USERNAME>.github.io/cloud-lab1/`

---

## 3. Câu trả lời mẫu cho Task 4 (Q1 – Q5) (độ dài 50–100 từ mỗi câu)

Bạn có thể sử dụng trực tiếp các câu trả lời dưới đây cho phần **Task 4: Explain Your Deployment** trong file báo cáo PDF:

### Q1: Which platform did you select, and why?
> **Answer (76 words):**
> I selected GitHub Pages (Option B) because it offers a seamless, zero-cost, and developer-friendly solution for hosting static websites. It integrates natively with Git version control, allowing automated continuous deployment whenever changes are pushed to the main branch. Additionally, GitHub Pages provides an enterprise-grade global Content Delivery Network (CDN) with free, automatically managed SSL/TLS certificates, ensuring high availability, rapid page loading speeds, and public accessibility worldwide without requiring server provisioning or credit card registration.

### Q2: How does opening index.html locally differ from visiting the deployed HTTPS URL?
> **Answer (83 words):**
> Opening `index.html` locally uses the `file://` protocol, rendering files directly from the local filesystem on a single computer without network transmission, web server handling, or security certificates. Conversely, visiting the deployed HTTPS URL accesses the website over the public Internet via the `https://` protocol. The request is routed through a distributed Content Delivery Network (CDN), encrypted using TLS/SSL certificates, and served by cloud edge servers, making the website universally accessible to any user and browser globally with verified security.

### Q3: What is HTTPS, and why is it important?
> **Answer (79 words):**
> Hypertext Transfer Protocol Secure (HTTPS) is an extension of HTTP that secures communication over computer networks using Transport Layer Security (TLS/SSL) encryption. HTTPS is critical for three primary reasons: data confidentiality (encrypting sensitive traffic to prevent eavesdropping), data integrity (ensuring transmitted content cannot be intercepted or tampered with by man-in-the-middle attacks), and identity authentication (cryptographically proving to visitors via trusted digital certificates that they are connecting to the legitimate server rather than an impostor).

### Q4: Does the selected hosting platform fit IaaS, PaaS or SaaS directly? Explain its characteristics.
> **Answer (85 words):**
> GitHub Pages most closely fits the Platform as a Service (PaaS) model, with characteristics of a specialized serverless hosting platform. Users do not manage physical hardware, virtual machines, operating systems, or web server daemons (which would be IaaS). Instead, developers simply provide application code and assets (HTML, CSS, JavaScript), and the underlying platform automatically handles infrastructure provisioning, static build processing, web serving, global CDN routing, and certificate management. It differs from SaaS because users deploy custom code rather than consuming finished turnkey applications.

### Q5: What changes would be needed for authentication or a database?
> **Answer (88 words):**
> Because GitHub Pages only serves static files, supporting user authentication or dynamic database persistence requires introducing a backend architecture. We could adopt a serverless Jamstack approach by integrating cloud functions (such as AWS Lambda, Cloudflare Workers, or Supabase) to handle server-side API requests. For user authentication, we would integrate third-party identity providers such as Auth0, Firebase Authentication, or AWS Cognito. For database storage, client-side scripts would interact via secure REST or GraphQL APIs with managed cloud databases such as MongoDB Atlas, Supabase PostgreSQL, or DynamoDB.

---

## 4. Danh sách 4 ảnh chụp minh chứng cần chụp cho PDF Report (Task 5)

Theo mục **5. PDF Report — Required Evidence** trong đề bài, bạn cần chụp 4 ảnh màn hình sau:

1. **E1 — Desktop website**: Chụp toàn bộ giao diện website trên trình duyệt máy tính (thấy rõ phần About Me có Họ tên và MSSV của bạn).
2. **E2 — Mobile website**: Mở Inspect (F12) trên trình duyệt, chuyển sang chế độ thiết bị di động (Responsive / iPhone / Android) và chụp lại màn hình hiển thị đẹp trên điện thoại.
3. **E3 — Hosting dashboard**: Chụp màn hình trang **Settings -> Pages** trên GitHub repo của bạn, thấy rõ thông báo deploy thành công kèm link `https://<YOUR_GITHUB_USERNAME>.github.io/cloud-lab1/`.
4. **E4 — HTTPS verification**: Chụp thanh địa chỉ (address bar) của trình duyệt khi mở trang web ở chế độ ẩn danh (Incognito/Private), thấy rõ icon ổ khóa bảo mật và đường dẫn `https://...`.

---

## 5. Quy cách nộp bài (Submission)

- **File nộp**: 1 file ZIP duy nhất theo định dạng:
  `Lab01_<StudentID>_<FullName>.zip`
  *(Ví dụ: `Lab01_22110123_NguyenVanA.zip`)*
- **Cấu trúc bên trong file ZIP**:
  ```
  Lab01_22110123_NguyenVanA.zip
  ├── index.html
  ├── style.css
  ├── assets/
  │   └── cloud.svg
  └── Lab01_Report_22110123.pdf
  ```
- **Trên hệ thống LMS**: Dán URL HTTPS công khai vào ô nộp bài (submission field) và đính kèm file ZIP trên.
