# Bulk Name → Phone Extractor

An Apify actor that searches CyberBackgroundChecks and extracts up to 5 phone numbers per person in bulk.

## Features

✅ **Bulk Processing** — Paste unlimited names, get results for all  
✅ **Phone Extraction** — Finds up to 5 phone numbers per person  
✅ **Clean Output** — Organized CSV/JSON/Excel exports  
✅ **Error Handling** — Gracefully skips failed lookups  
✅ **Fast** — Optimized for high-volume searches  

## Installation

### Option A: Deploy to Apify Console (Recommended)

1. Go to [Apify Console](https://console.apify.com)
2. Click **"Create new actor"** → Select **Node.js**
3. Copy the contents of `main.js` into the editor
4. Go to **"Input schema"** → Paste contents of `INPUT_SCHEMA.json`
5. Save and run!

### Option B: Clone This Repository

```bash
git clone https://github.com/Baetheape/bulk-name-phone-extractor.git
cd bulk-name-phone-extractor
npm install
