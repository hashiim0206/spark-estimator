# SparkGroup Repair Cost Estimator

A mobile-first, offline-capable Progressive Web App (PWA) built for real estate acquisition agents to walk through properties, estimate renovation costs in the field, and evaluate deal profitability.

## Key Features

- **Project Management**: Save, rename, switch, and delete multiple estimates. All project details are persisted offline in browser storage (IndexedDB and localStorage).
- **Comprehensive Pricing Checklist**: 109 items pre-loaded across 21 collapsible groups in 5 sections (Interior/General, Kitchen, Bathroom, Systems & Structure, Exterior).
- **Decoupled Room Configurations**: Flexible support for multiple rooms. Add or remove instances of rooms with customized checklists specific to each room type.
- **Custom Price Overrides**: Edit item costs per-project or update pricing globally for all walkthroughs.
- **CSV Bulk Import**: Upload a spreadsheet (`Pricing List.csv`) in the Control Center to update standard pricing globally.
- **Running Total & Progress Tracking**: Real-time progress bar calculated per checklist group across all rooms.
- **Photo & Voice Logging**: Capture photos from the device camera (including automatic compression) and record audio voice memos for individual repair items.
- **Deal Analyzer**: An interactive profitability calculator that evaluates buy-in totals, holding/financing costs, and profit margins, displaying results on a capital allocation breakdown chart.
- **Excel ZIP Export**: Pack all checklist data into a formatted Excel sheet styled with borders and bold headers, zipped together with all inspection photos.

## Architecture & Libraries Used

The app is built as a **single self-contained HTML file** (`index.html`) using vanilla JavaScript and HTML5 with custom CSS. It does not require any build tools, servers, or compiler setup.

The following client-side libraries are loaded via CDN:

- **xlsx-js-style**: To generate and style Excel spreadsheets locally.
- **JSZip**: To compress the generated Excel file and walkthrough photos into a single download.

## How to Run

**Option 1 — Live App (no setup required):**
Visit [spark-estimator-kappa.vercel.app](https://spark-estimator-kappa.vercel.app) directly in any browser on any device.

**Option 2 — Run Locally:**
Double-click `index.html` to open it directly in any web browser. No build tools, servers, or dependencies required.

## Project Structure

```
├── index.html       # Single-file PWA (HTML, CSS, JS)
├── vercel.json      # Vercel deployment configuration
├── README.md        # This file
```
