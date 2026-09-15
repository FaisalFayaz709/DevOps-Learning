# File and Directory Management

## Commands learned

I have learned how to create directories/files, edit text with Vim, copy content, and read files using:

- `mkdir`
- `mkdir -p`
- `touch`
- `vim`
- `cp`
- `cat`
- `cat -n`
- `less`

> `mv` and `rm` are not included as learned commands yet because I have not studied them.

---

## `mkdir` - Create a Directory

```bash
mkdir projects
```

### Why it is used

Creates a new directory.

### When to use it

Use it when organizing files into a new folder.

Multiple directories can also be created at once:

```bash
mkdir notes labs projects
```

---

## `mkdir -p` - Create Parent Directories as Needed

```bash
mkdir -p devops/linux/labs
```

### Why it is used

The `-p` option creates missing parent directories instead of failing when intermediate directories do not exist.

### When to use it

Use it when creating a complete nested folder path in one command.

---

## `touch` - Create an Empty File / Update Timestamp

```bash
touch notes.txt
```

### Why it is used

If the file does not exist, `touch` creates an empty file. If it already exists, it updates its timestamps without replacing its contents.

### When to use it

Use it to quickly create files before editing them.

Example:

```bash
touch notes.md commands.md
```

---

## `vim` - Edit a Text File

```bash
vim notes.txt
```

### Why it is used

Vim is a terminal-based text editor commonly available on Linux systems.

### When to use it

Use it when editing configuration files, scripts, notes, or other text directly on a Linux machine or remote server.

### Basic Vim workflow learned

Vim starts in **Normal mode**.

```text
i      → enter Insert mode and start typing
Esc    → return to Normal mode
:w     → save/write the file
:q     → quit
:wq    → save and quit
:q!    → quit without saving changes
```

Typical flow:

```text
vim file.txt
→ press i
→ type text
→ press Esc
→ type :wq
→ press Enter
```

---

## `cp` - Copy Files

```bash
cp source.txt backup.txt
```

### Why it is used

Creates a copy of a file at another path/name.

### When to use it

Use it when creating backups or duplicating files before making changes.

To copy a directory recursively, practice:

```bash
cp -r source-directory destination-directory
```

`-r` means recursive, so files and subdirectories inside the directory are copied as well.

---

## `cat` - Display File Content

```bash
cat notes.txt
```

### Why it is used

Prints file content directly to the terminal.

### When to use it

Use it for small files when I want to quickly inspect the entire content.

---

## `cat -n` - Display Content with Line Numbers

```bash
cat -n notes.txt
```

### Why it is used

Displays the file and adds line numbers.

### When to use it

Useful when discussing or troubleshooting a specific line in a file.

---

## `less` - Read a File Page by Page

```bash
less large-file.txt
```

### Why it is used

Unlike `cat`, `less` lets me scroll through larger files without printing everything at once.

### When to use it

Use it for long configuration files, output, or logs.

Useful controls:

```text
Space / Page Down → move forward
b                 → move backward
/search-text      → search forward
q                 → quit less
```

---

## Useful reading commands to practice next

These belong to the same file-reading topic and were identified as useful additions:

```bash
head file.txt       # show the beginning of a file
tail file.txt       # show the end of a file
tail -f app.log     # keep watching new lines appended to a file
```

They are included as **next-practice commands**, not as commands I have already mastered.
