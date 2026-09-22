# Duong Dai Chau — Personal Website

Trang portfolio cá nhân. Một trang HTML tĩnh, không cần build, không cần cài gì.

## Nội dung thư mục

```
index.html        ← toàn bộ trang (HTML + CSS + JS trong một file)
three.min.js      ← thư viện 3D, để dựng mô hình toà nhà ở hero
assets/           ← ảnh
  portrait.jpg
  zeit-skyline.jpg
  zeit-towers.jpg
  zeit-team.jpg
  poster-session.jpg
  poster-group.jpg
README.md         ← file này
```

Giữ nguyên cấu trúc thư mục. `index.html` gọi `three.min.js` và `assets/...`
theo đường dẫn tương đối, nên nếu đổi tên hoặc di chuyển file thì trang sẽ hỏng.

---

## Đưa lên GitHub Pages để có link tên-bạn.github.io

### Bước 1 — Tạo tài khoản GitHub

Vào https://github.com/signup. **Username bạn chọn chính là tên miền sau này**,
nên hãy chọn kỹ. Ví dụ:

| Username        | Link sẽ là                      |
|-----------------|---------------------------------|
| `duongchau`     | https://duongchau.github.io     |
| `milesdchau`    | https://milesdchau.github.io    |
| `chaudaiduong`  | https://chaudaiduong.github.io  |

Nên dùng tên dễ đọc, không dấu, không số năm sinh — recruiter sẽ nhìn thấy link này.

### Bước 2 — Tạo repository

1. Bấm dấu **+** góc trên bên phải → **New repository**
2. Ô **Repository name**: gõ chính xác `<username>.github.io`
   (ví dụ username là `duongchau` thì gõ `duongchau.github.io`)
3. Chọn **Public**
4. **Không** tích "Add a README file"
5. Bấm **Create repository**

Tên repo phải khớp tuyệt đối với username, nếu sai một ký tự thì GitHub Pages
sẽ không tự bật.

### Bước 3 — Tải file lên

1. Trong repo vừa tạo, bấm link **uploading an existing file**
2. Giải nén file zip, rồi **kéo thả cả `index.html`, `three.min.js` và thư mục `assets`** vào ô upload
3. Kéo nguyên thư mục `assets` vào, đừng kéo từng ảnh rời — GitHub giữ nguyên cấu trúc thư mục
4. Bấm **Commit changes**

### Bước 4 — Đợi

GitHub Pages tự bật cho repo dạng `<username>.github.io`. Đợi khoảng 1–3 phút,
rồi mở `https://<username>.github.io`.

Kiểm tra trạng thái ở tab **Actions** trong repo — dấu tích xanh là đã xong.

---

## Muốn tên miền riêng, ví dụ duongchau.com

1. Mua tên miền ở Namecheap, Cloudflare hoặc Porkbun (khoảng 10–15 USD/năm)
2. Trong repo: **Settings → Pages → Custom domain**, gõ tên miền, bấm Save
3. Ở trang quản lý tên miền, thêm 4 bản ghi **A** trỏ về:
   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```
   và một bản ghi **CNAME** cho `www` trỏ về `<username>.github.io`
4. Quay lại Settings → Pages, tích **Enforce HTTPS**

---

## Sửa nội dung sau này

Mở `index.html` bằng bất kỳ trình soạn thảo nào (VS Code, Notepad++, kể cả Notepad).
Nội dung chữ nằm trong phần `<main>`, gần cuối file. Sửa xong thì upload lại
`index.html` lên GitHub là trang tự cập nhật.

Muốn thêm ảnh dự án: bỏ ảnh vào thư mục `assets/`, rồi trong `index.html` thêm

```html
<img src="assets/ten-anh.jpg" alt="Mô tả ảnh" loading="lazy">
```

Luôn ghi `alt` — vừa tốt cho SEO, vừa hiện ra khi ảnh chưa tải xong.

---

## Vài lưu ý kỹ thuật

- **Form liên hệ** mở ứng dụng email của người gửi với nội dung điền sẵn gửi tới
  dchau38@gatech.edu. Không có server nào lưu tin nhắn, nên không tốn phí và
  không hỏng theo thời gian. Nếu sau này muốn nhận thẳng vào hộp thư mà người gửi
  không phải mở app email, có thể dùng Formspree hoặc EmailJS (bản miễn phí đủ dùng).
- **Mô hình 3D** dùng Three.js chạy bằng WebGL. Máy hoặc trình duyệt quá cũ không
  hỗ trợ WebGL thì phần hero vẫn hiện chữ và nút bình thường, chỉ thiếu mô hình.
- **Font Poppins** tải từ Google Fonts. Không có mạng thì trang tự rơi về font hệ thống.
- Trang tự đổi bố cục trên điện thoại, menu thu thành nút ☰.
