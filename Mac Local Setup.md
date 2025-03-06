
# Mac Development Setup Guide for Beginners

A step-by-step guide to setting up your Mac for software development. Includes tools like Homebrew, Git, Python, Java, Docker, and more.

---

## Table of Contents
1. [System Updates](#1-system-updates)
2. [Xcode Command Line Tools](#2-xcode-command-line-tools)
3. [Install Homebrew](#3-install-homebrew)
4. [Git & GitHub Setup](#4-git--github-setup)
5. [Java](#5-java)
6. [Python](#6-python)
7. [Node.js & npm](#7-nodejs--npm)
8. [Docker](#8-docker)
9. [Visual Studio Code](#9-visual-studio-code)
10. [Other Helpful Tools](#10-other-helpful-tools)
11. [Security Tips](#11-security-tips)
12. [Post-Setup Checklist](#12-post-setup-checklist)
13. [Troubleshooting](#13-troubleshooting)

---

### 1. System Updates
- **Update macOS**:  
  Go to > System Preferences > Software Update. Install all updates.
- **Enable Full Disk Encryption**:  
  Turn on **FileVault** (System Preferences > Security & Privacy > FileVault).

---

### 2. Xcode Command Line Tools
**Required for compiling software**. Open Terminal and run:
```bash
xcode-select --install
```
Click "Install" when prompted.

---

### 3. Install Homebrew
**Homebrew** is a package manager for macOS. Install it:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
After installation, add Homebrew to your shell:
```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zshrc
source ~/.zshrc
```
Verify with `brew --version`.

---

### 4. Git & GitHub Setup
**Install Git**:
```bash
brew install git
```
**Configure Git**:
```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```
**Set up SSH for GitHub**:
```bash
ssh-keygen -t ed25519 -C "your@email.com"
cat ~/.ssh/id_ed25519.pub  # Copy this key to GitHub SSH settings
```

---

### 5. Java
**Install OpenJDK** (Java Development Kit):
```bash
brew install openjdk
```
**Set JAVA_HOME** (add to `~/.zshrc`):
```bash
echo 'export JAVA_HOME=$(/usr/libexec/java_home)' >> ~/.zshrc
source ~/.zshrc
```
Verify with `java -version`.

---

### 6. Python
**Install Python 3**:
```bash
brew install python
```
**Verify**:
```bash
python3 --version
pip3 --version
```
**Set up Virtual Environments**:
```bash
pip3 install virtualenv
```

---

### 7. Node.js & npm
**Install Node.js** (using Homebrew):
```bash
brew install node
```
Verify with `node -v` and `npm -v`.

---

### 8. Docker
**Install Docker Desktop for Mac**:
- Download from [Docker Hub](https://www.docker.com/products/docker-desktop)
- Drag the app to Applications, then launch it.
- Allow permissions and let it run in the background.

---

### 9. Visual Studio Code
**Install VS Code**:
```bash
brew install --cask visual-studio-code
```
**Recommended Extensions**:
- Python
- ESLint
- Docker
- Live Server

---

### 10. Other Helpful Tools
**iTerm2** (better Terminal):
```bash
brew install --cask iterm2
```

**Oh My Zsh** (Terminal customization):
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

**Postman** (API testing):
```bash
brew install --cask postman
```

**PostgreSQL** (Database):
```bash
brew install postgresql
```

---

### 11. Security Tips
- **Enable Firewall**: System Preferences > Security & Privacy > Firewall.
- **Use a Password Manager**: 1Password or Bitwarden.
- **Avoid `sudo` with Homebrew**: Never run `sudo brew` commands.
- **Hide API Keys**: Store secrets in `.env` files and add them to `.gitignore`.

---

### 12. Post-Setup Checklist
- [ ] Test `git clone` with your GitHub repo.
- [ ] Run a Python script: `python3 hello.py`.
- [ ] Build a Docker container: `docker run hello-world`.
- [ ] Deploy a test app (e.g., a simple HTML page).

---

### 13. Troubleshooting
- **"Command not found"**: Check PATH in `~/.zshrc` or restart Terminal.
- **Permission Issues**: Use `chmod` or `sudo` (carefully!).
- **Homebrew Errors**: Run `brew doctor`.

---
