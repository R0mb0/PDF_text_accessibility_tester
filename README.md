# PDF Accessibility Checker

[![Codacy Badge](https://app.codacy.com/project/badge/Grade/6b90593f124e4b8a94e63cd32a61b93b)](https://app.codacy.com/gh/R0mb0/PDF_text_accessibility_tester/dashboard?utm_source=gh&utm_medium=referral&utm_content=&utm_campaign=Badge_grade)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/R0mb0/PDF_text_accessibility_tester)
[![Open Source Love svg3](https://badges.frapsoft.com/os/v3/open-source.svg?v=103)](https://github.com/R0mb0/PDF_text_accessibility_tester)
[![MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/license/mit)
[![Donate](https://img.shields.io/badge/PayPal-Donate%20to%20Author-blue.svg)](http://paypal.me/R0mb0)

A modern, client-side web tool for checking the accessibility of PDF documents in batch. Upload one or more PDF files and instantly see if their text is selectable and readable — all directly in your browser, with no server upload required. Results are shown with document previews, clear status indicators, and easy navigation.

<div align="center">

[![example](https://github.com/R0mb0/PDF_text_accessibility_tester/blob/main/ReadMe_Imgs/example.png)](https://github.com/R0mb0/PDF_text_accessibility_tester)

</div>

---

## Features

- **Batch upload PDF files:** Select one or more PDFs from your computer. Only `.pdf` files are accepted (Windows shortcuts and other types are excluded).
- **Image area tolerance slider:** Choose the maximum percentage of document area that can be made up of images (default: 80%). If a document contains more images than the set threshold, it is considered not accessible. This allows for more granular control over what is considered accessible, even for mixed-content PDFs.
- **Client-side analysis:** All processing happens in your browser; no files are uploaded or stored elsewhere.
- **Accessibility check:** The tool analyzes each PDF to verify if it contains selectable and readable text (not just images or corrupted content).
- **Visual previews:** See a thumbnail of the first page for each PDF, or a placeholder if no preview is available.
- **Clear results table:** Each document is marked as accessible (green lamp) or not accessible (red lamp), along with its file name and preview.
- **Paginated results:** If more than 20 files are uploaded, results are split across pages, with navigation controls.
- **Progress bar and smooth UI:** Animated progress indicators for file loading and analysis, with a modern, responsive interface.
- **Legend:** A clear legend explains the meaning of the green and red icons.

---

## What is "PDF Accessibility"?

In this tool, a PDF is considered **accessible** if:
- The document contains at least one page with selectable, readable text (not just scanned images).
- The extracted text is readable (not corrupted or made up of random/garbled characters).
- The percentage of image area in the document is **less than** the tolerance threshold set by the user (default: 80%).

A PDF is **not accessible** if:
- It only contains scanned images (no selectable text).
- Its text is damaged or unreadable when copied/pasted.
- It is encrypted, protected, or fails to load.
- The percentage of the document composed of images is **equal to or greater than** the selected tolerance.

---

## How To Use

1. **Open the application** in your browser (just open `index.html`).
2. Click the **"Upload documents"** button.
3. Optionally, adjust the **image area tolerance** slider to your desired value (default 80%). This sets the threshold for how much of a PDF can be image content before it is marked as "not accessible".
4. Select one or more PDF files from your computer (only real PDF files are accepted; Windows shortcuts are skipped).
5. Wait for the progress bar and analysis to finish.  
   - The tool will first show file upload progress, then analysis progress.
6. View results in the table:
   - Each row shows a preview, file name, and accessibility status (green/red lamp).
   - If you uploaded more than 20 PDFs, use the navigation buttons below the table.
7. Check the legend for icon meanings.
8. Click **"Upload more files"** to start a new session.

---

## How the Tolerance Slider Works

The **image area tolerance slider** allows you to define the maximum percentage of each PDF that can be composed of images for it to be considered accessible.  
- **Default value:** 80% (indicated on the slider).  
- If a PDF has images that cover more than the selected percentage, it is **not accessible**.
- This is useful for mixed-content PDFs where a small amount of selectable text does not make the document truly accessible.

---

## Limitations

- Does not check for full WCAG/PDF-UA accessibility, only for selectable/readable text and image content percentage.
- Password-protected, encrypted, or DRM PDFs are marked as "not accessible".
- Analysis speed depends on your browser and computer.
