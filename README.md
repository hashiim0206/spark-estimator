# Spark Homes Repair Cost Estimator

A mobile-first, offline-capable Progressive Web App (PWA) built for real estate acquisition agents to walk through properties, estimate renovation costs in the field, and evaluate deal profitability.

This project was built from scratch as part of the Spark Homes Developer Contest.

## Key Features

- **Project Management**: Save, rename, switch, and delete multiple estimates. All project details are persisted offline in browser storage (IndexedDB and localStorage).
- **Comprehensive Pricing Checklist**: Over 110 items pre-loaded across 19 collapsible groups in 5 key sections (Interior, Kitchen, Bathrooms, Systems, Exterior).
- **Decoupled Room Configurations**: Flexible support for multiple rooms. Add or remove instances of rooms (Bathroom, Kitchen, Bedroom, Living/Common Areas, Systems, Exterior) with customized checklists specific to each room type.
- **Custom Price Overrides**: Edit item costs per-project or update pricing globally for all walkthroughs.
- **CSV Bulk Import**: Upload a spreadsheet (`Pricing List.csv`) in the Control Center panel to update standard pricing globally.
- **Running Total & Progress Tracking**: Real-time progress bar calculated per checklist group across all rooms.
- **Photo & Voice Logging**: Capture photos from the device camera (including automatic compression) and record audio voice memos for individual repair items.
- **Deal Analyzer (Creative Addition)**: An interactive profitability calculator that evaluates buy-in totals, holding/financing costs, and profit margins, displaying results on a capital allocation breakdown chart.
- **Excel ZIP Export**: Pack all checklist data into an formatted Excel sheet styled with borders and bold headers, zipped together with all inspection photos.

## Architecture & Libraries Used

The app is built as a **single self-contained HTML file** (`index.html`) using vanilla JavaScript, HTML5, and Tailwind CSS. It does not require any build tools, servers, or compiler setup.

The following client-side libraries are loaded via CDN:
- **Tailwind CSS (v3)**: Used for responsive, mobile-first utility classes.
- **xlsx-js-style**: To generate and style Excel spreadsheets locally.
- **JSZip**: To compress the generated Excel file and walkthrough photos into a single download.
- **python-docx (Python)**: Used locally to compile the technical project writeup Word document.

## How to Run Locally

Since this app is a single self-contained file with zero external runtime dependencies, it can be launched instantly:

1. **Double-click `index.html`** to open it directly in any web browser.
2. For the complete Progressive Web App (PWA) experience (including offline mode and installability):
   - Serve the directory using a simple local server (e.g., `python -m http.server 8000` or the VS Code Live Server extension).
   - Navigate to `http://localhost:8000` in Google Chrome or Safari.
   - Click the "Install App" icon in the address bar.

## Project Structure

```
├── index.html       # Single-file PWA (HTML, CSS, JS)
├── writeup.docx     # One-page technical writeup (Word Document)
├── README.md        # This file
```
