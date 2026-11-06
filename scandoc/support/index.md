---
# Trang hỗ trợ Scan Doc (Support URL App Store). Mọi ý dưới đây lấy từ chức năng THẬT của app:
# E:/Onsite/flutter/tmk_scan_doc/cau_truc.md mục 1-10 (quét, lịch sử, chi tiết, sửa chữ + dịch, xuất PDF,
# ký tên, đóng dấu, tab Công cụ, Cài đặt, SQLite), mục 15 (nối / tách trang), mục 19 (bộ chữ OCR),
# mục 20 (nhập ảnh), mục 21 (Xử lý PDF 6 việc). Không có app_name → trang chủ không liệt kê như 1 chính
# sách. Mẫu: /fincore/support/.
layout: default
permalink: /scandoc/support/
title: "Scan Doc — Support"
description: "Support for Scan Doc: document scanner, OCR and PDF toolkit."
last_updated: 2026-11-06
---

<article class="app-policy">
  <p class="app-back"><a href="{{ '/scandoc/' | relative_url }}">← Scan Doc privacy policy</a></p>
  <header class="app-header">
    <h1>Scan Doc — Support</h1>
  </header>

<div markdown="1">

Need help with **Scan Doc**? Email **TMK Tech Group** at [tmktechgroup@gmail.com](mailto:tmktechgroup@gmail.com). Please include your device model and what happened.

## No account, no sign-in

Scan Doc works on your device. There is nothing to register and nothing to log in to, so there is no password to lose and no server that can go down.

## Scanning a document

Open the **Scan** tab and tap the scan button. The camera finds the edges of the page by itself; you can keep adding pages up to ten in one document. When you finish, the app reads the text on every page and saves one document, then opens it so you can check it.

**Tools → Scan ID Card** is the same scanner limited to two pages, for the front and back of a card.

No camera at hand? **Tools → Import images** takes pictures you already have in your photo library and makes a document out of them the same way.

## Finding what you scanned

Every document is listed in the **History** tab with its name, date and page count. Tap a card to open it. Inside you can swipe between pages, pinch to zoom, rename the document, or delete it.

Nothing is uploaded, so the list is only ever on this phone. Uninstalling the app deletes all of it, and nobody — including us — can recover it.

## Fixing the recognised text

Open a document and tap the text button. The recognised text is editable, so you can correct anything the camera misread, then save it back into the document.

If the text comes back wrong for a whole document, check **Settings → Writing system**: text recognition needs to know whether it is reading Latin, Chinese, Devanagari, Japanese or Korean script. Leave it on **Follow the app language** and it picks the one matching your app language.

## Translating

On the same text screen, pick the language you are translating **from** and **to**, then tap translate. The first time you use a language, your phone downloads that language pack from Google — that needs a connection, and takes a moment. After that, translation runs on the phone.

## Getting documents out

From a document: **Export PDF**, **Export Word** (`.docx`), or **Share**. Sharing opens your phone's own share sheet, so the file goes wherever you send it.

## Signing and stamping

**Tools → Sign** opens a pad: draw your signature with a finger or a stylus, undo strokes, or clear and start again, then place it on the page.

**Tools → Watermark** stamps text you type across the page, for example DRAFT or COPY.

## Pages

In a document, open **Pages** to add more pages, bring in another document, reorder pages by dragging, rotate a page, or remove one. You can also select several pages and **Split** them into a new document — keeping them in both documents, or moving them out.

## PDF tools

**Tools → PDF tools** holds six jobs for PDF files already on your phone. Pick files, set the options, tap Run; results are saved in the app folder and the Share button sends them out.

- **Merge** — several PDFs or images into one PDF.
- **Split** — one PDF into a number of parts, or a page range you type.
- **Compress** — rebuilds the pages as images at a lower resolution to make the file smaller. Four levels: Screen, E-book, Printer, Prepress. Text in the result can no longer be selected.
- **To image** — each page as a PNG or JPEG.
- **To Word** — reads the text on the pages and writes a `.docx`.
- **To Markdown** — reads the text on the pages and writes a `.md`, one heading per page. The text is written exactly as recognised: no headings, lists or tables are guessed from how the page looks.

**Resolution (DPI)** is a number you type, anywhere from 36 to 600. Higher is clearer but makes a bigger file. Choosing a compression level fills it in for you, and you can still change it.

Scanned PDFs have no text layer, so **To Word** and **To Markdown** run text recognition over the pages first — a long document takes a while, and the page counter shows where it is.

## Language and appearance

The **Settings** tab holds dark mode, five accent colours, the app language and the writing system used for text recognition. Your choices are remembered the next time you open the app.

## Privacy

Read our [Privacy Policy](https://privacy.tmktechgroup.com/scandoc/).

</div>
</article>
