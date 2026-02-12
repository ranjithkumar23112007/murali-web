# 🔥 Firebase Configuration - Step By Step

Follow these exact steps to get your Firebase credentials.

---

## 1. Open Firebase Console
```
👉 Go to: https://console.firebase.google.com/
   (Sign in with Google if prompted)
```

## 2. Create New Project
- Click: **"Add project"**
- Project name: `valentine-app`
- [Continue] → [Continue] → [Continue] → **[Create project]**
- Wait for it to load (might take 30 seconds)

## 3. Create Web App
- Click the **Web icon** (looks like `</>`)
- App nickname: `valentine-web`
- Click: **[Register app]**

## 4. Copy Your Config
You'll see a code snippet that looks like:

```javascript
import { initializeApp } from "firebase/app";

const firebaseConfig = {
  apiKey: "AIzaSyDKEXAMPLE1234567890...",
  authDomain: "valentine-app-xxxxx.firebaseapp.com",
  projectId: "valentine-app-xxxxx",
  storageBucket: "valentine-app-xxxxx.appspot.com",
  messagingSenderId: "123456789012",
  appId: "1:123456789012:web:abcde1234567890abcde"
};

const app = initializeApp(firebaseConfig);
```

## 5. Copy ONLY the firebaseConfig part

**Copy this:**
```javascript
{
  apiKey: "AIzaSyDKEXAMPLE...",
  authDomain: "valentine-app-xxxxx.firebaseapp.com",
  projectId: "valentine-app-xxxxx",
  storageBucket: "valentine-app-xxxxx.appspot.com",
  messagingSenderId: "123456789012",
  appId: "1:123456789012:web:abcde1234567890"
}
```

**NOT this:**
```javascript
const firebaseConfig = {
  ...
};
```

(Just the object contents without the variable declaration)

---

## 6. Update index.html

1. **Open** `index.html` in VS Code
2. Find this section (around line 10):
```javascript
const firebaseConfig = {
    apiKey: "AIzaSyDemoKeyPleaseUpdateThis",
    authDomain: "your-project.firebaseapp.com",
    databaseURL: "https://your-project-default-rtdb.firebaseio.com",
    projectId: "your-project-id",
    storageBucket: "your-project.appspot.com",
    messagingSenderId: "123456789",
    appId: "1:123456789:web:abcdef123456"
};
```

3. **Replace it with your copied config:**
```javascript
const firebaseConfig = {
    apiKey: "AIzaSyDKEXAMPLE1234567890...",
    authDomain: "valentine-app-xxxxx.firebaseapp.com",
    projectId: "valentine-app-xxxxx",
    storageBucket: "valentine-app-xxxxx.appspot.com",
    messagingSenderId: "123456789012",
    appId: "1:123456789012:web:abcde1234567890abcde"
};
```

4. **Save** (Ctrl + S)

---

## 7. Enable Realtime Database

Back in Firebase Console:

1. **Left sidebar** → Click **"Realtime Database"**
2. Click: **[Create Database]**
3. Location: Pick closest to your location
4. Security rules: **Start in test mode** (for now)
5. Click: **[Enable]**

✅ Your database is ready!

---

## ✅ You're Done with Firebase!

You now have:
- ✅ Firebase project created
- ✅ Credentials updated in index.html
- ✅ Realtime Database enabled
- ✅ Ready to deploy

**Next step:** Deploy to Netlify (see SETUP_GUIDE.md)

---

## 🔍 Verify Your Config

You should see this in Firebase Console:
- **Project ID:** valentine-app-xxxxx
- **Database URL:** https://valentine-app-xxxxx-default-rtdb.firebaseio.com
- **Storage bucket:** valentine-app-xxxxx.appspot.com

These should match what you put in `index.html`!

---

## ⚠️ Common Mistakes

❌ **Forgot to replace the config?**
   → App will show warning: "Firebase not configured"
   → Fix: Copy new config values into index.html

❌ **Didn't enable Realtime Database?**
   → Images won't save when shared
   → Fix: Go to Firebase Console → Realtime Database → Enable

❌ **Left demo values in config?**
   → Firebase errors in browser console
   → Fix: Make sure ALL values are from YOUR project, not the example

---

## 🚀 Next: Deploy to Netlify

See **QUICK_START.txt** for next steps!
