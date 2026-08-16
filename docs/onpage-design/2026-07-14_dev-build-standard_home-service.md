# ViBIM — Semantic HTML Guide cho Dev: Homepage + Scan to BIM Service Page

> **Mục đích**: hướng dẫn dev đặt **thẻ semantic HTML cho chuẩn** khi code web chính, theo đúng bộ section + nội dung đã demo. Đây là guide "đặt thẻ thế nào cho đúng", KHÔNG phải review demo.
> **Phạm vi**: chỉ semantic HTML (landmark, heading, article/section, list, strong, figure, table, label). **Schema JSON-LD nằm ngoài phạm vi** (xử lý riêng). **Platform-agnostic** — áp cho mọi nền tảng.
> **Nguồn content (verbatim)**: GDoc Homepage `1cgJjExok…gY8f0` · GDoc Service `10FkN8rS9…Sx34o`. Con số/tên/URL chỉ lấy từ đây — thiếu thì HỎI, không tự điền.
> **Companion element-level**: [`2026-07-13_semantic-html-code-standard.md`](2026-07-13_semantic-html-code-standard.md).

---

## 1. Bốn luật khung — áp mọi page

1. **`<main>` đúng 1 cái**, bọc TẤT CẢ section nội dung (giữa `<header>` và `<footer>`). Không lồng `<main>`, không bọc header/footer vào trong.
   ```
   <body>
     <header>…</header>
     <main> … tất cả section … </main>
     <footer>…</footer>
   </body>
   ```
2. **1 `<h1>`/page** · không skip level (H1→H2→H3, không nhảy H2→H4) · mỗi heading có content ngay dưới · heading mô tả cụ thể · heading KHÔNG dùng để chỉnh cỡ chữ (dùng CSS).
3. **Test chọn `<article>` vs `<section>`**: *"Copy block này sang site khác còn nghĩa không?"* → CÓ = `<article>` (tự-chứa); KHÔNG = `<section>` (cần ngữ cảnh). **Có thứ tự** (bước 1→N) = `<ol>`, không phải `<ul>` hay `<article>`.
4. **Thẻ nhấn/media/form**: số liệu & fact quan trọng bọc `<strong>` (KHÔNG `<b>`) · ảnh bọc `<figure>` (+ `<figcaption>` nếu có caption) · mỗi input form có `<label for>` thật (không chỉ placeholder).

---

## 2. Bảng tag map — HOMEPAGE

Thứ tự = thứ tự content. Cột "Item" = thẻ cho phần tử lặp bên trong.

| # | Section | Heading | Section wrapper | Item bên trong | Ghi chú |
|---|---|---|---|---|---|
| 1 | Hero (Revit BIM Modeling & Outsourcing…) | `<h1>` | `<section class="hero">` | benefit list = `<ul><li>` (label `<strong>`) | H1 = tên page, nằm trong `<main>` |
| 2 | As Seen On | — (`aria-label`) | `<section>` | `<ul><li><a>` 6 báo | list link, KHÔNG article |
| 3 | What Clients Say | `<h2>` | `<section>` | mỗi review = `<article>` + `<blockquote><cite>` | quote tự-chứa |
| 4 | By the Numbers | `<h2>` | `<section>` | `<ul><li><strong>11+</strong> Years…` | **có `<h2>` thật** (ẩn trực quan được); số bọc `<strong>` |
| 5 | All ViBIM Revit BIM Modeling Services (8) | `<h2>` + mỗi svc `<h3>` | `<section>` | **8× `<article>`** | service tự-chứa |
| 6 | BIM Standards & QC | `<h2>` + `<h3>` | `<section>` | 5 điểm QC = `<ul><li><strong>` | — |
| 7 | Featured Projects (6) | `<h2>` + `<h3>`/card | `<section>` | **6× `<article>`** + `<figure>` | project tự-chứa |
| 8 | Why Choose ViBIM (5 pillar) | `<h2>` + `<h3>` | `<section>` | 5× `<section><h3>` hoặc `<ul><li>` | **KHÔNG `<article>`** (cần ngữ cảnh "vì sao ViBIM") |
| 9 | The specialists (5 người) | `<h2>` + mỗi người `<h3>` | `<section>` | **5× `<article>`** (Person) | tự-chứa; **đúng 5** (xem §4) |
| 10 | Industries We Serve (9) | `<h2>` | `<section>` | `<ul><li><strong>label</strong> mô tả` | list, không article |
| 11 | How to Start (Quote/Trial/Pricing) | `<h2>` | `<section>` | **`<ol><li>`** 3 bước | bước tuần tự → `<ol>`, KHÔNG article |
| 12 | BIM Outsourcing Across US/UK/… | `<h2>` | `<section>` | `<ul><li>` markets | nêu US primary |
| 13 | Send Your Scan (form) | `<h2>` | `<section>` | `<form>` + mỗi input `<label for>` | function; label thật |
| 14 | FAQ (6 câu) | `<h2>` + mỗi câu `<h3>` | `<section>` | mỗi Q&A: `<h3>` câu hỏi + `<p>` trả lời | H3 = câu hỏi (AI thích Q&A) |
| 15 | Guides & Insights | `<h2>` | `<section>` | `<ul><li><a>` | link list; **KHÔNG cần `<time>`** (không phải blog card có ngày) |

---

## 3. Bảng tag map — SCAN TO BIM SERVICE PAGE

| # | Section | Heading | Section wrapper | Item bên trong | Ghi chú |
|---|---|---|---|---|---|
| 0 | Breadcrumb | — | `<nav aria-label="Breadcrumb"><ol>` | `<li><a>` Home > Scan to BIM Services | dùng `<ol>` (có thứ tự) |
| 1 | Hero (Scan to BIM Services…) | `<h1>` | `<section class="hero">` | tooltip list = `<ul><li><strong>` | trong `<main>` |
| 2 | As Seen On | — | `<section>` | `<ul><li><a>` 6 báo | — |
| 3 | Client Reviews | `<h2>` | `<section>` | `<article>` + `<blockquote><cite>` | — |
| 4 | By the Numbers | `<h2>` | `<section>` | `<ul><li><strong>` | có `<h2>` + `<strong>` |
| 5 | Point Cloud to BIM by Discipline (4) | `<h2>` + mỗi discipline `<h3>` | `<section>` | **4× `<article>`** | mỗi discipline có scope/output = `<ul>` con |
| 6 | Service Deliverables (4) | `<h2>` + `<h3>` | `<section>` | **4× `<article>`** | — |
| 7 | **How Scan to BIM Works (6 phase/13 step)** | `<h2>` + mỗi phase `<summary>` | `<section>` (giữ `<details>` accordion) | **`<ol>` liền mạch 1→13** | xem §3b — điểm quan trọng nhất |
| 7a | Point Cloud Formats We Accept | `<h3>` (con của #7) | `<section>` | `<ul><li>` | **KHÔNG `<article>`**; đặt ngay sau H2 process |
| 7b | Scan to BIM Software We Use (10) | `<h3>` (con của #7) | `<section>` | `<ul><li><strong>tool</strong>` | — |
| 8 | Accuracy, LOD & Quality (3 measure) | `<h2>` + 3× `<h3>` | `<section>` | bảng LOD = `<table>` (`<thead><th>`) | LOD 100–500 dùng `<table>` thật |
| 9 | Featured Projects (6) | `<h2>` + `<h3>` | `<section>` | **6× `<article>`** + `<figure>` | ảnh NDA-safe |
| 10 | Why Choose ViBIM (5 pillar) | `<h2>` + `<h3>` | `<section>` | 5× `<section><h3>`/`<ul>` | KHÔNG article |
| 11 | The specialists (5 người) | `<h2>` + `<h3>` | `<section>` | **5× `<article>`** | **đúng 5** (§4) |
| 12 | Scan to BIM by Industry (9) | `<h2>` | `<section>` | `<ul><li><strong>` | — |
| 13 | Where Scan to BIM Is Used (7) | `<h2>` | `<section>` | `<ul><li>` | use case |
| 14 | Turnaround, Engagement & Pricing | `<h2>` + 3× `<h3>` | `<section>` | Turnaround `<table>` · Engagement **`<ol>`** 3 bước · Pricing `<ul>` 6 factor | bảng số → `<table>`; bước → `<ol>` |
| 15 | Scan to BIM Worldwide (markets + US states) | `<h2>` + `<h3>` | `<section>` | markets `<ul>`; states `<ul>` multi-col | chỉ **Texas + Washington DC** có `<a>`, còn lại text thường |
| 16 | Checklist Resources (4) | `<h2>` | `<section>` | `<ul><li><a download>` | 4 checklist |
| 17 | Send Your Scan (form) | `<h2>` | `<section>` | `<form>` + `<label for>` | — |
| 18 | FAQ (9 câu) | `<h2>` + mỗi câu `<h3>` | `<section>` | `<h3>` câu + `<p>` đáp | — |
| 19 | Scan to BIM Guides | `<h2>` | `<section>` | `<ul><li><a>` | không cần `<time>` |

### 3b. Process 13-step = `<ol>` thật (không phải `<ul>` + số vẽ tay)

13 bước có tính tuần tự → phải là `<ol>` thì Google/AI mới đọc được là "quy trình". Giữ `<details>` cho UX, nhưng list bước bên trong dùng `<ol>` với `start` nối tiếp qua 6 phase; tiêu đề bước bọc `<strong>` (không `<b>`); số thứ tự để `<ol>` tự sinh (CSS `::marker`/counter), không viết số tay trong `<span>`:

```html
<details name="proc" open>
  <summary><span class="proc-ptitle">Phase 1: Project Setup</span></summary>
  <ol start="1">
    <li><strong>Project Brief Analysis &amp; Scope Clarification</strong></li>
    <li><strong>Point Cloud Preparation &amp; Coordinate Setup</strong></li>
    <li><strong>Level &amp; Grid Establishment</strong></li>
    <li><strong>Element Classification &amp; Modeling Setup</strong></li>
  </ol>
</details>
<details name="proc">
  <summary><span class="proc-ptitle">Phase 2: Discipline Modeling</span></summary>
  <ol start="5"> … </ol>   <!-- nối tiếp bước 5,6 -->
</details>
<!-- Phase 3 start="7" · Phase 4 start="9" · Phase 5 start="11" · Phase 6 start="13" -->
```

---

## 4. Content lock — chống confill (đọc trước khi điền text)

> Mọi token dưới đây khoá theo GDoc. Dev **không thêm/bớt/đổi**; gặp chỗ trống (`[…]`, `http:///`, "set at UX/UI") → **HỎI, không tự lấp**.

- **Số khoá (2 page giống nhau)**: `250,000+` giờ · `11+` năm · `1,000+` dự án · `5+` thị trường · `99%` on-time · `80%` retention · `80%` referral · `up to 30%` nhanh hơn · quote `12–24h` · team `30+` · QC = **2 lớp độc lập** (US+UK).
- **Đếm khoá HOME**: 8 service · **5 chuyên gia** · 6 As-Seen-On · 6 project · 9 industry · 6 FAQ.
- **Đếm khoá SERVICE**: 4 discipline · 4 deliverable · **6 phase/13 step** · 10 software · 3 format nhận (RCP/RCS/E57) · 3 format giao (.RVT/.IFC/.DWG) · 9 industry · 5 market (chỉ Texas+DC có link) · 4 checklist · 9 FAQ · **5 chuyên gia** (giống home — KHÔNG phải 7).
- **Errata trong GDoc (đừng bê nguyên)**: (a) link "Read more" của **Structural** đang trỏ nhầm `/architectural-…` → phải `/structural-bim-modeling/`; (b) mọi href dạng `http:///…` thiếu domain → thay bằng URL thật; (c) review section còn `[hiển thị 2 tab mail…]` → chờ nội dung email thật, **không viết review giả, không bịa số sao**.

---

## 5. QC gate — grep nhanh trước khi ship

| Check | Đạt |
|---|---|
| `<main>` | = 1 |
| `<h1>` | = 1 |
| Heading không skip level | H1→H2→H3 |
| `<b>` | = 0 (dùng `<strong>`) |
| `<article>` chỉ ở block tự-chứa | service/discipline/deliverable/project/expert/review — KHÔNG ở step/pillar/format |
| Process (service) | có `<ol>`, số bước liền mạch 1→13 |
| Bảng số (LOD/Turnaround) | `<table>` có `<thead><th>` |
| Mỗi input form | có `<label>` |
| Đếm entity vs §4 | khớp 100% (đặc biệt **5 expert**) |
| Còn `http:///` / `[…]` chưa xử lý | = 0 |
