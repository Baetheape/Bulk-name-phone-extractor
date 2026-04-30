# Step-by-Step Setup Guide

## Deploy to Apify Console

### Prerequisites

- [Apify Account](https://console.apify.com) (free)
- Web browser

### Steps

#### 1. Create a New Actor

1. Go to https://console.apify.com
2. Click the **"+" button** or **"Create new actor"**
3. Select **"Node.js"** as the template
4. Click **"Create"**

#### 2. Add the Main Code

1. You'll see the editor with some default code
2. **Delete all the default code**
3. Copy the entire contents of `main.js` from this repo
4. Paste it into the editor
5. Click **"Save"**

#### 3. Set Up the Input Schema

1. Click the **"Input schema"** tab (next to the Code tab)
2. Delete the existing schema
3. Copy the entire contents of `INPUT_SCHEMA.json` from this repo
4. Paste it into the Input schema editor
5. Click **"Save"**

#### 4. Test with Sample Data

1. Go back to the **"Code"** tab
2. Click **"Start"** (or the play button)
3. A modal will appear asking for input
4. Paste sample names:
   ```
   John Doe
   Maria Hernandez
   James Carter
   ```
5. Click **"Start"**

#### 5. View Results

1. Wait for the actor to finish
2. Click the **"Dataset"** tab at the bottom
3. You'll see extracted data:
   - `first_name`
   - `last_name`
   - `phone_1` through `phone_5`

#### 6. Export Results

1. In the **"Dataset"** tab, click **"Download"**
2. Choose format:
   - **CSV** (for Excel)
   - **JSON** (for APIs)
   - **Excel** (XLSX)
3. Save the file

## Optional: Set Up Notifications

After the actor finishes, get notified via:

1. Go to **Settings**
2. Enable **Email notifications** or **Webhook**
3. Save

## Optional: Schedule Recurring Runs

1. Go to **Settings**
2. Click **"Schedule"**
3. Choose frequency (Daily, Weekly, Monthly)
4. Save

## Troubleshooting

### "Module not found: apify"

- Dependencies should auto-install. If not:
  - Click **Settings** → **Dependencies**
  - Ensure `apify` and `cheerio` are listed

### "No data in dataset"

- Names might not exist in CyberBackgroundChecks
- Try common names: "John Smith", "Jane Doe"
- Check the **Logs** tab for errors

### Actor keeps timing out

- Too many names at once? Try smaller batches (10-20 names)
- Add delays between requests in the code

## Need Help?

- Check [Apify Docs](https://docs.apify.com/)
- Review the [actor tutorial](https://docs.apify.com/actors/quick-start)
