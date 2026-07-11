# Technical Architecture & Implementation Report
**Submission Project: Spark Estimator & Real Estate Deal Analyzer**

---

## 1. Most Interesting Design / UX Decision

### Indented Cards with Wide Tap Targets
Designing for construction sites means users are walking around holding their phones in one hand. Standard small checkboxes are hard to tap, so I made the entire top header of the item card clickable. When tapped, the card expands and shifts the quantity boxes, photos, and notes to the right by 40 pixels. This simple indentation keeps the edit fields separate from the selection headers, making it easy to tap card headers without accidentally editing the inputs.

---

## 2. What's Broken or Fragile

### First Boot Network Dependency
The app depends on SheetJS and JSZip loaded from a CDN to build Excel sheets and compress files into a ZIP. I set up a Service Worker to cache these files for offline use. However, if a user opens the app for the very first time in a basement with zero cell service, the export buttons will fail because the app hasn't had a chance to download and cache those libraries yet. I added a warning to explain that they need a brief internet connection on the first boot.

---

## 3. Creative Addition: Real Estate Deal Analyzer

### On-Site Profit Analysis
Estimating repair costs is only useful if it helps determine the profitability of a property. I added a Deal Analyzer that uses the repair estimate to calculate the final profit margin, ROI, and closing/holding costs. This lets real estate agents run all their calculations in one place on their phone, so they can decide if a property is a good investment right during the site walkthrough.

---

## 4. Next Shipments (With 2 More Days)

### Offline Independence & Camera Detection
First, I would bundle the SheetJS and JSZip libraries directly into the single HTML file using base64. This would make the first load 100% offline-friendly without any CDN dependency. Second, I would add a simple computer vision feature using the phone camera to detect wall damage or room dimensions and auto-fill the measurements in the estimator.

---

## 5. The Role of Generative AI

### Testing and Verification Support
AI helped me build the app by checking edge cases in the CSV parser, helping set up the PWA caching logic, and writing unit tests. It acted like an experienced classmate who helped debug my functions and verify that the math calculations were accurate.
