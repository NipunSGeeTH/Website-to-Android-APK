# Web-to-APK (Trusted Web Activity)

A simple, lightweight template to convert your website into a high-performance Android App using **Trusted Web Activity (TWA)**. Unlike a standard WebView, TWA provides better performance and full browser features while feeling like a native app.

## 📱 Live Demo
You can see this template in action with my personal website:
- **Website:** [https://nipunsgeeth.top](https://nipunsgeeth.top)
- **Sample APK:** [Download Sample APK](https://github.com/NipunSGeeTH/my-web-apk/releases/download/0.0.1v/nipunsgeeth.apk) *(Update this link after uploading your APK to GitHub Releases)*

## 🚀 Getting Started

Follow these steps to customize this project for your own website.

### 1. Prerequisites
- **Android Studio** (Latest version recommended)
- A website with a **Web App Manifest** and **Service Worker** (required for TWA to be compliant).
- Access to your website's server (to host the Digital Asset Links file).

### 2. Basic Configuration

#### Change the Website URL
Open `app/src/main/AndroidManifest.xml` and update the following fields:
- `android.support.customtabs.trusted.DEFAULT_URL`: Change `https://nipunsgeeth.top` to your website URL.
- `<data android:host="..." />`: Change `nipunsgeeth.top` to your domain name.

#### Change App Name
Open `app/src/main/res/values/strings.xml` and change the `app_name` string:
```xml
<string name="app_name">Your App Name</string>
```

#### Change Package Name (Application ID)
Open `app/build.gradle.kts` and update the `applicationId`:
```kotlin
defaultConfig {
    applicationId = "com.yourdomain.app"
    ...
}
```
*Note: If you change the package name, you should also update the folder structure in `app/src/main/java/` to match.*

### 3. Setup Digital Asset Links (Crucial)
To remove the browser URL bar and make the app feel native, you must verify ownership of your domain:
1. Generate a **Digital Asset Links** JSON file.
2. Place it on your server at: `https://yourdomain.com/.well-known/assetlinks.json`.
3. You can use the [Asset Links Tool](https://developer.android.com/training/app-links/verify-site-associations) or Android Studio's **App Links Assistant** to generate this.

### 4. Customizing App Icons
**Important:** Don't forget to replace the default Android icon with your own brand logo:
1. Right-click on the `app` folder in the Project view.
2. Select **New > Image Asset**.
3. For **Icon Type**, choose `Launcher Icons (Adaptive and Legacy)`.
4. In **Path**, select your logo image (PNG, SVG, or JPG).
5. Adjust the size using the slider and click **Next > Finish**.

### 5. Build Your APK
- Go to **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
- For production, use **Build > Generate Signed Bundle / APK**.

## 🛠 Tech Stack
- **Kotlin**
- **Android Browser Helper** (TWA)
- **Material 3**

## 📄 License
This project is open-source. Feel free to use it for your own projects!
