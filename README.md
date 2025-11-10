# DineTime

A full-featured **React Native** app built for both **Android** and **iOS** that allows users to explore restaurants, browse carousel images, book dining slots, place orders, and manage their accounts with Firebase Authentication.

---

## 🍽️ Overview
**DineTime** is a cross-platform restaurant booking and ordering app that lets users:
- Sign up or log in with Firebase Authentication
- View restaurants with carousel-style image galleries
- Book available dining slots in real-time
- Place and manage food orders
- Seamlessly use the app on Android and iOS devices

Built using React Native (Expo) and Firebase for a smooth, cloud-connected experience.

---

## 🧠 Features
- 🔐 **Authentication:** Firebase email/password login and signup  
- 🏙️ **Restaurant Carousel:** Scrollable restaurant showcase with images  
- 📅 **Slot Booking:** Select available dining slots and confirm reservations  
- 🍔 **Food Ordering:** View menu, add to cart, and place orders  
- ☁️ **Cloud Database:** Firebase Firestore for real-time updates  
- 📱 **Cross-platform:** Works on both Android and iOS using Expo  
- 💾 **Persistent Data:** User sessions and orders stored securely in Firebase  

---

## 🛠️ Tech Stack
| Category | Technology |
|-----------|-------------|
| Framework | React Native (Expo) |
| Backend | Firebase |
| Auth | Firebase Authentication |
| Database | Firestore |
| Image Storage | Firebase Storage |
| State Management | Context API / Redux (optional) |
| UI Library | React Native Paper / Tailwind / NativeWind |
| Platform Support | Android & iOS |

---

## 📂 Project Structure
DineTime/
├── app/
│ ├── screens/
│ │ ├── LoginScreen.js
│ │ ├── SignupScreen.js
│ │ ├── HomeScreen.js
│ │ ├── RestaurantScreen.js
│ │ └── BookingScreen.js
│ ├── components/
│ │ ├── Carousel.js
│ │ ├── SlotCard.js
│ │ ├── OrderCard.js
│ │ └── Button.js
│ ├── config/
│ │ └── firebaseConfig.js
│ ├── store/
│ │ └── context.js
│ ├── utils/
│ │ └── helpers.js
│ └── App.js
├── assets/
│ ├── images/
│ └── icons/
├── package.json
├── app.json
├── babel.config.js
└── README.md

yaml
Copy code

---

## ⚙️ Setup & Installation

### 1. Clone the repository
```bash
git clone <your-repo-url>
cd DineTime
2. Install dependencies
bash
Copy code
npm install
# or
yarn install
3. Configure Firebase
Go to Firebase Console

Create a new project named DineTime

Enable Authentication, Firestore, and Storage

Get your Firebase config and add it to config/firebaseConfig.js:

js
Copy code
import { initializeApp } from "firebase/app";
import { getAuth } from "firebase/auth";
import { getFirestore } from "firebase/firestore";
import { getStorage } from "firebase/storage";

const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_AUTH_DOMAIN",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_STORAGE_BUCKET",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID"
};

const app = initializeApp(firebaseConfig);
export const auth = getAuth(app);
export const db = getFirestore(app);
export const storage = getStorage(app);
4. Run the App
Using Expo CLI:
bash
Copy code
npx expo start
Press a to run on Android emulator/device

Press i to run on iOS simulator (Mac required)

Or scan the QR code with the Expo Go app

🔑 Firebase Authentication Flow
Signup: Create a new user with email & password

Login: Authenticate existing user

Logout: Clear session and navigate back to login screen

Firestore: Store user data, bookings, and order history

🧩 Example Firestore Collections
css
Copy code
users/
  userId/
    name
    email
    bookings/
restaurants/
  restaurantId/
    name
    images[]
    slots[]
    menu[]
orders/
  orderId/
    userId
    restaurantId
    items[]
    total
📱 Screens
Login & Signup – Firebase Auth integration

Home – Carousel of restaurants

Restaurant Details – Menu, available slots

Booking – Select date/time and confirm

Orders – View placed orders

🚀 Deployment (Production Build)
To create standalone builds:

bash
Copy code
eas build --platform android
eas build --platform ios

# 🧾 License
This project is open-source under the MIT License.
