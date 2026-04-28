# 🐧 Linux Basic Commands Assignment

## 📌 Overview

This assignment covers fundamental Linux commands including directory management, file operations, and content manipulation. It is designed to build hands-on experience with essential shell commands.

---

## 🎯 Objectives

* Understand directory creation and deletion
* Perform file operations without using editors
* Practice text manipulation using CLI
* Learn file viewing techniques
* Explore file and directory listing options

---

## 🛠️ Tasks & Commands

### 1️⃣ Check Current Directory

```bash
pwd
```
<img width="313" height="131" alt="image" src="https://github.com/user-attachments/assets/218a88d7-8be5-4a2f-941d-f545d6c8fb41" />




---

### 2️⃣ Create Directory "linux"

```bash
mkdir linux
```

📸 *Add Screenshot:* `images/step2_mkdir_linux.png`

---

### 3️⃣ Create "Assignment-01" inside "linux"

```bash
mkdir linux/Assignment-01
```

📸 *Add Screenshot:* `images/step3_assignment_dir.png`

---

### 4️⃣ Create Directory in /tmp Without Changing Directory

```bash
mkdir /tmp/dir1
```

📸 *Add Screenshot:* `images/step4_tmp_dir1.png`

---

### 5️⃣ Create Nested Directory Structure (Single Command)

```bash
mkdir -p /tmp/dir1/dir2/dir3
```

#### 📂 Directory Structure

```
/tmp
 └── dir1
      └── dir2
           └── dir3
```

📸 *Add Screenshot:* `images/step5_tree.png`

---

### 6️⃣ Delete "dir3"

```bash
rm -r /tmp/dir1/dir2/dir3
```

📸 *Add Screenshot:* `images/step6_delete_dir3.png`

---

### 7️⃣ Create Empty File (First Name)

```bash
touch /tmp/first-name
```

📸 *Add Screenshot:* `images/step7_touch.png`

---

### 8️⃣ Add First Line to File

```bash
echo "This is my first line" > /tmp/first-name
```

📸 *Add Screenshot:* `images/step8_add_line.png`

---

### 9️⃣ Append Additional Line (Without Overwriting)

```bash
echo "this is a additional content" >> /tmp/first-name
```

📸 *Add Screenshot:* `images/step9_append.png`

---

### 🔟 Create "last-name" File with Content

```bash
echo "last-name is my last name" > /tmp/last-name
```

📸 *Add Screenshot:* `images/step10_lastname.png`

---

### 1️⃣1️⃣ Add Line at Beginning of File

```bash
sed -i '1i this is line at the beginning' /tmp/last-name
```

📸 *Add Screenshot:* `images/step11_sed.png`

---

### 1️⃣2️⃣ Add Multiple Lines (8–10 Lines)

```bash
for i in {1..10}; do echo "Line $i" >> /tmp/last-name; done
```

📸 *Add Screenshot:* `images/step12_multiple_lines.png`

---

## 📖 File Viewing Commands

### 🔹 Top 5 Lines

```bash
head -n 5 /tmp/last-name
```

### 🔹 Bottom 2 Lines

```bash
tail -n 2 /tmp/last-name
```

### 🔹 Only 6th Line

```bash
sed -n '6p' /tmp/last-name
```

### 🔹 Lines 3 to 8

```bash
sed -n '3,8p' /tmp/last-name
```

📸 *Add Screenshot:* `images/step13_view_commands.png`

---

## 📂 Listing /tmp Directory

### 🔹 List All Files (Including Hidden)

```bash
ls -la /tmp
```

### 🔹 List Only Files

```bash
find /tmp -maxdepth 1 -type f
```

### 🔹 List Only Directories

```bash
find /tmp -maxdepth 1 -type d
```

📸 *Add Screenshot:* `images/step14_list.png`

---

## 📁 File Operations

### 🔹 Copy "last-name" to dir2

```bash
cp /tmp/last-name /tmp/dir1/dir2/
```

### 🔹 Copy with New Name

```bash
cp /tmp/last-name /tmp/dir1/dir2/last-name.copy
```

### 🔹 Rename "first-name"

```bash
mv /tmp/first-name /tmp/new-first-name
```

### 🔹 Move "last-name" to dir1

```bash
mv /tmp/last-name /tmp/dir1/
```

📸 *Add Screenshot:* `images/step15_file_ops.png`

---

## 📌 Notes

* All operations are performed using CLI (no editors like vim/nano).
* Ensure proper permissions when working in `/tmp`.
* Use `tree /tmp` (if installed) for better visualization.

---

## 📁 Suggested Repository Structure

```
linux-assignment/
│── README.md
└── images/
    ├── step1_pwd.png
    ├── step2_mkdir_linux.png
    ├── step3_assignment_dir.png
    ├── step4_tmp_dir1.png
    ├── step5_tree.png
    ├── step6_delete_dir3.png
    ├── step7_touch.png
    ├── step8_add_line.png
    ├── step9_append.png
    ├── step10_lastname.png
    ├── step11_sed.png
    ├── step12_multiple_lines.png
    ├── step13_view_commands.png
    ├── step14_list.png
    └── step15_file_ops.png
```

---

## 🚀 Author

**Your Name**

---
