# Raspberry Pi 5 Setup

[Raspberry Pi Official Documentation](https://www.raspberrypi.org/documentation/)

---

## Chapters

- [Requirements](#requirements)
- [Installation](#installation)
- [Initial Configuration](#initial-configuration)

---

## Requirements

Before setting up your Raspberry Pi 5, ensure you have the following:

- Raspberry Pi 5 board
- USB-C power supply (5V, 3A minimum)
- MicroSD card (16GB or larger, Class 10 recommended)
- Computer with an SD card reader
- HDMI cable and compatible monitor
- USB keyboard and mouse
- Optional: Ethernet cable or Wi-Fi access

---

## Installation

### Step 1: Download the OS

1. Visit the [Raspberry Pi Imager page](https://www.raspberrypi.org/software/).
2. Download and install the Raspberry Pi Imager for your operating system (Windows, macOS, or Linux).

### Step 2: Flash the OS to the SD Card

1. Insert the MicroSD card into your computer.
2. Open the Raspberry Pi Imager tool.
3. Select **Choose OS** and pick an operating system (e.g., Raspberry Pi OS).
4. Select **Choose Storage** and pick your MicroSD card.
5. Click **Write** to flash the OS to the SD card.
6. Once the process is complete, safely eject the SD card.

### Step 3: Assemble Your Raspberry Pi

1. Insert the flashed MicroSD card into the MicroSD card slot on the Raspberry Pi 5.
2. Connect the HDMI cable to the Raspberry Pi and your monitor.
3. Attach the USB keyboard and mouse to the Raspberry Pi.
4. Connect the power supply to the Raspberry Pi. It should power on automatically.

---

## Initial Configuration

### Step 1: Boot the Raspberry Pi

1. Wait for the Raspberry Pi to boot into the setup wizard.
2. Follow the on-screen instructions to:
   - Set your preferred language and time zone.
   - Connect to a Wi-Fi network (if applicable).
   - Update the system software.

### Step 2: Enable SSH (Optional)

1. Open the **Raspberry Pi Configuration** tool from the desktop or terminal.
2. Go to the **Interfaces** tab and enable **SSH**.

### Step 3: Set a Static IP Address (Optional)

1. Open a terminal and edit the `dhcpcd.conf` file:
   ```bash
   sudo nano /etc/dhcpcd.conf
   ```
2. Add the following lines, replacing the placeholders:
   ```
   interface wlan0
   static ip_address=192.168.1.xxx/24
   static routers=192.168.1.1
   static domain_name_servers=8.8.8.8 8.8.4.4
   ```
3. Save and exit the file, then restart the network service:
   ```bash
   sudo systemctl restart dhcpcd
   ```

### Step 4: Install Additional Software

1. Open a terminal and update the package list:
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```
2. Install any additional packages you need, such as:
   ```bash
   sudo apt install git vim python3
   ```

---

Your Raspberry Pi 5 is now ready to use! For advanced configurations and project ideas, visit the [official Raspberry Pi documentation](https://www.raspberrypi.org/documentation/).