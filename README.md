# kgen.cloud - Landing Page

Khảo sát mức độ thương hiệu Việt xuất hiện trong AI search (ChatGPT, Claude, Perplexity, Gemini).

## Cấu trúc

| File | Mục đích |
|---|---|
| `index.html` | Landing page chính, single-file HTML/CSS/JS |
| `chinh-sach-bao-mat.html` | Trang chính sách bảo mật (Nghị định 13/2023/NĐ-CP) |
| `dieu-khoan-su-dung.html` | Trang điều khoản dịch vụ |
| `vercel.json` | Vercel config (clean URLs + security headers) |

## Deploy

Auto-deploy qua Vercel khi push lên `main`. Mỗi commit = 1 preview URL.

## Stack

- Pure HTML/CSS/JS, không build process
- noti-vn liquid glass design system
- Font: Inter (Google Fonts)
- Form submit POST tới webhook backend (cấu hình `WEBHOOK_URL` trong `index.html`)

## Edit production

Sửa file → commit → push → Vercel tự deploy. Đợi 30s.

## TODO trước khi launch

- [ ] Thay `WEBHOOK_URL` trong `index.html` từ placeholder → URL n8n thật
- [ ] Setup email `hello@kgen.cloud` qua Hostinger Email
- [ ] Tạo Calendly link và add vào landing nếu cần
- [ ] Rà soát 2 trang chính sách + nhờ luật sư check (Nghị định 13/2023/NĐ-CP)

## Liên hệ

hello@kgen.cloud
