# Flutter Android Setup Without Android Studio
**Windows**

## 📥 Download the Tools
1. Download **Command Line Tools** from the [official Android website](https://developer.android.com/studio)
2. Scroll to the bottom of the page, where you'll find **"Command line tools only"**

## 📁 Create Folder Structure
Create a folder for Android SDK (example for Windows):
```
C:\progs\android_sdk
```

**Important:** Do not use folders with special access permissions (e.g., "Program Files")

## 🗂️ Extract the Tools
Extract `commandlinetools-win-13114758_latest.zip` into the folder `C:\progs\android_sdk`

You should have the following structure: `C:\progs\android_sdk\cmdline-tools`

## ⚙️ Install Packages
Open Command Prompt and execute:

```cmd
# Navigate to the sdkmanager folder
cd C:\progs\android_sdk\cmdline-tools\bin

# Install required packages
sdkmanager --install "platforms;android-36"
sdkmanager --install "platform-tools"
sdkmanager --install "build-tools;36.0.0"
sdkmanager --install "cmdline-tools;latest"
```

## 🌐 Environment Variables Setup
Open Windows Settings → System → About → Advanced system settings → Environment Variables

![alt text](https://github.com/user-attachments/assets/2762a53d-7eb4-4ae8-9439-2a9bd1ed81f5)

![alt text](https://github.com/user-attachments/assets/e636e3f9-46dd-48ee-ba69-68eeeb71de90)

### Add System Variable:
| Variable | Value |
|----------|-------|
| ANDROID_HOME | C:\progs\android_sdk |

### Add to Path Variable:
```
%ANDROID_HOME%\platform-tools
%ANDROID_HOME%\cmdline-tools\latest\bin
%ANDROID_HOME%\build-tools\35.0.2
```

## ✅ Verify Installation

```cmd
flutter doctor
```

If everything is configured correctly, Flutter should recognize the installed Android SDK.

### Notes:
- After changing environment variables, you may need to restart your terminal
- You may also need to specify the JDK location for Flutter:
```cmd
flutter config --jdk-dir "C:\Program Files\Java\jdk-23"
```

### Build Your App:
```cmd
flutter clean
flutter build apk --release
```
