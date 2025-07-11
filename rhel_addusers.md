# 👤 Add a New User and Grant Sudo Access via the Wheel Group

> 🔗 [Back to Main README](./README.md)

Follow these steps to create a new user and add them to the `wheel` group.

## 🧱 Prerequisites
- You must have root privileges or be able to run commands with `sudo`.

## 🛠️ Steps

### 1. Create a New User
Replace `username` with your desired username:
```bash
sudo useradd -m username
sudo passwd username
sudo usermod -aG wheel username
groups username
