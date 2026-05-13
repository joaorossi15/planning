# Wedding Planner with Google Sheets

This version uses:

- `index.html` hosted on GitHub Pages
- Google Sheets as storage
- Google Apps Script as a tiny API

## 1. Create the Google Sheet backend

1. Create a new Google Sheet.
2. Go to **Extensions > Apps Script**.
3. Delete any existing code.
4. Paste the contents of `Code.gs`.
5. Change this line:

```js
const APP_PASSWORD = "change-this-password";
```

Use a password that only you and your fiancée know.

## 2. Deploy the Apps Script

In Apps Script:

1. Click **Deploy > New deployment**.
2. Select type: **Web app**.
3. Set:
   - **Execute as:** Me
   - **Who has access:** Anyone
4. Click **Deploy**.
5. Authorize the script.
6. Copy the Web app URL.

Google’s Apps Script docs explain that web apps use `doGet(e)` / `doPost(e)` functions and can return `TextOutput`, which is what this backend does.

## 3. Host the app on GitHub Pages

1. Rename `wedding-planner-sheets.html` to `index.html`.
2. Put it in your GitHub Pages repo.
3. Commit and push.
4. Open the site.
5. Paste the Apps Script Web App URL.
6. Enter the shared password.
7. Click **Save config**.
8. Click **Connect**.

## Important

This is fine for wedding planning, but do not store sensitive personal data, documents, CPF, addresses, or full contracts in it.
The password is not hardcoded into the public site, but the Apps Script endpoint is still a simple personal API, not a bank-grade authentication system.
