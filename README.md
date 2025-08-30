# Customised Virtual File System (CDFS)

## 📌 Overview

This project implements a **Customised Virtual File System (CDFS)** in C. It simulates the core functionalities of a file system within a single program, providing users with the ability to create, open, read, write, delete, and manage files via custom commands.

The system mimics the behaviour of traditional file systems using in-memory data structures such as **inode tables, superblocks, file tables, and UFDT (User File Descriptor Table)**.

---

## ⚙️ Features

* **File Operations:**

  * Create new files with permissions
  * Read and write file contents
  * Open and close files
  * Delete files (`rm`)
  * Truncate (empty) files
* **File Metadata Management:**

  * View file details using `stat` or `fstat`
  * Manage file offsets with `lseek`
  * Track inode, file size, and permissions
* **System Commands:**

  * `ls` → List all existing files
  * `help` → Display available commands
  * `man <command>` → Show manual for a specific command
  * `clear` → Clear the console
  * `exit` → Terminate the VFS

---

## 📂 Data Structures Used

* **SUPERBLOCK** → Tracks total and free inodes
* **INODE** → Stores file metadata (name, type, size, permissions)
* **FILETABLE** → Holds offsets, mode, and reference to inode
* **UFDT (User File Descriptor Table)** → Array mapping file descriptors to FILETABLE entries

---

## 🖥️ Commands

| Command  | Description                          | Usage                                        |
| -------- | ------------------------------------ | -------------------------------------------- |
| create   | Create a new file with permissions   | `create <filename> <permission>`             |
| open     | Open an existing file                | `open <filename> <mode>`                     |
| read     | Read data from a file                | `read <filename> <bytes>`                    |
| write    | Write data into a file               | `write <filename>`                           |
| ls       | List all files                       | `ls`                                         |
| stat     | Show file details by name            | `stat <filename>`                            |
| fstat    | Show file details by file descriptor | `fstat <fd>`                                 |
| truncate | Remove data from file                | `truncate <filename>`                        |
| close    | Close a file                         | `close <filename>`                           |
| closeall | Close all files                      | `closeall`                                   |
| lseek    | Change file offset                   | `lseek <filename> <offset> <start/curr/end>` |
| rm       | Delete a file                        | `rm <filename>`                              |
| man      | Show command manual                  | `man <command>`                              |
| help     | Show all available commands          | `help`                                       |
| clear    | Clear screen                         | `clear`                                      |
| exit     | Exit the VFS                         | `exit`                                       |

---

## 🚀 How to Run

1. Compile the program:

   ```bash
   g++ CDFS.cpp -o cdfs
   ```
2. Run the executable:

   ```bash
   ./cdfs
   ```
3. Enter commands in the terminal (e.g., `create demo.txt 3`).

---

## 📌 Permissions & Modes

* **Permissions:**

  * `1` → Read Only
  * `2` → Write Only
  * `3` → Read & Write
* **Modes (for open):**

  * `1` → Read
  * `2` → Write
  * `3` → Read & Write


This project is licensed under the **MIT License**.
