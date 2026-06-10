# 📖 Class 02 - Redirection, Copy, Move, Word Count, Grep & Permissions
**Date:** 03-05-2026

---

# 🔄 Redirection Operators

Redirection is used to send the output of a command into a file instead of displaying it on the terminal.

---

## Write Output to a File (`>`)

The `>` operator writes the output of a command to a file.

If the file does not exist, it will be created.

If the file already exists, its content will be overwritten.

### Syntax

```bash
command > file_name
```

### Examples

```bash
echo "welcome" > test
```

### Output in `test`

```text
welcome
```

---

### Important Note

> ⚠️ The `>` operator replaces the existing content of the file.

Example:

```bash
echo "linux" > test
echo "devops" > test
```

Final content:

```text
devops
```

---

## Append Output to a File (`>>`)

The `>>` operator appends content to the end of a file.

If the file does not exist, it will be created.

### Syntax

```bash
command >> file_name
```

### Examples

```bash
echo "welcome" > test
echo "ss training" >> test
```

### Output

```text
welcome
ss training
```

---

# 📋 Copy Command (`cp`)

The `cp` command is used to copy files and directories.

---

## Copy File to Another File

### Syntax

```bash
cp <source_file> <destination_file>
```

### Example

```bash
cp test test1
```

Copies the content of `test` into `test1`.

---

## Copy File to Directory

### Syntax

```bash
cp <file_name> <directory>
```

### Example

```bash
cp test /home/ec2-user/demo1/
```

Copies `test` into the `demo1` directory.

---

## Copy Directory Recursively

### Syntax

```bash
cp -R <source_directory> <destination_directory>
```

### Example

```bash
cp -R test2 demo1
```

Copies all files and subdirectories.

---

# 🚚 Move Command (`mv`)

The `mv` command is used for:

- Moving files
- Moving directories
- Renaming files
- Renaming directories

---

## Rename a File

### Syntax

```bash
mv <old_file> <new_file>
```

### Example

```bash
mv test test1
```

---

## Move File to Directory

### Syntax

```bash
mv <file_name> <directory>
```

### Example

```bash
mv test demo1/
```

---

## Move Directory

### Syntax

```bash
mv <directory1> <directory2>
```

### Example

```bash
mv demo1 backup
```

---

# 📊 Word Count Command (`wc`)

The `wc` command displays:

- Number of lines
- Number of words
- Number of characters

---

## Syntax

```bash
wc <file_name>
```

### Example

```bash
wc test
```

### Output

```text
2 6 33 test
```

Meaning:

| Value | Description |
|---------|------------|
| 2 | Number of Lines |
| 6 | Number of Words |
| 33 | Number of Characters |

---

## Count Lines Only

```bash
wc -l test
```

---

## Count Characters Only

```bash
wc -c test
```

---

## Count Words Only

```bash
wc -w test
```

---

# 🔍 Grep Command

`grep` is used to search for a pattern or string inside a file.

---

## Basic Search

### Syntax

```bash
grep <pattern> <file_name>
```

### Example

```bash
grep linux test
```

Displays all lines containing `linux`.

---

## Search Full Word Only

### Syntax

```bash
grep -w <pattern> <file_name>
```

### Example

```bash
grep -w linux test
```

Matches only complete words.

---

## Search Multiple Patterns

### Syntax

```bash
grep -e <pattern1> -e <pattern2> <file_name>
```

### Example

```bash
grep -e linux -e devops test
```

---

## Search Lines Starting with Pattern

### Syntax

```bash
grep '^pattern' file
```

### Example

```bash
grep '^linux' test
```

---

## Search Lines Ending with Pattern

### Syntax

```bash
grep 'pattern$' file
```

### Example

```bash
grep 'linux$' test
```

---

## Invert Search

Displays lines that do NOT contain the pattern.

### Syntax

```bash
grep -v pattern file
```

### Example

```bash
grep -v linux test
```

---

## Count Matching Lines

### Syntax

```bash
grep -c pattern file
```

### Example

```bash
grep -c linux test
```

---

## Ignore Case

### Syntax

```bash
grep -i pattern file
```

### Example

```bash
grep -i linux test
```

Matches:

```text
linux
Linux
LINUX
LiNuX
```

---

# 🔐 Linux Permissions

Every file and directory has permissions assigned to:

- Owner (User)
- Group
- Others

Example:

```text
-rw-r--r--
```

---

## Permission Breakdown

```text
Owner  Group  Others
 rw-    r--    r--
```

Numeric Value:

| Permission | Binary | Value |
|------------|---------|--------|
| Read (r) | 2² | 4 |
| Write (w) | 2¹ | 2 |
| Execute (x) | 2⁰ | 1 |

---

## Common Permission Values

| Permission | Value |
|------------|-------|
| r-- | 4 |
| rw- | 6 |
| rwx | 7 |
| r-x | 5 |

---

# 🔧 chmod Command

Used to change permissions.

---

## Change File Permission

### Syntax

```bash
chmod <permission> <file_name>
```

### Example

```bash
chmod 777 file.txt
```

---

## Change Directory Permission Recursively

### Syntax

```bash
chmod -R <permission> <directory_name>
```

### Example

```bash
chmod -R 777 demo1
```

---

# 📌 Common chmod Examples

## 777

```bash
chmod 777 file.txt
```

Permissions:

| User | Group | Others |
|--------|--------|--------|
| rwx | rwx | rwx |

Everyone gets full access.

> ⚠️ Not recommended for production systems.

---

## 644

```bash
chmod 644 file.txt
```

Permissions:

| User | Group | Others |
|--------|--------|--------|
| rw- | r-- | r-- |

Most common file permission.

---

## 555

```bash
chmod 555 file.txt
```

Permissions:

| User | Group | Others |
|--------|--------|--------|
| r-x | r-x | r-x |

Read and execute only.

---

## 700

```bash
chmod 700 file.txt
```

Permissions:

| User | Group | Others |
|--------|--------|--------|
| rwx | --- | --- |

Only owner has access.

---

# 🔧 Symbolic chmod

## User Types

| Symbol | Meaning |
|----------|----------|
| u | Owner |
| g | Group |
| o | Others |

---

## Add Permission

### Add Read, Write, Execute to Owner

```bash
chmod u+rwx file.txt
```

---

### Add Permission to User and Group

```bash
chmod ug+rwx file.txt
```

---

## Remove Permission

### Remove Read Permission from Others

```bash
chmod o-r file.txt
```

---

### Remove Execute Permission from Owner

```bash
chmod u-x file.txt
```

---

# 📝 Assignment

Practice the following:

1. Create a file and test `>` and `>>`.
2. Copy a file to another file.
3. Copy a directory recursively.
4. Rename a file using `mv`.
5. Search a word using `grep`.
6. Search multiple words using `grep -e`.
7. Set file permission to:
   - 777
   - 644
   - 555
   - 700
8. Add and remove permissions using symbolic mode.

---

# 📚 Quick Command Cheat Sheet

| Command | Description |
|----------|------------|
| `>` | Redirect output |
| `>>` | Append output |
| `cp` | Copy files |
| `cp -R` | Copy directories |
| `mv` | Move/Rename |
| `wc` | Count lines, words, chars |
| `grep` | Search text |
| `grep -w` | Match full word |
| `grep -e` | Multiple patterns |
| `grep -v` | Invert match |
| `grep -c` | Count matches |
| `grep -i` | Ignore case |
| `chmod` | Change permissions |
| `chmod -R` | Recursive permissions |

---

> 💡 **DevOps Tip**
>
> In production environments:
>
> - Use `644` for most files.
> - Use `755` for executable scripts/directories.
> - Avoid `777` unless absolutely necessary.
> - Always verify permissions using:
>
> ```bash
> ls -l
> ```
