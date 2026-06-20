# kgen.cloud - Web

Repo monorepo cho các trang công khai của kgen.cloud. Mỗi dịch vụ nằm trong 1 subfolder, deploy chung qua Vercel.

## Cấu trúc

```
/
├── index.html                          ← kgen.cloud (hub homepage)
├── geo/                                ← kgen.cloud/geo
│   ├── index.html                      ← GEO Audit landing
│   ├── chinh-sach-bao-mat.html         ← /geo/chinh-sach-bao-mat
│   └── dieu-khoan-su-dung.html         ← /geo/dieu-khoan-su-dung
├── vercel.json                         ← Vercel config
└── README.md
```

## URL routing

| URL | File | Dịch vụ |
|---|---|---|
| `kgen.cloud/` | `index.html` | Hub homepage (list dịch vụ) |
| `kgen.cloud/geo` | `geo/index.html` | GEO Audit landing |
| `kgen.cloud/geo/chinh-sach-bao-mat` | `geo/chinh-sach-bao-mat.html` | Chính sách bảo mật GEO Audit |
| `kgen.cloud/geo/dieu-khoan-su-dung` | `geo/dieu-khoan-su-dung.html` | Điều khoản dịch vụ GEO Audit |

Vercel `cleanUrls: true` tự ẩn `.html` extension.

## Deploy

Auto-deploy qua Vercel khi push lên `main`. Mỗi commit = 1 preview URL.

## Stack

- Pure HTML/CSS/JS, không build process
- noti-vn liquid glass design system
- Font: Inter (Google Fonts)
- Form submit POST tới n8n webhook (cấu hình `WEBHOOK_URL` trong `geo/index.html`)

## Thêm dịch vụ mới

```bash
mkdir new-service
cp geo/index.html new-service/index.html  # base template
# Edit content
git add new-service && git commit && git push
```

Service tự xuất hiện tại `kgen.cloud/new-service` sau khi Vercel deploy.

Đừng quên link service mới vào `/index.html` (hub homepage) section "services-grid".

## TODO trước khi launch

- [ ] Thay `WEBHOOK_URL` trong `geo/index.html` từ placeholder → URL n8n thật
- [ ] Setup email `hello@kgen.cloud` qua Hostinger Email
- [ ] Tạo Calendly link và add vào landing nếu cần
- [ ] Rà soát 2 trang chính sách `geo/` + nhờ luật sư check (Nghị định 13/2023/NĐ-CP)

## Liên hệ

hello@kgen.cloud
