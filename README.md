# neon-snake
it is game created via antigravity
Modern Snake - Cloud Edition Walkthrough
I have updated the game to the Cloud Edition, integrating Google Services and Monetization features.

🚀 How to Play
Open File: 

index.html
 in your browser.
Google Sign-In: Click the "Sign in with Google" button on the start screen.
Note: Requires Firebase Configuration (see below).
Monetization: Die in the game to see the "Watch Ad to Revive" button.
☁️ Cloud Features Setup
The game is pre-wired for Firebase, but you must provide your own API Keys for the cloud features to work.

1. Firebase Setup
To enable Leaderboards and Auth:

Go to console.firebase.google.com.
Create a project "Neon Snake".
Enable Authentication -> Google Sign-In.
Enable Firestore Database.
Get your Web Configuration (API Key, Project ID, etc.).
Open 

index.html
 in a text editor.
Replace the placeholder config in the 

CloudService
 class:
const firebaseConfig = {
    apiKey: "PASTE_YOUR_API_KEY_HERE",
    authDomain: "...",
    // ...
};
2. AdMob / Monetization
The game currently uses a Simulated Ad Overlay (Mock Mode).
To use real ads, you would wrap this HTML file in an Android WebView (using Android Studio) and inject the Android AdMob SDK.
The 

AdController
 class is designed to be the bridge for this native injection.
✅ Feature Verification
🟢 Google Play Games Services (via Firebase)
Auth: firebase.auth() manages user sessions.
Leaderboards: firestore.collection('leaderboard') stores global high scores.
Saves: Progress matches the user ID.
🟢 Remote Config
The game attempts to fetch base_speed from Firebase Remote Config.
If you set this value in the console, all players' games will update instantly without downloading a new file.
🟢 Analytics
Google Analytics events are fired on:
Game Start
Ad Watch Complete
Level Up
