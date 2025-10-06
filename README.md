# 🌐 Social Connect

A modern **social media mobile application** built using **React (Ionic + Firebase)** that allows users to **connect, post, like, comment, and receive notifications** in real time.  
This project was developed as part of the **Mobile App Development Internship Task** and demonstrates a full-featured mini social network.

---
## 🚀 Overview

**Social Connect** provides a clean, intuitive social experience — from signing up and setting up your profile to creating posts, liking, commenting, and receiving notifications.  
It is optimized for smooth navigation, responsive UI, and real-time updates.

---

## 🧩 Core Features

### 🔑 Authentication
- Sign Up, Login, and Forgot Password screens  
- **Firebase Authentication** (using **Emulator Suite**)  
- Secure validation using **Formik + Yup**

### 👤 Profile Management
- Create and edit profile:
  - Name  
  - Bio  
  - Profile Picture Upload (via local image picker)  
- View own and other users' profiles

### 📰 Post System
- Create, edit, and delete posts  
- Optional image attachments  
- Real-time timestamps  
- Display feed in scrollable vertical layout

### ❤️ Likes & 💬 Comments
- Like and unlike posts instantly  
- Add and view comments  
- Comment count display  
- Real-time updates for likes/comments

### 🔔 Notifications
- Real-time notifications when someone likes/comments  
- Implemented via **local notification logic** (mocked FCM)

### 🧠 State Management
- Global app state managed with **React Context API / Redux Toolkit**

### 🧭 Navigation
- Built using **Ionic React Router** with:
  - Home
  - Profile
  - Explore
  - Notifications
  - Settings

### 💫 UI & UX
- Minimal and consistent design using Ionic  
- Fixed header padding (no overlap with mobile status bar)  
- Optimized for both Android & iOS  
- Smooth animations using Ionic transitions  

---

## 🛠️ Tech Stack

| Category | Technology |
|-----------|-------------|
| **Frontend** | React (Ionic Framework) |
| **Backend / Database** | Firebase (with Emulator Suite) |
| **Notifications** | Local mock notifications / FCM setup |
| **State Management** | React Context API / Redux Toolkit |
| **Validation** | Formik + Yup |
| **Styling** | Ionic Components + Custom CSS |
| **Image Handling** | Capacitor Camera / react-native-image-picker |
| **Development Platform** | Firebase Emulator Suite (Free Alternative) |

---

## 💰 Why Firebase Emulator Suite?

Firebase Storage and advanced features require billing activation on real Firebase projects.  
To keep this project **100% free and local**, the app is integrated with the **Firebase Emulator Suite**, which replicates:

- **Authentication**
- **Firestore Database**
- **Storage**
- **Hosting**

Everything works locally, so you can **develop and test without any paid Firebase plan.**

---

## ⚙️ Setting Up & Running the Project

### 1️⃣ Clone Repository
```bash
git clone https://github.com/your-username/social-connect.git
cd social-connect
```

### 2️⃣ Install Dependencies
```bash
npm install
```

### 3️⃣ Setup Firebase (Local Emulator)
You can use the Firebase Emulator Suite instead of connecting to a paid Firebase backend.

#### 🔧 Step 1: Install Firebase CLI
```bash
npm install -g firebase-tools
```

#### 🔧 Step 2: Initialize Firebase in your project
```bash
firebase init
```
Select:
- **Emulators**
- Choose: Authentication, Firestore, Storage  
- Then choose default ports or custom if needed.

#### 🔧 Step 3: Start Emulator
```bash
firebase emulators:start
```

This runs:
- Auth Emulator → `localhost:9099`  
- Firestore Emulator → `localhost:8080`  
- Storage Emulator → `localhost:9199`

Your app will now communicate with these local services.

> 💡 Make sure you have a Firebase configuration in `src/lib/firebase.ts` that points to your local emulator when developing.

Example:
```ts
import { initializeApp } from "firebase/app";
import { getAuth, connectAuthEmulator } from "firebase/auth";
import { getFirestore, connectFirestoreEmulator } from "firebase/firestore";
import { getStorage, connectStorageEmulator } from "firebase/storage";

const firebaseConfig = {
  apiKey: "fake-api-key",
  authDomain: "localhost",
  projectId: "social-connect",
  storageBucket: "social-connect.appspot.com",
};

const app = initializeApp(firebaseConfig);
const auth = getAuth(app);
const db = getFirestore(app);
const storage = getStorage(app);

if (window.location.hostname === "localhost") {
  connectAuthEmulator(auth, "http://localhost:9099");
  connectFirestoreEmulator(db, "localhost", 8080);
  connectStorageEmulator(storage, "localhost", 9199);
}

export { app, auth, db, storage };
```

---

### 4️⃣ Run the App
Run in your browser (Ionic server):
```bash
ionic serve
```

Run on Android/iOS emulator:
```bash
ionic capacitor run android
ionic capacitor run ios
```

## 🧪 Testing & Debugging

- All core features tested on Android Emulator  
- Firebase Emulator handles all local data  
- Fixed header overlap issue  
- Improved app performance and reduced re-renders  
- Error handling included for all Firebase operations  

---

## 🎥 Submission Requirements (Internship)

- **Video Demo:** Short video showing key app features  
- **GitHub Repo:** Public repository with complete source code  


---

## 👨‍💻 Contributing

1. Fork this repo  
2. Create a new branch (`feature/new-feature`)  
3. Commit and push your changes  
4. Submit a Pull Request  

---

## 📜 License

This project is created for **educational and internship purposes** under the **Social Connect Internship Task**.  
You are free to fork and modify it for personal use or learning.

---

## 💬 Author

**👩‍💻 Developer:** *Sawaira Tanveer*  
📧 **Email:** [sawairatanveer10@gmail.com]  
🌐 **GitHub:** 
