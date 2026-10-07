# Lịch Sử Prompt - Tháng 10/2026

## 2026-10-07 15:46:21
**Prompt:**
> Please build an interactive, retro pixel-art File Converter & Compressor Web Application inside a single, self-contained "index.html" file.
> 
> Project Resources Located in This Workspace:
> - Background Image: "assets/background.jpg" (or .png)
> - Postman Walking Animation: "assets/postman-walk.mp4" (or .gif)
> 
> Core UX & Storyline Mechanics:
> 1. Layout & Visual Integration:
>    - Use "assets/background.jpg" as the full-viewport fixed background (100vw x 100vh, object-fit: cover).
>    - Coordinate Hotspots / Interactive Buttons on the Left: Overlap two transparent, clickable retro pixel button areas exactly over the "Convert file" and "Compress file" positions on the left side of the background. Synthesize retro pixel sound (Web Audio API) and trigger modal/dropdown menus.
> 2. Hover & Click Dropdown Menus:
>    - "Convert file": PDF to PNG, PNG to JPEG, Excel to PDF, Word to PDF, TXT to PDF, JSON to CSV, etc.
>    - "Compress file": Compress Image (JPEG/PNG), Compress PDF, Compress Video.
>    - Upload zone with drag & drop retro pixel styling.
> 3. Postman Character & Background Removal:
>    - Use "assets/postman-walk.mp4" with real-time background keying (mix-blend-mode: screen / Canvas Luma keying).
>    - Idle state waiting near left/center sidewalk.
> 4. Delivery Journey Animation (File Processing Sequence):
>    - Step 1: File drop/select.
>    - Step 2: Postman walks to the right into Saigon Central Post Office entrance doors, vanishes inside, post office windows illuminate with retro badge "Đang xử lý / Delivering & Converting...".
>    - Step 3: Returns from post office, walks to center, turns forward with celebratory jump.
>    - Step 4: Speech bubble "Bưu kiện của bạn đã xử lý xong!", retro download button, and reset button.
> 5. Client-Side Conversion Engine:
>    - PDF-lib / jsPDF, Canvas API, SheetJS, docx/mammoth/pdfjs client-side libraries.
> 6. Technical Delivery:
>    - Single-file "index.html", client-side, zero server dependencies, responsive in Chrome.

## 2026-10-07 16:36:10
**Prompt:**
> CRITICAL FIX: Buttons are completely unclickable and frozen!
> Look at the screenshot:
> 1. The interactive button ("NÉN TỆP") is shifted completely down to the street and misaligned with the visual buttons!
> 2. Clicking anywhere on the buttons does nothing because an invisible overlay or the background div is blocking pointer events (z-index issue).
> 
> PLEASE REWRITE "index.html" WITH THIS FOOLPROOF FIX:
> 1. Real Clickable Retro UI Buttons on the Left (Fixed Positioning):
>    - Do NOT rely on background image coordinates. Instead, create TWO actual HTML <button> elements styled with 16-bit retro pixel CSS:
>      * Top Button: "Convert file" (Grey/Chunky retro border)
>      * Bottom Button: "Compress file" (Blue/Chunky retro border)
>    - Place them inside a fixed container on the left:
>      `position: fixed; top: 32%; left: 30px; display: flex; flex-direction: column; gap: 18px; z-index: 99999;`
>    - Ensure `pointer-events: auto !important;` and `cursor: pointer;` so they are 100% CLICKABLE on any screen size.
> 2. Interactive Dropdown / Popover Modal on Click & Hover:
>    - When clicking or hovering "Convert file":
>      * Instantly pop up a sleek pixel dropdown menu next to the button with options:
>        - "PDF to PNG"
>        - "PNG to JPEG"
>        - "JPEG to WEBP"
>        - "Excel (.xlsx) to PDF"
>        - "TXT to PDF"
>    - When clicking or hovering "Compress file":
>      * Pop up options:
>        - "Nén ảnh (PNG / JPEG)"
>        - "Nén file PDF"
>    - Clicking ANY option opens a clean, retro pixel Drag & Drop modal in the center:
>      * File input: `<input type="file" ...>` with big retro drop zone: "Kéo thả file vào đây hoặc bấm để chọn".
> 3. Animation & Conversion Pipeline:
>    - As soon as the user selects a file:
>      * The postman sprite walks from the sidewalk towards the Saigon Post Office on the right.
>      * Conversion runs client-side (Canvas for images, SheetJS/jsPDF for documents).
>      * Postman walks back out to the center and displays the "TẢI VỀ / DOWNLOAD" button with confetti!
> 4. Clean DOM & CSS:
>    - Ensure the background image has `pointer-events: none;` so it NEVER intercepts clicks.
>    - Consolidate everything in "index.html". Make sure it is fast, lightweight, and responds to clicks immediately.

## 2026-10-07 17:14:55
**Prompt:**
> Please update "index.html" with the following two quick UI improvements:
> 1. Compact Top-Left Title Badge:
>    - Make the top-left title banner ("1891 BƯU ĐIỆN TRUNG TÂM SÀI GÒN • PIXEL CONVERTER") much shorter and more compact so it doesn't take up excessive screen width.
>    - Shorten the display text to: "BƯU ĐIỆN SÀI GÒN" (or "SG POST • CONVERTER").
>    - Reduce its font size, padding, and max-width (e.g., `font-size: 11px; padding: 4px 10px; max-width: fit-content;`) with a neat, compact 16-bit retro pixel border.
> 2. Remove "Postman Sprite" Artifact Completely:
>    - Ensure there is NO broken image tag, NO `<img alt="Postman Sprite">`, and no fallback text rendered above the postman's head.
>    - The postman must be rendered cleanly and solely by the video/sprite container without any text labels hovering on top.
> 
> Please apply these updates directly inside "index.html".
