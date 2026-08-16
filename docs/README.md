# Hồ sơ nguồn của trang chủ ViBIM

Thư mục này giữ bản gốc dùng để dựng `index.html` ở thư mục cha. Khi sửa trang, sửa ở đây trước rồi mới port sang HTML — ngược lại thì hồ sơ sẽ lệch với bản live.

## content/

| File | Vai trò |
|---|---|
| `2026-06-21_humanized-homepage-revit-bim-modeling.md` | Bản content trang chủ. Intro là bản v2 (2 đoạn, mô hình 2 vùng). 11 H2, trùng khớp thứ tự với `index.html`. **Chưa có marker ảnh** — vị trí ảnh tra ở `onpage-design/2026-08-14-homepage-image-map.md`. |

## onpage-design/

| File | Vai trò |
|---|---|
| `2026-08-14-homepage-image-map.md` | Bản đồ ảnh: mỗi khối trên trang dùng ảnh nào, alt ra sao. Đây là tài liệu chốt khi thay ảnh. |
| `2026-07-15_SPEC-homepage-revit-bim-semantic.md` | Spec cấu trúc semantic HTML của trang. |
| `2026-07-15_BUILD-NOTES-homepage-revit-bim.md` | Ghi chú lúc dựng: quyết định gì, vì sao. |
| `2026-07-15_semantic-homepage-audit.md` | Kết quả audit semantic của bản dựng. |
| `2026-07-14_dev-build-standard_home-service.md` | Chuẩn build dùng chung cho trang chủ và trang dịch vụ. |

## Ba điểm cần biết trước khi sửa

1. **`index.html` là bản mới nhất**, không phải các file mockup cũ. Hai file mockup trước đó (`2026-06-22_mockup-homepage-revit-bim.html`, `2026-07-15_homepage-revit-bim-semantic.html`) đã được đưa vào `_archive/` trong workspace và không nằm trong repo này.
2. **Ngày sửa file không nói lên file nào còn sống.** Bản dựng trong repo này kế thừa từ 2 mockup kia, nên dù mockup có mtime mới hơn thì bản kế thừa vẫn là bản thắng.
3. Ba ô ảnh trong khối Industries đang **lệch với image map** (Data Center dùng ảnh nhà máy, Hospitality dùng ảnh roller coaster, Residential dùng ảnh văn phòng). Đã ghi chú trong Google Doc, chưa sửa trên trang.
