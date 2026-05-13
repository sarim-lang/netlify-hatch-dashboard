# Hatch Dashboard

Minimal Netlify dashboard for authenticated hatch control.

## Configure

Edit `config.js` before uploading to Netlify:

```js
window.APP_CONFIG = {
  API_BASE: "https://your-backend-domain.example.com"
};
```

## Backend

Run `proxy (2).py` from the parent folder with dashboard users configured:

```powershell
$env:DASHBOARD_USERS="admin:your-password"
python "..\proxy (2).py"
```

Only one active login is allowed by the backend. Set `SESSION_TTL_SECONDS=30` on Render for a 30-second session. Hatch requests use the backend command lock, so a second command receives `Robot is busy`.
