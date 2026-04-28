# 🐧 FileManager Utility Script (Assignment 1.2)

## 📌 Problem Statement

Create a Bash utility script `FileManager.sh` that can perform various **directory and file operations** using basic Linux commands.

⚠️ **Constraint:** Do NOT use `sed`. Only basic Linux commands are allowed.

---

## 🎯 Objectives

* Automate directory management
* Perform file operations via shell script
* Practice Linux CLI commands
* Build reusable DevOps-style utility

---

## 📂 Directory Operations

The script should support the following:

* Create a directory
* Delete a directory
* List directory contents
* List only files
* List only directories
* List all (files + directories)

### ▶️ Example Commands

```bash
./FileManager.sh addDir /tmp dir1
./FileManager.sh addDir /tmp dir2
./FileManager.sh addDir /tmp dir3

./FileManager.sh listFiles /tmp
./FileManager.sh listDirs /tmp
./FileManager.sh listAll /tmp

./FileManager.sh deleteDir /tmp dir3
```

📸 **Add Screenshot Here:**
`images/directory_operations.png`

---

## 📄 File Operations

Extend the script to support file handling:

* Create a file
* Add content to file
* Add content at the beginning of file
* Show top N lines
* Show last N lines
* Show content at a specific line
* Show content for a line range
* Move file
* Copy file
* Clear file content
* Delete file

---

### ▶️ Example Commands

```bash
# Create file
./FileManager.sh addFile /tmp/dir1 file1.txt
./FileManager.sh addFile /tmp/dir1 file1.txt "Initial Content"

# Add content
./FileManager.sh addContentToFile /tmp/dir1 file1.txt "Additional Content"

# Add content at beginning
./FileManager.sh addContentToFileBegining /tmp/dir1 file1.txt "New First Line"

# Show content
./FileManager.sh showFileBeginingContent /tmp/dir1 file1.txt 5
./FileManager.sh showFileEndContent /tmp/dir1 file1.txt 5

# Specific line
./FileManager.sh showFileContentAtLine /tmp/dir1 file1.txt 10

# Line range
./FileManager.sh showFileContentForLineRange /tmp/dir1 file1.txt 5 10

# Move file
./FileManager.sh moveFile /tmp/dir1/file1.txt /tmp/dir1/file2.txt
./FileManager.sh moveFile /tmp/dir1/file2.txt /tmp/dir2/

# Copy file
./FileManager.sh copyFile /tmp/dir2/file2.txt /tmp/dir1/
./FileManager.sh copyFile /tmp/dir1/file2.txt /tmp/dir1/file3.txt

# Clear content
./FileManager.sh clearFileContent /tmp/dir1 file3.txt

# Delete file
./FileManager.sh deleteFile /tmp/dir1 file2.txt
```

📸 **Add Screenshot Here:**
`images/file_operations.png`

---

## 🛠️ Commands Used (Concept)

| Operation        | Command        |
| ---------------- | -------------- |
| Create Directory | `mkdir`        |
| Delete Directory | `rm -r`        |
| List Files       | `find -type f` |
| List Directories | `find -type d` |
| Create File      | `touch`        |
| Add Content      | `echo >>`      |
| View Top Lines   | `head`         |
| View Last Lines  | `tail`         |
| Specific Line    | `awk`          |
| Move File        | `mv`           |
| Copy File        | `cp`           |
| Clear File       | `> file`       |

---

## 🚀 How to Run

```bash
chmod +x FileManager.sh
./FileManager.sh <operation> <arguments>
```

---

## 📂 Project Structure

```bash
file-manager/
│── FileManager.sh
│── README.md
└── images/
    ├── directory_operations.png
    └── file_operations.png
```

---

## 📌 Notes

* Do not use `sed`
* Handle invalid inputs in script
* Ensure proper file/directory permissions
* Use absolute paths for reliability

---

## 🚀 Future Enhancements

* Add logging feature
* Add help command (`--help`)
* Add colored output
* Add interactive menu

---

## 👨‍💻 Author

**Your Name**

