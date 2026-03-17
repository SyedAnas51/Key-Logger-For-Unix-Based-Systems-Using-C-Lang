# 🔐 Linux Keylogger in C (OS Project)

## 📌 Overview
This project is a **Linux-based keylogger written in C**, developed as part of an **Operating Systems course**. It demonstrates how low-level input devices can be accessed and monitored using system calls.

The program reads raw keyboard events from the Linux input subsystem and logs them into a file.

> ⚠️ This project is strictly for **educational and research purposes only**.

---

## 🎯 Features
- Captures real-time keyboard input from `/dev/input/event0`
- Logs keystrokes into `/tmp/data`
- Uses Linux input event interface (`/linux/input.h`)
- Automated script for compile + run + permission handling
- Restores original device permissions after execution ✅

---

## 🛠️ Technologies Used
- **C Programming Language**
- **Linux Input Subsystem**
- **Bash Scripting**
- System Calls (`open`, `read`, etc.)

---

## 📂 Project Structure

Keylogger_C/
│── keylogger.c # Main keylogger source code
│── run_main.sh # Script to compile, execute, and manage permissions
│── README.md # Documentation


---

## ⚙️ How It Works
1. The program opens the keyboard input device:

/dev/input/event0

2. It continuously reads input events using:
- `struct input_event`
3. When a key is pressed:
- It maps the keycode to a readable character
- Writes it into:
  ```
  /tmp/data
  ```
4. The bash script:
- Compiles the program
- Temporarily adjusts device permissions
- Runs the keylogger
- Restores original permissions after execution

---

## ▶️ How to Run

### Step 1: Give permission to script
```bash
chmod +x run_main.sh
Step 2: Run the script
sudo ./run_main.sh
📁 Output

Logged keystrokes are stored in:

/tmp/data
⚠️ Important Notes

Requires root privileges to access /dev/input/event0

Works only on Linux systems

Device path may vary (e.g., event1, event2, etc.)

To find correct device:

cat /proc/bus/input/devices
🚨 Disclaimer

This project is created only for academic purposes.

Unauthorized use of keyloggers is illegal

Do NOT use this on systems without permission

The author is not responsible for misuse

📚 Learning Outcomes

Understanding Linux input device handling

Working with low-level system programming

File handling and logging in C

Bash scripting for automation

Permission management in Linux
