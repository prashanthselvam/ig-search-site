# Chrome Web Store Listing Content

Use this file as a reference when filling out the Chrome Web Store Developer Dashboard.

---

## Short Description (manifest, 132 chars max)

```
Search posts on any Instagram profile by caption text.
```

This is already in your manifest.json `description` field.

---

## Detailed Description (store listing)

```
IG Search lets you search through posts on any Instagram profile by caption text — so you can finally find that recipe, quote, or recommendation without scrolling through hundreds of posts.

HOW IT WORKS
1. Visit any Instagram profile
2. Click the IG Search icon in the top-right corner
3. Click "Load Posts" — the page scrolls automatically and saves all posts to your browser
4. Type any keyword to instantly find matching posts

KEY FEATURES
- Search by caption text across any profile
- Save and search multiple profiles
- Search across all your saved profiles at once
- Posts and Tagged tabs supported
- Pinned posts stay at the top, just like on Instagram
- Expand the panel for a larger view
- Works in both dark and light mode

PRIVACY FIRST
All data stays on your device. Nothing is ever sent to any server. No accounts, no sign-ups, no tracking, no analytics. You can clear your data at any time from within the extension.
```

---

## Category

```
Productivity
```

---

## Single Purpose Statement (privacy tab)

```
Enables keyword search across posts on Instagram profiles by capturing and storing post data locally in the browser.
```

---

## Permission Justifications (privacy tab)

### storage
```
Used to save post data (captions, thumbnails, timestamps) locally on the user's device via chrome.storage.local so that posts can be searched without re-loading. No data is transmitted externally.
```

### activeTab
```
Used to interact with the currently active Instagram tab when the user invokes the extension, ensuring the extension only operates on the page the user is actively viewing.
```

### Host permission: https://*.instagram.com/*
```
Required to inject the search panel UI and content script into Instagram pages. The permission is scoped narrowly to only instagram.com domains to enable the extension's core search functionality.
```

### MAIN world content script
```
A content script runs in the MAIN world at document_start to intercept Instagram's fetch/XHR API responses. This is necessary because Instagram loads post data via JavaScript API calls that are not accessible from the isolated content script world. The intercepted data (post captions, thumbnails, timestamps) is stored locally and never transmitted externally.
```

---

## Data Use Certification Checkboxes

When filling out the "Privacy practices" tab, here's how to answer:

**Does your extension collect or use any user data?**
→ Yes

**What data types does it collect?**
→ "Website content" (post captions, thumbnails from instagram.com)

**How is this data used?**
→ Check ONLY: "Functionality" — the extension needs this data to provide its search feature

**Is the data transferred to third parties?**
→ No

**Is the data sold to third parties?**
→ No

---

## Privacy Policy URL

Point this to wherever you host the landing page:
```
https://YOUR-DOMAIN/privacy.html
```

---

## Screenshots Checklist

You need to take these yourself (1280x800 px, JPEG or PNG):

1. **The search panel open on a profile page** — showing search results with highlighted terms
2. **The "Load Posts" flow** — panel open with progress bar visible during loading
3. **All Profiles view** — showing multiple saved profile cards
4. **Cross-profile search** — global search results showing posts from different profiles
5. **The help modal** — showing the "How to use" overlay

Tip: Use Chrome DevTools device toolbar to get an exact 1280x800 viewport, then take a full-page screenshot.

---

## Small Promotional Tile (440x280 px)

Create a simple graphic with:
- "IG Search" text
- A search icon or magnifying glass
- Tagline: "Search Instagram posts by caption"
- Use the brand purple (#5b51d8) as background
