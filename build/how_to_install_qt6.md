# Qt 6 Installation Guide for Windows and Linux

This guide provides step-by-step instructions for installing **Qt 6.8.3 LTS** on both **Windows** and **Linux**. It includes methods using the official Qt Online Installer and the community-supported `aqtinstall` tool.

---

## Windows Installation

### Method 1: Qt Online Installer (Recommended)

1. **Download the Installer**

   * Visit the official Qt website: [https://www.qt.io/download](https://www.qt.io/download)
   * Click **Explore Qt Community Edition**
   * Click **Download the Qt Online Installer**

2. **Run the Installer**

   * Launch the downloaded file (e.g., `qt-unified-windows-x64.exe`)
   * Sign in or create a Qt account

3. **Select Components**

   * Choose version `6.8.3 LTS`
   * Select desired kits (e.g., `MSVC 2022`)
   * Optional: Add tools like **Qt Creator**, **CMake**

4. **Set Installation Directory**

   * Example: `C:\Qt`

5. **Add Qt to System Path**

```cmd
setx /M path "%path%;C:\Qt\6.8.3\msvc2022_64\bin"
```

---

### Method 2: Using `aqtinstall`

#### Prerequisites

* [Visual Studio](https://visualstudio.microsoft.com/) with C++ Desktop Development
* [Python](https://www.python.org/) 3.9 or newer

#### Steps

1. **Install `aqtinstall`**

```bash
pip install -U pip
pip install aqtinstall
```

2. **Install Qt using aqt**

```bash
aqt install-qt windows desktop 6.8.3 win64_msvc2022_64 -O C:\Qt \
    --archives icu qtbase qtdeclarative qtsvg -m qt5compat
```

3. **Add Qt to System Path**

```cmd
setx /M path "%path%;C:\Qt\6.8.3\msvc2022_64\bin"
```

---

## Linux Installation

### Method 1: Qt Online Installer

1. **Download the Installer**

   * Go to: [https://www.qt.io/download](https://www.qt.io/download)
   * Download: `qt-unified-linux-x64-online.run`

2. **Make Installer Executable and Run**

```bash
chmod +x qt-unified-linux-x64-online.run
./qt-unified-linux-x64-online.run
```

3. **Follow the Installation Wizard**

   * Log in with your Qt account
   * Select Qt version `6.8.3` and desired modules
   * Complete the installation

---

### Method 2: Using `aqtinstall`

#### Prerequisites

```bash
sudo apt update
sudo apt install -y build-essential python3 python3-pip python3-venv \
    git cmake ninja-build libgl1-mesa-dev libxkbcommon-x11-dev
```

#### Create a Virtual Environment

```bash
python3 -m venv ~/.venv
source ~/.venv/bin/activate
```

#### Install and Use `aqtinstall`

```bash
pip install -U pip
pip install aqtinstall

# Install Qt
aqt install-qt linux desktop 6.8.3 linux_gcc_64 -O ~/Qt6 \
    --archives icu qtbase qtdeclarative qtsvg -m qt5compat
```

---

## Resources

* [Qt Documentation](https://doc.qt.io/)
* [Qt Creator IDE](https://www.qt.io/product/development-tools)
* [aqtinstall GitHub](https://github.com/miurahr/aqtinstall)

---

> After installation, make sure the Qt `bin` directory is in your system's `PATH` to use tools like `qmake` or `qt-cmake` from the terminal.
