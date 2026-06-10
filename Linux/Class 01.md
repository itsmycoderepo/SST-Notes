# 📖 Class 01 - Linux Basics & File Management
**Date:** 02-05-2026

---

# 📂 File Operations

## Create Files

The `touch` command is used to create files.

### Syntax

```bash
touch <file_name>
```

### Examples

```bash
touch f1
touch f2 f3 f4
```

---

## Clear Terminal Screen

The `clear` command clears the terminal screen.

```bash
clear
```

---

# 📋 Listing Files & Directories

## List Files

```bash
ls
```

Lists files and directories in the current directory.

---

## Long Listing Format

```bash
ls -l
```

Lists files and directories in long format.

---

## Sort by Time

```bash
ls -lt
```

Lists files and directories based on modification time.

---

## Reverse Order

```bash
ls -lrt
```

Lists files and directories in reverse order.

---

## Human Readable File Size

```bash
ls -lrth
```

Lists files in reverse order with human-readable sizes.

---

# 📁 Directory Operations

## Create Directory

### Syntax

```bash
mkdir <directory_name>
```

### Examples

```bash
mkdir sagar
mkdir test test1 test2
```

---

## Change Directory

### Syntax

```bash
cd <directory_name>
```

### Example

```bash
cd sagar
```

---

## Move One Directory Back

```bash
cd ..
```

Moves to the parent directory.

---

## Move to Home Directory

```bash
cd
```

Returns to the user's home directory.

---

# 📍 Present Working Directory

Displays the current working directory.

```bash
pwd
```

---

# 🗑️ File & Directory Deletion

## Delete a File

### Syntax

```bash
rm <file_name>
```

### Examples

```bash
rm f1
rm f2 f3 f4
```

---

## Delete a Directory

### Syntax

```bash
rm -rf <directory_name>
```

### Examples

```bash
rm -rf sagar
rm -rf test test1
```

---

## Delete All Files in Current Directory

```bash
rm *
```

> ⚠️ Deletes all files in the present working directory.

---

## Delete All Files and Directories

```bash
rm -rf *
```

> 🚨 **Dangerous Command**
>
> Deletes everything in the current directory.

---

## Delete Files by Extension

### Delete All `.c` Files

```bash
rm *.c
```

### Delete All `.txt` Files

```bash
rm *.txt
```

---

# ✏️ VI Editor

The **Vi Editor** is used to create and edit files.

## Open/Create a File

```bash
vi <file_name>
```

### Example

```bash
vi test.txt
```

---

# ⌨️ Modes in VI Editor

## Insert Mode

Press:

```text
i
```

to enter Insert Mode.

---

# 💾 Save & Exit Commands

## Save and Quit

```text
ESC + :wq!
```

---

## Save Only

```text
ESC + :w
```

---

## Quit Without Saving

```text
ESC + :q!
```

---

# 📄 Display File Content

```bash
cat <file_name>
```

### Example

```bash
cat test.txt
```

---

# 🔄 Undo Changes

```text
ESC + u
```

Undo the last change.

---

# 🔢 Line Numbers

## Show Line Numbers

```text
ESC + :set nu
```

---

## Remove Line Numbers

```text
ESC + :set nonu
```

---

# 🎯 Move Cursor to Specific Line

### Move to Line 4

```text
ESC + :4
```

---

# 🔍 Find & Replace in VI Editor

## Syntax

```text
ESC + :%s/<old_word>/<new_word>/ig
```

### Example

```text
ESC + :%s/linux/windows/ig
```

---

## Meaning of Options

| Symbol | Meaning |
|----------|----------|
| `%` | All lines |
| `s` | Substitute |
| `g` | Global replacement |
| `i` | Case sensitive (as per class notes) |

---

## Replace in Entire File

```text
ESC + :%s/linux/windows/ig
```

---

## Replace in Line 2

```text
ESC + :2s/linux/windows/ig
```

---

## Replace Between Line 2 and 3

```text
ESC + :2,3s/linux/windows/ig
```

---

## Replace From Line 2 Till End

```text
ESC + :2,$s/linux/windows/ig
```

---

## Replace in Multiple Specific Lines

```text
ESC + :2s/linux/windows/ig | 5s/linux/windows/ig
```

---

# ❌ Delete a Line

```text
ESC + dd
```

Deletes the current line.

---

# 🖨️ Printing Output in Linux

The `echo` command is used to print output.

## Syntax

```bash
echo "message"
```

---

## Example 1

```bash
echo "welcome to ss training"
```

### Output

```text
welcome to ss training
```

---

## Example 2

```bash
echo -e "welcome \nss training"
```

### Output

```text
welcome
ss training
```

### Explanation

| Option | Description |
|----------|------------|
| `-e` | Enables interpretation of escape characters |
| `\n` | New line |

---

# 📝 Assignment

## Task

Display the contents of a file in reverse order.

---

# 📚 Quick Command Cheat Sheet

| Command | Description |
|----------|-------------|
| `touch` | Create files |
| `clear` | Clear terminal |
| `ls` | List files |
| `ls -l` | Long listing |
| `ls -lt` | Sort by time |
| `mkdir` | Create directory |
| `cd` | Change directory |
| `pwd` | Print current directory |
| `rm` | Delete file |
| `rm -rf` | Delete directory |
| `vi` | Open VI editor |
| `cat` | Display file contents |
| `echo` | Print text |

---

> 💡 **Tip for DevOps Engineers**
>
> Be extremely careful while using:
>
> ```bash
> rm -rf *
> ```
>
> This command can permanently delete important files and directories.
