# Linux Permissions

## Current status: Preview only

I have **not studied Linux permission-management commands yet**. This file records only the permission information that appeared while learning `ls -l` so I do not incorrectly claim knowledge I have not covered.

Example:

```text
-rw-r--r-- 1 harry developers 1024 Sep 12 notes.txt
```

The first field contains the file type and permission bits. A useful high-level view is:

```text
-rw-r--r--
││  │  │
││  │  └── permissions for others
││  └───── permissions for the group
│└──────── permissions for the owner
└───────── file type
```

The letters commonly represent:

- `r` = read
- `w` = write
- `x` = execute
- `-` = permission not granted in that position

The same `ls -l` output also shows the file **owner** and **group**.

## Not covered yet

Commands for changing permissions and ownership are intentionally not documented yet. I will update this note after learning the permissions topic properly.
