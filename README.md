# Install Flutter tanpa Android Studio (Ubuntu 22.04.1 LTS) *update September 2022*
Step by step instalasi Flutter + VSCode
Credits to [aantamim.id](https://aantamim.id/flutter-install-tanpa-android-studio-ubuntu/)

### 1. Install dependencies
- Update Ubuntu
```shell
sudo apt update && sudo apt upgrade
```
- [Install tools dan library](https://docs.flutter.dev/get-started/install/linux#system-requirements)
- [Install library 32bit (untuk OS Linux 64bit)](https://developer.android.com/studio/install#64bit-libs)
- Install Java
```shell
sudo apt install openjdk-11-jre
sudo apt install openjdk-11-jdk
```
### 2. Membuat direktori `Android`
- Buat direktori Android di Home
```shell
cd
mkdir Android
cd Android/
mkdir cmdline-tools
```
### 3. Instalasi Flutter SDK dan Android Command Line Tools
- [Download Flutter SDK](https://docs.flutter.dev/get-started/install/linux#install-flutter-manually)
- Extract file kemudian pindahkan folder `flutter` ke direktori Android
```shell
cd ~/Downloads/[folder_hasil_extract]/
sudo mv flutter/ ~/Android/
```
- [Download Android Command Line Tools](https://developer.android.com/studio#command-tools)
- Extract file dan pindahkan folder hasil extract ke direktori Android
```shell
sudo mv latest/ ~/Android/cmdline-tools/
```
- [Dokumentasi `sdkmanager`](https://developer.android.com/studio/command-line/sdkmanager)
- [Dokumentasi `avdmanager`](https://developer.android.com/studio/command-line/avdmanager)
### 4. Struktur direktori `Android`
- Sejauh ini struktur direktori Android menjadi:
```shell
Android/
     flutter/
     cmdline-tools/
          latest/
```
### 5. Set PATH
- Copy dan paste baris kode ini ke baris paling akhir file .bashrc
```shell
# Android
export ANDROID=$HOME/Android
export PATH=$ANDROID/cmdline-tools/latest:$PATH
export PATH=$ANDROID/cmdline-tools/latest/bin:$PATH
export PATH=$ANDROID/platform-tools:$PATH
 
# Android SDK
export ANDROID_SDK=$HOME/ANDROID
export PATH=$ANDROID_SDK:$PATH
 
# Flutter
export FLUTTER=$ANDROID/flutter
export PATH=$FLUTTER/bin:$PATH
```
- Save file, kemudian:
```shell
source ~/.bashrc
```
### 6. Instalasi Android SDK
- Untuk melihat versi dari `system-images`, `platforms;android`, `platform-tools`, `patcher`, `emulator`, `build-tools`, ketik command berikut:
```shell
cd Android/cmdline-tools/tools
sdkmanager --list
```
- Untuk menginstall Android SDK versi 30 ketik command berikut satu-persatu:
```shell
sdkmanager "system-images;android-30;google_apis;x86_64"
sdkmanager "platforms;android-30"
sdkmanager "platform-tools"
sdkmanager "patcher;v4"
sdkmanager "emulator"
sdkmanager "build-tools;30.0.2"
```
- Setujui lisensi
```shell
sdkmanager --licenses
```
### 7. Konfigurasi SDK Path untuk Flutter
- Ketik command:
```shell
flutter config --android-sdk ~/Android
```
- Jalankan command `flutter doctor`
```shell
flutter doctor -v
```
- Kemudian jalankan command berikut untuk menyetujui lisensi
```shell
flutter doctor --android-licenses
```
### 8. Membuat emulator
- Ketikkan command di bawah untuk melihat daftar device, pilih satu dan salin ID device
```shell
avdmanager list
```
- Beri nama pada emulator yang akan dibuat dan paste ID device ke baris kode berikut:
```shell
avdmanager -s create avd -n nama_emulator -k "system-images;android-30;google_apis;x86_64" -d id_device
```
### 9. Selesai
- Download `Flutter` extension untuk VSCode (`Dart` extension otomatis terinstall)
