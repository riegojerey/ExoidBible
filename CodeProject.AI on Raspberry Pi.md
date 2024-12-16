# CodeProject.AI on Raspberry Pi

[Exoid Bash Script Documentation](https://github.com/riegojerey/ExoidBashScript)

---

## Chapters

- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)

---

## Introduction

This guide provides instructions for installing and running CodeProject.AI on a Raspberry Pi using a custom bash script from the [ExoidBashScript repository](https://github.com/riegojerey/ExoidBashScript).

---

## Installation

### Prerequisites

Ensure you have the following before starting the installation:

- Raspberry Pi running Raspberry Pi OS (Debian-based).
- Git installed on your Raspberry Pi:
  ```bash
  sudo apt update && sudo apt install git -y
  ```
- A stable internet connection.

### Steps

1. **Clone the Bash Script Repository**:
   ```bash
   git clone https://github.com/riegojerey/ExoidBashScript.git
   ```

2. **Navigate to the Repository Directory**:
   ```bash
   cd ExoidBashScript
   ```

3. **Make the Script Executable**:
   ```bash
   chmod +x install_codeproject_ai.sh
   ```

4. **Run the Installation Script**:
   ```bash
   ./install_codeproject_ai.sh
   ```

5. **Follow On-Screen Instructions**:
   The script will handle the installation and configuration of CodeProject.AI on your Raspberry Pi.

---

## Usage

### Access the Web Interface to Install Modules

1. Open a web browser and navigate to:
   ```
   http://localhost:32168/explorer.html
   ```

2. Follow the on-screen instructions to install the necessary modules for your use case.

