---
title: "QR.GEN — Real-time QR Code Studio"
date: 2026-03-30 15:00:00 +0000
categories: [Projects, Python, Web]
tags: [flask, qrcode, pil, web-app, qr-code, frontend]
---

# QR.GEN — Real-time QR Code Studio

A beautiful, real-time QR code generator with advanced customization options.

![alt text](/assets/img/projects/qr_img_1.png)

### Features

- **Live Preview** — See changes instantly as you type or adjust settings
- **Advanced Styling** — Rounded, Square, Circle, Gapped, Horizontal/Vertical bars modules
- **Logo Overlay** — Add your logo/image in circle or rounded square with smart cropping
- **Color Control** — Custom foreground & background with quick presets
- **Error Correction** — L, M, Q, H levels with real-time scannability analysis
- **Dot Controls** — Adjust dot size, gap, opacity, and tint
- **High Quality Export** — Download as optimized PNG

### Tech Stack

- **Backend**: Flask (Python)
- **QR Generation**: `qrcode[pil]` + StyledPilImage
- **Frontend**: Vanilla HTML, CSS, JavaScript (no heavy frameworks)
- **Styling**: Custom dark cyber theme with smooth animations

### Screenshots

![alt text](/assets/img/projects/qr_img_2.png)
![alt text](/assets/img/projects/qr_img_3.png)

### GitHub Repository

**[View Source Code](https://github.com/thesahilsinh/qr-gen)**  

### What I Learned

- Building a responsive real-time web app with Flask
- Advanced usage of the `qrcode` library with custom module drawers
- Image processing with Pillow (smart cropping, masking, overlay)
- Real-time scannability calculation based on error correction + overlay coverage
- Creating a modern, dark cyber-themed UI with pure CSS and vanilla JS

This project helped me improve my full-stack skills and attention to UI/UX details.

---

**Related:**
- [My AI & Web Projects](/projects)