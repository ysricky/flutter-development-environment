# flutter-development-environment (Ubuntu 22.04.1 LTS)
Step by step instalasi Flutter + VSCode

## Requirements
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
- Mengatur direktori di Home
```shell
cd
mkdir Android
cd Android
mkdir cmdline-tools
```
- [Download Flutter SDK](https://docs.flutter.dev/get-started/install/linux#install-flutter-manually)
- Extract file kemudian pindahkan folder `flutter` ke direktori Android
```shell
cd ~/Downloads/[folder_hasil_extract]/
sudo mv flutter/ ~/Android/
```
- [Install Android Command Line Tools](https://developer.android.com/studio#command-tools)
- Extract file
- Pindahkan folder hasil extract ke direktori Android
```shell
sudo mv latest/ ~/Android/cmdline-tools/
```
- [Dokumentasi `sdkmanager`](https://developer.android.com/studio/command-line/sdkmanager)
- [Dokumentasi `avdmanager`](https://developer.android.com/studio/command-line/avdmanager)
