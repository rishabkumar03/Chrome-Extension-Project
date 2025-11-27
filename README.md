# Chrome-Extension-Project

A simple and efficient Chrome Extension for saving URLs and notes directly from your browser. It allows users to store input links, save the current tab's URL, persist data using localStorage, and manage saved items with an easy-to-use interface.

## Features

- **Save Input Links:** Manually enter any URL or text and save it instantly
- **Save Active Tab:** One-click save for the currently active browser tab
- **Delete All:** Removes all saved data, triggered by double-click for safety
- **Persistent Storage:** Uses localStorage to keep leads even after browser restart
- **Clickable Link List:** Saved URLs appear as clickable links
- **Simple and Fast UI:** Lightweight popup with quick interactions

## Technologies Used

### Frontend

- HTML5
- CSS3
- JavaScript (ES6+)

### Extension APIs

- Chrome Tabs API
- Chrome Action Popup
- localStorage API

## Installation

1. Download or clone this repository
2. Open Chrome and go to:
    ```arduino
    chrome://extensions/
    ```
3. Enable **Developer Mode** in the top-right
4. Click **Load unpacked**
5. Select your project folder
6. Your extension is now added to Chrome!

## File Structure

```
chrome-extension-project/
├── README.md
├── chrome.css
├── chrome.js
├── icon.png
├── index.html
└── manifest.json
```

## How It Works

1. User clicks on the extension icon to open the popup
2. They can:
    - Enter text and save it
    - Save the current browser tab’s URL
    - Double-click the delete button to remove all saved leads
3. All leads are displayed as a linked list below
4. Data is saved in `localStorage` for persistence

## Configuration

### Chrome Tabs API Usage

The extension uses:

```js
chrome.tabs.query({ active: true, currentWindow: true })
```

to fetch the URL of the currently opened tab.

### Local Storage

Leads are stored using:

```js
localStorage.setItem("myLeads", JSON.stringify(myLeads))
```

## Known Issues

1. **Not Working on Chrome Mobile**

    Chrome Extensions are not supported on mobile devices.

2. **Requires Manifest File**

    Ensure a valid `manifest.json` exists, otherwise the extension won't load.

3. **LocalStorage Limitations**

    Large data storage may exceed browser limits.

## Troubleshooting

### Extension Not Working
- Ensure Developer Mode is enabled
- Reload the extension after changes
- Check Console errors in popup (Right-click → Inspect popup)

### URLs Not Saving
- Make sure Chrome has permission to access tabs
- Verify your manifest contains "tabs" permission

### Leads Not Showing
- Confirm valid JSON format in localStorage
- Check for typos in element IDs in HTML

## Security Considerations
- Data is stored locally on user’s device
- No external servers or databases are used
- Avoid storing sensitive or personal information

## Contributing
1. Fork the repository
2. Create a new branch (`git checkout -b feature-name`)
3. Make your changes
4. Commit your changes (`git commit -m 'Add some feature'`)
5. Push to the branch (`git push origin feature-name`)
6. Open a Pull Request