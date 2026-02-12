# 🎉 Valentine's Day App - Complete Setup Guide

## ✅ What You'll Have After This:
- ✨ Web app hosted on Netlify (free)
- 🔥 Firebase backend for saving images (free tier)
- 📱 Shareable links that work across different devices
- ❤️ Full valentine experience with photos, names, and answers

---

## 📋 Step 1: Create a Firebase Project (5 minutes)

### 1.1 Go to Firebase Console
- Visit: https://console.firebase.google.com/
- Click **"Add project"**
- Project name: `valentine-app` (or your choice)
- Click Continue → Continue → Continue → **Create Project**

### 1.2 Get Your Firebase Credentials
Once project is created:
1. Click the **Web icon** (the `</>` symbol) on the Firebase console
2. App nickname: `valentine-web`
3. Click **Register app**
4. **Copy the entire config object** (it looks like this):

```javascript
const firebaseConfig = {
    apiKey: "AIzaSy....",
    authDomain: "your-app.firebaseapp.com",
    databaseURL: "https://your-app-default-rtdb.firebaseio.com",
    projectId: "your-app",
    storageBucket: "your-app.appspot.com",
    messagingSenderId: "123456789",
    appId: "1:123456789:web:abcd1234"
};
```

### 1.3 Replace in index.html
- Open `index.html` in VS Code
- Find this line (around line 10):
```javascript
const firebaseConfig = {
    apiKey: "AIzaSyDemoKeyPleaseUpdateThis", // Replace with your API Key
    ...
};
```
- **Replace the entire `firebaseConfig` object** with your copied config
- **Save the file** (Ctrl + S)

### 1.4 Enable Realtime Database
In Firebase Console left sidebar:
1. Click **Realtime Database**
2. Click **Create Database**
3. Location: Choose closest to you
4. Start in **Test mode** (easier for now)
5. Click **Enable**

---

## 🚀 Step 2: Deploy to Netlify (3 minutes)

### 2.1 Prepare Files
Make sure you have these files in your project folder:
```
/project/murali/
├── index.html          ← Main file with updated Firebase config
├── SETUP_GUIDE.md      ← This file
└── (any other files)
```

### 2.2 Deploy to Netlify

**Option A: Drag & Drop (Easiest)**
1. Go to https://netlify.com
2. Sign up with **GitHub, Google, or Email**
3. On the dashboard, find **"Sites"** → **"Add new site"**
4. Click **"Deploy manually"**
5. **Drag your `index.html` file** into the drop area
6. Wait for it to upload ✅
7. You'll get a link like: `https://your-site-name.netlify.app`

**Option B: GitHub (Better)**
1. Create GitHub account: https://github.com
2. Create a new repository called `valentine-app`
3. Upload your `index.html` 
4. Go to Netlify → Connect GitHub → Select your repo
5. Click **Deploy site**

### 2.3 Your Live Website
After deployment, you'll have a live URL like:
```
https://your-site-name.netlify.app/index.html
```

✅ You can now share this URL with anyone!

---

## 💝 How to Use It

### Step 1: Sender's Setup
1. Open your Netlify link on your device
2. Click **"Personalize Message"** → Enter your crush's name
3. Click **"Add Your Photos"** → Upload 2 images
4. Images will save + Question appears: "Will you be my Valentine?"
5. Click **"Share with Friend"** → Link copied!
6. Send the link to your crush via WhatsApp, Messenger, SMS, etc.

### Step 2: Receiver's Response
1. Your crush opens the link on **their device**
2. They see:
   - ❤️ Personalized message with their name
   - 📸 Both your photos
   - ❓ "Will you be my Valentine?" question
3. They click:
   - **YES** → 🎆 Celebration + ❤️ Red heart shows
   - **NO** → 🤍 White heart shows
4. They see share options (can share further if said YES!)

---

## 🔍 Troubleshooting

### Problem: "Firebase not configured" warning
**Solution:** Update the Firebase config in `index.html` (Step 1.3)

### Problem: Link doesn't show images to friend
**Solution:** Make sure Firebase Realtime Database is enabled (Step 1.4)

### Problem: Netlify site shows blank page
**Solution:** 
1. Check browser console (F12 → Console tab)
2. Make sure `index.html` is uploaded

### Problem: Firebase errors in console
**Solution:** 
1. Check Firebase config is correctly copied
2. Make sure database rules allow reads/writes

---

## 🛡️ Security Note

Your Firebase project is set to **Test Mode** which allows anyone to read/write.
For production, you should update these rules:

**Go to Firebase Console → Realtime Database → Rules:**
Replace with:
```json
{
  "rules": {
    "valentines": {
      "$uid": {
        ".read": true,
        ".write": true,
        ".indexOn": ["timestamp"]
      }
    }
  }
}
```

---

## 📱 Testing Before Sending

1. Open your Netlify link
2. Test on both **desktop and mobile**
3. Personalize message + Add photos
4. Click Share → Copy link
5. Open in **different browser or incognito window**
6. Verify images load and you see the personalized message ✅
7. Test YES/NO answers
8. Check heart indicator appears ✅

---

## 🎁 Share Your Link!

Once everything works:
```
Send this to your crush:
https://your-site-name.netlify.app/index.html?name=YourName&sid=your-session-id
```

They'll see:
✨ Your personalized message
📸 Your uploaded photos
💝 Request to be your valentine

---

## 📞 Need Help?

**Firebase Issues:** https://firebase.google.com/docs
**Netlify Help:** https://docs.netlify.com
**VS Code Tips:** Use Ctrl+F to find/replace config

Enjoy your Valentine's app! 💕
