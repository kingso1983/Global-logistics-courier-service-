# GLOBAL Logistics Service — Real Website

Professional courier & logistics website ready for **GitHub Pages + Firebase**.

## Features

- Modern responsive design
- 9 languages (English, Spanish, French, German, Portuguese, Arabic RTL, Chinese, Hindi, Russian)
- **Pricing section** with Standard / Express / International packages
- **Request a Quote** form → opens WhatsApp with pre-filled details
- Real parcel tracking (Firebase Firestore)
- Secure Admin panel (Firebase Authentication)
- Generate tracking codes, update status, delete shipments
- Contact via Email, Phone, WhatsApp
- Ready for free GitHub Pages hosting + custom domain

---

## 🚀 Launch in 5 Steps

### Step 1 — Create free Firebase project

1. Go to https://console.firebase.google.com
2. Create a project (any name)
3. Add a **Web app** → copy the `firebaseConfig` object
4. **Authentication** → Sign-in method → Enable **Email/Password**
5. **Authentication** → Users → Add user (this will be your Admin login)
6. **Firestore Database** → Create database → Start in **test mode** → Enable

### Step 2 — Add your Firebase keys

Open `js/firebase-config.js` and replace the placeholder values with your real keys from Step 1.

### Step 3 — Upload to GitHub

1. Create a new repository on GitHub (Public)
2. Upload **all files** from this folder
3. Go to **Settings → Pages**
4. Source: Deploy from a branch → `main` → `/ (root)` → Save
5. Your site will be live at:  
   `https://YOUR-USERNAME.github.io/REPOSITORY-NAME/`

### Step 4 — Secure Firestore rules

In Firebase → Firestore → Rules, paste this and Publish:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /shipments/{doc} {
      allow read: if true;
      allow write: if request.auth != null;
    }
  }
}
```

### Step 5 — Test

1. Open your live site
2. Go to **Admin** → Login with the email/password you created
3. Add a shipment → copy the tracking code
4. On the main site → Track page → paste the code

---

## 🌐 Custom Domain (Optional)

1. Buy a domain (Namecheap, GoDaddy, Google Domains, etc.)
2. In GitHub → your repo → **Settings → Pages**
3. Under “Custom domain” type your domain (e.g. `globallogistics.com`) → Save
4. GitHub will show the DNS records you need (usually A records or CNAME)
5. In your domain registrar, add the DNS records GitHub shows
6. Wait 5–30 minutes (sometimes up to 24h) for DNS to update
7. Enable “Enforce HTTPS” when it becomes available

Example CNAME setup (common):
- Type: CNAME
- Host: www (or @)
- Value: `YOUR-USERNAME.github.io`

---

## Contact details already set

- Email: globallogistic@fastservice.com
- Phone: +1 518 416 8768
- WhatsApp: https://wa.me/15184168768

---

## File Structure

```
├── index.html              ← Main public website
├── admin.html              ← Admin panel
├── css/styles.css
├── js/
│   ├── firebase-config.js  ← PUT YOUR FIREBASE KEYS HERE
│   ├── translations.js
│   ├── main.js
│   └── admin.js
├── assets/logo.svg
└── README.md
```

---

## Need help?

Most common issues:
1. Forgot to replace Firebase keys in `js/firebase-config.js`
2. Forgot to enable Email/Password authentication
3. Forgot to create an Admin user in Firebase
4. GitHub Pages still building (wait 1–2 minutes)

Your real courier website is ready to launch!
