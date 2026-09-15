# Linux Filesystem and Navigation

## What I learned

Linux uses a hierarchical filesystem made of directories and files. When working in a shell, there is always a **current working directory**.

The commands I have already used for navigation and listing are:

- `pwd`
- `cd`
- `ls`
- `ls -l`

Additional navigation/listing forms from the same topic are included below so I can practice them next.

---

## `pwd` - Print Working Directory

```bash
pwd
```

### Why it is used

It prints the full path of the directory I am currently inside.

### When to use it

Use it when I am unsure where I am in the filesystem before creating, editing, copying, or installing files.

Example output:

```text
/home/hamza/devops
```

---

## `cd` - Change Directory

```bash
cd /path/to/directory
```

### Why it is used

It changes the current working directory.

### When to use it

Use it whenever I need to move to another directory before working with its files.

Examples to practice:

```bash
cd ..      # go to the parent directory
cd ~       # go to the current user's home directory
cd -       # return to the previous directory
```

---

## `ls` - List Directory Contents

```bash
ls
```

### Why it is used

It shows files and directories in the current directory.

### When to use it

Use it to see what is available before opening or modifying files.

Useful forms to practice:

```bash
ls -l      # long/detailed listing
ls -a      # include hidden files
ls -la     # detailed listing including hidden files
ls -lh     # detailed listing with human-readable sizes
```

---

## Understanding `ls -l`

Example:

```text
-rw-r--r-- 1 harry developers 1024 Sep 12  notes.txt
```

Important fields include:

```text
-rw-r--r--   ← file type and permission information
1            ← hard-link count
harry        ← owner
 developers  ← group
1024         ← size in bytes
Sep 12       ← modification date/time
notes.txt    ← file name
```

The permissions part is only a preview for now. Permission-management commands such as `chmod` and `chown` have **not** been studied yet and are intentionally not documented as learned commands.
