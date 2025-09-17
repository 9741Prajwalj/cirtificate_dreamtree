# DreamTree Certificate Generator

A web-based application for generating customizable certificates of completion and assessment. This tool allows users to input student details, course information, and export professional-looking certificates as PDF files.

## Features

- **Customizable Certificate Fields**: Input student name, certification number, date, and course name
- **Real-time Preview**: See changes instantly in the certificate preview
- **PDF Export**: Generate and download certificates as PDF files
- **Responsive Design**: Modern, gradient-styled form interface
- **Professional Layout**: Certificate includes logo, seal, signature, and issuer details

## Installation

1. Clone or download the project files to your local machine.
2. Ensure all required images are present in the `image/` folder:
   - `certificate.png` – Certificate background
   - `logo_dreamtree.jpeg` – Logo at the top
   - `seal1.png` – Seal graphic
   - `signature.png` – Signature image

## Usage

### Running the Application

To avoid CORS errors (tainted canvas issue), you must serve the project using a local server instead of opening the file directly in the browser.

**Option 1: Python HTTP Server (Recommended)**

For Python 3:
```bash
python -m http.server 8000
```

Then open your browser at: `http://localhost:8000/certificate.html`

**Option 2: VS Code Live Server Extension**

1. Install the Live Server extension in VS Code.
2. Right-click `certificate.html` → Open with Live Server.

### Generating a Certificate

1. Fill in the form fields:
   - Student Name
   - Certification Number
   - Date
   - Course Name
2. The certificate preview updates in real-time.
3. Click "Generate PDF" to download the certificate as a PDF file.

## Tech Stack

- **HTML/CSS** – UI and layout
- **JavaScript** – Dynamic updates and PDF generation
- **html2canvas** – Screenshot generation for PDF
- **jsPDF** – PDF creation and export

## Image Requirements

All images used in the certificate must be accessible with CORS enabled. The images are located in the `image/` folder and include `crossorigin="anonymous"` attributes in the HTML to ensure proper loading.

## Troubleshooting

### ❌ Error: Tainted Canvas
**Error Message:**
```
Uncaught (in promise) SecurityError: Failed to execute 'toDataURL' on 'HTMLCanvasElement': Tainted canvases may not be exported.
```

**✅ Solution:**
- Serve the project from a local server (not `file://`).
- Ensure `crossorigin="anonymous"` is added to all `<img>` tags.
- Keep `useCORS: true` enabled in html2canvas.

### ❌ Images Not Loading?
- Check if the `image/` folder path is correct.
- Ensure filenames match exactly (case-sensitive).
- Verify your server is running in the correct project directory.

## License

This project is free to use and modify for personal and educational purposes.
