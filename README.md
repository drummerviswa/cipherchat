# CipherChat - End-to-End Encrypted Messenger

## 🔒 Overview
CipherChat provides a **fully encrypted chat experience** using AES-256 encryption, ensuring privacy and security for user conversations. Messages are **end-to-end encrypted**, stored securely on the device, and can be **self-destructed** for extra protection.

## 📌 Features
✅ **End-to-End Encryption** using AES-256  
✅ **Local Message Encryption** (no plaintext storage)  
✅ **Self-Destructing Messages** for extra privacy  
✅ **Biometric Authentication** (FaceID / TouchID)  
✅ **Steganography Support** (hide messages in images)  
✅ **Peer-to-Peer Messaging** (optional, without servers)  

## 🛠 Tech Stack
- **Frontend:** React Native (Expo or CLI)
- **Encryption:** `crypto-js`, `react-native-crypto`
- **Backend:** Firebase or Node.js + Express
- **Database:** Firebase Firestore / SQLite
- **Authentication:** Firebase Auth / JWT-based auth

## 🚀 Getting Started
### 1️⃣ Clone the Repository
```sh
git clone https://github.com/drummerviswa/cipherchat.git
cd cipherchat
```

### 2️⃣ Install Dependencies
```sh
yarn install   # or npm install
```

### 3️⃣ Set Up Firebase (if using Firebase Backend)
- Create a Firebase project.
- Enable Firestore Database.
- Enable Firebase Authentication (Google, Email/Password).
- Copy Firebase Config into `config/firebase.js`.

### 4️⃣ Run the App
```sh
expo start   # If using Expo
npx react-native run-android   # For Android
npx react-native run-ios       # For iOS
```

## 🔐 Security Implementation
### AES-256 Encryption for Messages
```js
import CryptoJS from 'crypto-js';

const encryptMessage = (message, key) => {
  return CryptoJS.AES.encrypt(message, key).toString();
};

const decryptMessage = (encryptedMessage, key) => {
  const bytes = CryptoJS.AES.decrypt(encryptedMessage, key);
  return bytes.toString(CryptoJS.enc.Utf8);
};
```

### Firebase Firestore Security Rules (Example)
```json
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /chats/{chatId} {
      allow read, write: if request.auth != null;
    }
  }
}
```

## 🚀 Future Enhancements
🔹 Implement **decentralized messaging (P2P, WebRTC)**  
🔹 Support **multi-device sync with encrypted backups**  
🔹 AI-based **phishing & spam detection for messages**  
🔹 QR-code based **key exchange** for secure chats  

## 🤝 Contributing
Feel free to fork, open issues, or submit pull requests to enhance this project! 🎉

## 📜 License
MIT License © 2025 Viswanathan P / drummerviswa