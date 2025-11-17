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

You should have the following structure: `C:\progs\android_sdk\cmdline-tools\latest\(files from cmdline-tools archive)`

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
## To start a new project
```cmd
flutter create demo
cd demo
flutter run
```

### Build Your App:
```cmd
flutter clean
flutter build apk --release or flutter build apk --split-per-abi

```



RU

# Настройка Flutter для Android без Android Studio (Windows)

Я потратил 5 часов, пока всё заработало. Эта инструкция работает на 100% для Windows 11 на текущий момент. При изменении переменных среды перезапускайте программы или терминал, но иногда это не помогает и лучше перезагрузить ПК.

## 📥 Скачивание Flutter
[Официальный сайт Flutter](https://docs.flutter.dev/install/manual)

![alt text](https://github.com/user-attachments/assets/a38dafc7-6ac1-4e4c-97de-f4513faf53cd)

Распакуйте архив в `C:\progs\`. Я использую winrar, также проверено стандартным распаковщиком Windows 11.
Добавьте `C:\progs\flutter\bin` в PATH

## 📥 Скачивание инструментов
1. Скачайте **Command Line Tools** с [официального сайта Android](https://developer.android.com/studio)
2. Прокрутите вниз до раздела **"Command line tools only"**

## 📁 Создание структуры папок
Создайте папку для Android SDK (пример для Windows):
```
C:\progs\android_sdk
```

**Важно:** Не используйте папки со специальными правами доступа (например, "Program Files")

## 🗂️ Распаковка инструментов
Распакуйте `commandlinetools-win-13114758_latest.zip` в папку `C:\progs\android_sdk`

У вас должна быть следующая структура: `C:\progs\android_sdk\cmdline-tools\latest\(files from cmdline-tools archive)`

## ⚙️ Установка пакетов
Откройте Командную строку и выполните:

```cmd
# Перейдите в папку sdkmanager
cd C:\progs\android_sdk\cmdline-tools\bin

# Установите необходимые пакеты
sdkmanager --install "platforms;android-36"
sdkmanager --install "platform-tools"
sdkmanager --install "build-tools;36.0.0"
sdkmanager --install "cmdline-tools;latest"
```

## 🌐 Настройка переменных среды
Откройте Параметры Windows → Система → О системе → Дополнительные параметры системы → Переменные среды

![alt text](https://github.com/user-attachments/assets/2762a53d-7eb4-4ae8-9439-2a9bd1ed81f5)

![alt text](https://github.com/user-attachments/assets/e636e3f9-46dd-48ee-ba69-68eeeb71de90)

### Добавьте системную переменную:
| Переменная | Значение |
|------------|----------|
| ANDROID_HOME | C:\progs\android_sdk |

### Добавьте в переменную Path:
```
%ANDROID_HOME%\platform-tools
%ANDROID_HOME%\cmdline-tools\latest\bin
%ANDROID_HOME%\build-tools\36.0.1
```

## ✅ Проверка установки

```cmd
flutter doctor
```

Если всё настроено правильно, Flutter должен распознать установленный Android SDK.

### Примечания:
- После изменения переменных среды может потребоваться перезапуск терминала
- Также может потребоваться указать расположение JDK для Flutter:
```cmd
flutter config --jdk-dir "C:\Program Files\Java\jdk-23"
```

## Чтобы начать новый проект
```cmd
flutter create demo
cd demo
flutter run
```

### Сборка приложения:
```cmd
flutter clean
flutter build apk --release или flutter build apk --split-per-abi
```

## Также можно развернуть эмулятор

Скачайте плагин в VS CODE
![alt text](https://github.com/user-attachments/assets/d26f8ab2-6a1f-4b86-b2f1-b0cc60e83767)
Далее введите например 
```cmd
sdkmanager "system-images;android-34;google_apis;x86_64"
```
Далее

```cmd
avdmanager create avd -n MyAVD -k "system-images;android-34;google_apis;x86_64" -d pixel_9_pro
```
Настройте путь для эмулятора в расширении vs code
![alt text](https://github.com/user-attachments/assets/12430c03-0736-4185-9526-db5d8295115a)
Введите в поиске emulator
![alt text](https://github.com/user-attachments/assets/d00c926b-83f0-45eb-8eb2-b73d029910fd)

Далее flutter run или ctrl + shift + P -> emulatop 
