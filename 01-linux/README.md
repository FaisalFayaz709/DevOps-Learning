# 01 - Linux

This section documents my Linux learning for the DevOps roadmap. The goal is to keep the repository honest and practical: topics I have learned are documented in detail, while topics I have not studied yet remain clearly marked as pending.

## Current learning checkpoint

| Topic | Status | What I currently know |
|---|---|---|
| Linux introduction | ✅ Covered | DevOps basics, Linux kernel, GNU/Linux utilities, shell, package manager, libraries, applications, Linux distributions, GNU vs shell, Apache concept |
| Filesystem/navigation | ✅ Beginner | `pwd`, `cd`, `ls`, `ls -l`, directories and basic navigation |
| File management | ✅ Beginner | `mkdir`, `mkdir -p`, `touch`, `vim`, `cp`, `cat`, `cat -n`, `less` |
| Users and groups | ✅ Beginner | `whoami`, `adduser`, `useradd`, `passwd`, `usermod`, `groups`, `su`, `exit`, `sudo` |
| Permissions | 🟡 Preview only | Reading the beginning of `ls -l`; permission-management commands have not been studied yet |
| Processes | ⏳ Not studied | Will be added after learning it |
| Services | 🟡 Concept only | I understand what Apache HTTP Server is; Linux service-management commands are not studied yet |
| Package management | ✅ Beginner | APT update/install/upgrade/purge and installed-package listing |
| Networking | ⏳ Not studied | Will be added after learning it |
| SSH | ✅ Concept covered | Secure remote shell, port 22, remote login idea, password/key authentication concept |
| Logs | ⏳ Not studied | Will be added after learning it |

> `mv` and `rm` are intentionally **not** documented as learned commands yet because I have not studied them.

## Structure

```text
01-linux/
├── README.md
├── notes/
│   ├── 01-linux-introduction.md
│   ├── 02-filesystem.md
│   ├── 03-file-management.md
│   ├── 04-users-groups.md
│   ├── 05-permissions.md
│   ├── 06-processes.md
│   ├── 07-services.md
│   ├── 08-package-management.md
│   ├── 09-networking.md
│   ├── 10-ssh.md
│   └── 11-logs.md
├── commands/
│   └── linux-command-cheatsheet.md
├── labs/
└── projects/
```

## Learning method

For each topic:

1. Understand the concept.
2. Practice the commands.
3. Write or update the notes.
4. Perform a small lab.
5. Commit and push the learning to GitHub.

This folder will grow as I learn new Linux topics.
