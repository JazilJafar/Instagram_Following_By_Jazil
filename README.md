# Instagram Follow Checker

A simple, privacy-focused web tool to find out who doesn't follow you back on Instagram. Works 100% in your browser — no server, no data collection, completely private.

![Screenshot placeholder - Upload your files and instantly see who's not following back]

## Features

✨ **Find who doesn't follow you back** — instantly see which accounts you follow that don't follow you  
🤝 **See mutual followers** — view accounts that follow you back  
⭐ **Find your fans** — discover people who follow you but you don't follow back  
🔍 **Search and filter** — quickly find specific usernames  
📊 **Export to CSV** — download any list for safekeeping  
🔒 **100% private** — all processing happens locally in your browser  
🌙 **Dark mode support** — automatically adapts to your system theme  
📱 **Works on mobile** — responsive design for all screen sizes

## How to Use

### Step 1: Get Your Instagram Data

1. Open Instagram (mobile app or web)
2. Go to **Settings** → **Your activity** → **Download your information**
3. Select **Some of your information**
4. Check only **Followers and following**
5. Choose **Format: JSON** (not HTML)
6. Click **Create files**
7. Wait for Instagram to email you (usually 5-15 minutes)
8. Download the ZIP file from the email

### Step 2: Extract the Files

Open the ZIP file and find these two JSON files:
- `followers_1.json` (or `followers.json`)
- `following.json`

### Step 3: Upload and Analyze

1. Open `instagram_follow_checker.html` in any modern browser (Chrome, Firefox, Safari, Edge)
2. Drag and drop or click to upload both JSON files
3. Click **Analyze now →**
4. View your results instantly

## What You'll See

### Three Tabs

**👻 Not following back** — People you follow who don't follow you back (the "ghosts")  
**🤝 Mutual** — People who follow you and you follow them back  
**⭐ Only follow you** — Your fans — people who follow you but you don't follow back

### For Each Person

- Avatar with initials
- Username
- Quick link to their Instagram profile
- Export button to download the entire list as CSV

## Privacy & Security

- **No data is sent anywhere** — everything runs in your browser
- **No tracking or analytics** — completely anonymous
- **No account required** — just upload your files
- **No Instagram API** — uses only your own exported data
- Your files are never uploaded to any server

## Technical Details

### Browser Compatibility

Works in all modern browsers:
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

### File Format Support

Handles all known Instagram export formats:
- `string_list_data[].value` structure (most common)
- `title` field format (newer exports)
- Direct `value` field (older exports)
- Wrapped formats like `{"relationships_following": [...]}`

### How It Works

1. Reads both JSON files completely in your browser
2. Recursively searches for all username entries
3. Compares the two lists to find differences
4. Displays results in an interactive interface
5. All processing happens in JavaScript — zero server involvement

## Troubleshooting

### "Could not find any usernames"

- Make sure you downloaded **JSON format**, not HTML
- Check you selected **Followers and following** in the export options
- Verify the files are named `followers_1.json` and `following.json`

### Numbers seem wrong

- The debug line shows how many accounts were parsed from each file
- If you see "Parsed 0 followers" or "Parsed 0 following", you may have uploaded the wrong file
- Try re-downloading your Instagram data and selecting JSON format

### Missing known accounts

- Instagram's data export may have a slight delay (accounts followed/unfollowed in the last 24 hours might not appear)
- The tool normalizes usernames to lowercase for comparison
- Make sure both files are from the same data export request

## Export Data

Click **Export CSV** on any tab to download:
- Clean CSV file with one username per line
- Opens in Excel, Google Sheets, or any spreadsheet app
- Filename indicates which list: `instagram_not_following_back.csv`, `instagram_mutual.csv`, etc.

## FAQ

**Q: Is this against Instagram's terms of service?**  
A: No — you're using your own data export that Instagram officially provides. This tool doesn't access Instagram's API or scrape their website.

**Q: Can Instagram detect if I use this?**  
A: No — the tool runs entirely offline in your browser. Instagram has no way to know you're using it.

**Q: Will people know if I check who unfollowed me?**  
A: No — this is completely private. You're only reading your own data.

**Q: Why do I need to download my data? Can't you just access my account?**  
A: That would require your Instagram password, which would be a massive security risk. Using Instagram's official data export is the safe, private way.

**Q: How often should I download new data?**  
A: Whenever you want to check — there's no limit. Each export takes 5-15 minutes to generate.

**Q: Does this work for business/creator accounts?**  
A: Yes — it works for all Instagram account types.

## Credits

Built with:
- Vanilla JavaScript (no frameworks)
- [DM Sans](https://fonts.google.com/specimen/DM+Sans) and [Syne](https://fonts.google.com/specimen/Syne) fonts
- Love for privacy and simplicity

## License

This tool is provided as-is for personal use. Feel free to modify and share, but please keep it free and open.

---

**Made with ❤️ for people who just want to know who's not following them back**

No ads · No tracking · No accounts · No bullshit
