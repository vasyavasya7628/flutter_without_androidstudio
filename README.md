# Flutter Android Setup Without Android Studio(Windows)

I struggled for 5 hours until I got it working. This instruction works 100% for Windows 11 as of today. When setting environment variables, restart your program or terminal, but sometimes it doesn't help and it's better to restart your PC.

## 📥 Download Flutter
[official Flutter website](https://docs.flutter.dev/install/manual)

![alt text](https://github.com/user-attachments/assets/a38dafc7-6ac1-4e4c-97de-f4513faf53cd)

unpack archive it to `C:\progs\`. I use winrar and also test default win11 extracor.
add `C:\progs\flutter\bin` to PATH
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
%ANDROID_HOME%\build-tools\36.0.1
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
flutter build apk --release or flutter build apk --split-per-abi

```
