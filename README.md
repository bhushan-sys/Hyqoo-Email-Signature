# Hyqoo-Email-Signature

[![semantic release](https://github.com/bhushan-sys/Hyqoo-Email-Signature/workflows/semantic%20release/badge.svg)](https://github.com/bhushan-sys/Hyqoo-Email-Signature/actions?query=workflow%3A%22semantic+release%22) [![coverage](https://github.com/bhushan-sys/Hyqoo-Email-Signature/workflows/coverage/badge.svg)](https://bhushan-sys.github.io/Hyqoo-Email-Signature/) [![npm](https://badge.fury.io/js/hyqoo-email-signature.svg)](https://www.npmjs.com/package/hyqoo-email-signature)

Interactive, brand-compliant email signature studio engineered for Outlook and Gmail compatibility

## Install

```
npm install hyqoo-email-signature
```

<!-- anything below this line will be safe from template removal -->

---

## 📌 Project Description

The **Hyqoo Email Signature Studio** is an intuitive, web-based tool designed to help team members quickly create, customize, and apply professional, brand-compliant email signatures.

Whether you use Classic Outlook, New Outlook, or Webmail (Office 365), this studio ensures your signature always looks sharp, consistent, and properly formatted across all desktop and mobile devices. Simply choose a template, enter your contact information, customize your profile photo and badges, and copy your signature directly into your email client with a single click.

---

## ✨ Features

- **🎨 Multi-Template Gallery**: Switch seamlessly between curated signature design variations (Template 1, Template 2, Template 3).
- **⚡ Real-Time Live Preview**: Instantaneous sandbox preview that updates as you type or toggle options.
- **🖼️ Profile Photo Customizer**:
  - Drag-and-drop headshot upload supporting PNG, JPG, JPEG, and WEBP formats.
  - Interactive canvas editor with direct drag-to-reposition controls.
  - Smooth scale slider (from 100% up to 200%).
  - Brand-aligned barrel mask clipping with toggle on/off support.
- **📝 Dynamic Form Controls**:
  - Floating label fields for Name, Job Title, Email ID, Contact Number (with real-time digit validation), Location, and LinkedIn profile.
- **🏆 Brand & Certification Accolades**:
  - Toggle company badges on demand: *President's Club*, *WLAB*, *Workplace for Women*, and *Great Place to Work Certification*.
  - Self-adjusting vertical table divider lines that adapt dynamically to signature height and badge selections.
- **📋 One-Click Rich-Text Clipboard Export**:
  - Direct clipboard write using standard Clipboard API (`text/html` & `text/plain`).
  - Automated conversion of vector SVGs to high-resolution (2x Retina) PNG data URIs to ensure flawless rendering in Microsoft Outlook.
- **🧭 Platform-Specific Guided Walkthroughs**:
  - Interactive step-by-step setup modals with instructions tailored for **Classic Outlook**, **New Outlook**, and **Office 365 (Web)**.
- **💡 Built-in Onboarding Tour**:
  - Guided interactive tour powered by Driver.js to assist first-time users.

---

## 🚀 Installation Instructions

### Prerequisites
- [Node.js](https://nodejs.org/) (version 18 or higher recommended)
- Git

### Steps

1. **Clone the repository**:
   ```bash
   git clone https://github.com/bhushan-sys/Hyqoo-Email-Signature.git
   cd Hyqoo-Email-Signature
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Run the local development server**:
   - **Option A: Using the built-in PowerShell server**:
     ```powershell
     powershell -ExecutionPolicy Bypass -File ./server.ps1
     ```
   - **Option B: Using any static HTTP file server** (e.g. `npx serve` or VS Code Live Server):
     ```bash
     npx serve .
     ```
   - Open your browser and navigate to `http://localhost:3000`.

4. **Run automated end-to-end tests (Playwright)**:
   ```bash
   npx playwright test
   ```

---

## 💻 Usage

1. **Select Your Email Client**: Click on **Outlook**, **New Outlook**, or **Office 365** to view matching configuration steps.
2. **Choose a Template**: Use the top template tabs (Template 1, 2, or 3) to pick your desired visual layout.
3. **Customize Your Headshot (Optional)**:
   - Drag and drop your photo into the upload dropzone or click to browse.
   - Drag the image across the canvas to center your face and use the scale slider to adjust framing.
   - Toggle the switch off if you prefer a compact, text-only signature.
4. **Enter Your Details**: Fill in your Name, Job Title, Collabera Email, Contact Number, Location, and LinkedIn handle.
5. **Copy & Apply**:
   - Click **"Apply Your Signature"** or **"Copy Signature"**.
   - Open your email client's signature preferences.
   - Paste (`Ctrl + V` on Windows / `Cmd + V` on macOS) directly into the signature editor and save.

---

## 🛠️ Contribution Guidelines

Contributions that enhance templates, improve email client compatibility, or refine the user experience are welcome!

### Architectural & Email Rendering Rules
When contributing new templates or modifying existing HTML layouts, you **must adhere to strict email client standards**:
- **Pure Nested Tables**: Use `<table>`, `<tr>`, and `<td>` for all structural layouts. CSS Flexbox, Grid, and absolute positioning are not supported by Outlook's WordHTML engine and must not be used.
- **Inline Styling Only**: All CSS styles must be applied directly to HTML elements via the `style=""` attribute. Do not use `<style>` blocks in the `<head>`.
- **Solid Hex Colors Only**: Microsoft Outlook ignores `rgba(...)` syntax. Use solid 6-digit hex values (e.g., `#B4BEBF` instead of `rgba(5, 38, 43, 0.3)`).
- **SVG to PNG Conversion**: Outlook strips raw SVG vectors from clipboard payloads. All icons and brand logos must be converted via `getHtmlWithPngImages()` in `app.js` prior to export.
- **Preserve Vector Aspect Ratios**: Retain natural graphic proportions and specify explicit `width` and `height` attributes on all `<img>` tags.
- **Audit Logging**: Document all bug fixes, template adjustments, and root cause notes in [Error Log File.txt](Error%20Log%20File.txt).

### Development Workflow
1. Fork the repository and create your feature branch:
   ```bash
   git checkout -b feature/new-template-variant
   ```
2. Test your changes thoroughly across browsers and target email clients (Classic Outlook, New Outlook, Gmail, Apple Mail).
3. Commit your changes with clear, semantic commit messages:
   ```bash
   git commit -m "feat: add template 4 with modern banner layout"
   ```
4. Push your branch and open a Pull Request against `main`.

---

## 📄 License

This project is licensed under the ISC License. See [package.json](package.json) for details.