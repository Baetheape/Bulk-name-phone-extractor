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
```

## Usage

### Step 1: Prepare Your Input

Paste names into the input box (one per line):

```
John Doe
Maria Hernandez
James Carter
Robert Wilson
```

### Step 2: Run the Actor

Click **"Start"** in the Apify console.

### Step 3: Export Results

Go to **Dataset** → Download as CSV, JSON, or Excel

## Output Format

| first_name | last_name  | phone_1      | phone_2      | phone_3 | phone_4 | phone_5 |
|------------|-----------|--------------|--------------|---------|---------|----------|
| John       | Doe       | 5551234567   | 5559876543   | NULL    | NULL    | NULL    |
| Maria      | Hernandez | 5552223333   | NULL         | NULL    | NULL    | NULL    |
| James      | Carter    | NULL         | NULL         | NULL    | NULL    | NULL    |
| Robert     | Wilson    | 5554445555   | 5556667777   | 5558889999 | NULL  | NULL    |

## How It Works

1. **Parse Input** — Splits bulk names into an array
2. **Search** — Queries CyberBackgroundChecks for each name
3. **Extract Profile** — Visits the first result and scrapes the profile page
4. **Parse Phone Numbers** — Finds all `tel:` links and extracts digits
5. **Push Data** — Outputs results to the Apify dataset

## API & Rate Limits

- **No API key required** — Uses public CyberBackgroundChecks searches
- **Rate Limiting** — Respects site rate limits with built-in delays
- **Timeouts** — 30-second timeout per request
- **Retries** — Automatic retry on network failures

## Troubleshooting

### No Results Found

- Name might not exist in CyberBackgroundChecks
- Site structure may have changed (update selectors in code)
- Person has no phone numbers listed

### Rate Limited?

Increase delays between requests or run smaller batches.

### Selector Not Finding Data?

CyberBackgroundChecks may have updated their HTML. Update the CSS selectors:

```javascript
// In extractPhones() function:
$('a[href^="tel:"]') // Update this selector
```

## License

MIT

## Contributing

Feel free to open issues or submit pull requests!
