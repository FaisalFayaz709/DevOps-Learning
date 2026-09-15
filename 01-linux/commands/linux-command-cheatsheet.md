# Linux Command Cheat Sheet

This cheat sheet separates commands I have already learned from useful commands introduced as the next practice within the same topics.

Status:

- ✅ **Learned/discussed** - already covered in my current learning.
- 🟡 **Next practice** - useful command from a topic I have started, but I should practice it before claiming mastery.

---

## Navigation and Listing

| Status | Command | What it does | Why / when I use it |
|---|---|---|---|
| ✅ | `pwd` | Prints the current working directory | Use when I need to confirm where I am in the filesystem |
| ✅ | `cd /path` | Changes the current directory | Use to move to the directory I want to work in |
| 🟡 | `cd ..` | Goes to the parent directory | Use to move one level up |
| 🟡 | `cd ~` | Goes to the current user's home directory | Quick way to return home |
| 🟡 | `cd -` | Returns to the previous directory | Useful when switching back and forth between two locations |
| ✅ | `ls` | Lists directory contents | Use to see files/directories in the current location |
| ✅ | `ls -l` | Shows a detailed/long listing | Use to see owner, group, size, time, and permission information |
| 🟡 | `ls -a` | Includes hidden entries | Use when hidden files such as `.gitignore` need to be seen |
| 🟡 | `ls -la` | Detailed listing including hidden entries | Useful for troubleshooting repository/config files |
| 🟡 | `ls -lh` | Long listing with human-readable sizes | Easier way to read file sizes such as KB/MB/GB |

---

## Directories and Files

| Status | Command | What it does | Why / when I use it |
|---|---|---|---|
| ✅ | `mkdir projects` | Creates a directory | Use to organize files into a new folder |
| ✅ | `mkdir -p devops/linux/labs` | Creates nested directories and missing parents | Use when building a complete directory tree in one command |
| ✅ | `touch notes.md` | Creates an empty file if missing; otherwise updates timestamps | Use to quickly create a file before editing it |
| ✅ | `cp source.txt backup.txt` | Copies a file | Use to duplicate or back up a file |
| 🟡 | `cp -r source/ destination/` | Copies a directory recursively | Use when copying a directory and everything inside it |

### Intentionally not covered yet

`mv` and `rm` are not documented as learned commands because I have not studied them yet.

---

## Reading Files

| Status | Command | What it does | Why / when I use it |
|---|---|---|---|
| ✅ | `cat file.txt` | Prints the whole file | Quick inspection of small files |
| ✅ | `cat -n file.txt` | Prints the file with line numbers | Useful when referring to a specific line |
| ✅ | `less file.txt` | Opens scrollable file viewing | Better for large files/configuration output |
| 🟡 | `head file.txt` | Shows the beginning of a file | Quick check of the first lines |
| 🟡 | `tail file.txt` | Shows the end of a file | Useful for recent lines or output |
| 🟡 | `tail -f app.log` | Follows new lines as they are appended | Commonly used to watch a changing log file |

Useful `less` controls:

```text
Space / Page Down  → forward
b                  → backward
/search-text       → search
q                  → quit
```

---

## Vim

Start Vim:

```bash
vim notes.txt
```

| Status | Vim key/command | What it does | Why / when I use it |
|---|---|---|---|
| ✅ | `i` | Enters Insert mode | Use when I want to type/edit text |
| ✅ | `Esc` | Returns to Normal mode | Use before entering Vim commands such as `:wq` |
| ✅ | `:w` | Writes/saves the file | Save without leaving Vim |
| ✅ | `:q` | Quits Vim | Leave when there are no unsaved changes |
| ✅ | `:wq` | Saves and quits | Normal way to save changes and exit |
| ✅ | `:q!` | Quits without saving | Discard unwanted changes and exit |

---

## Users, sudo, and Groups

| Status | Command | What it does | Why / when I use it |
|---|---|---|---|
| ✅ | `whoami` | Shows the current effective username | Verify which account I am using |
| ✅ | `sudo <command>` | Runs an allowed command with elevated privileges | Administrative tasks that a normal user cannot perform |
| ✅ | `sudo adduser harry` | Creates a user interactively on Debian/Ubuntu | Convenient manual user creation |
| ✅ | `sudo useradd -m rohan` | Creates user `rohan` and home directory | Lower-level/direct user creation |
| ✅ | `sudo passwd rohan` | Sets/changes `rohan`'s password | Configure/reset user password |
| ✅ | `su - harry` | Switches to `harry` with a login-style environment | Test/work as another user |
| ✅ | `exit` | Ends the current shell/session | Return from `su`, end SSH, or close the current shell |
| ✅ | `sudo usermod -aG sudo harry` | Appends `harry` to the `sudo` supplementary group | Grant sudo-group membership on Ubuntu/Debian |
| ✅ | `sudo groupadd developers` | Creates the `developers` group | Group multiple users for shared administration/access |
| ✅ | `sudo usermod -aG developers rohan` | Appends `rohan` to the `developers` group | Add a user to a supplementary group without dropping existing memberships |
| ✅ | `groups rohan` | Shows group memberships for `rohan` | Verify group membership |
| 🟡 | `groups` | Shows current user's groups | Quick check of my own group memberships |
| 🟡 | `id rohan` | Shows UID, GID and groups | More detailed identity/group verification |
| 🟡 | `getent passwd rohan` | Queries the system user database | Verify the user exists and inspect its account entry |
| 🟡 | `getent group developers` | Queries the system group database | Verify the group and see group information/members |

### Important `usermod -aG` breakdown

```text
-a  → append to existing supplementary groups
-G  → supplementary group list
```

Using `-G` without `-a` can replace supplementary group membership, so `-aG` is important when I mean **add this group and keep the existing ones**.

---

## Package Management (APT)

| Status | Command | What it does | Why / when I use it |
|---|---|---|---|
| ✅ | `apt` | APT command-line package interface | Entry point for package-management operations |
| ✅ | `sudo apt update` | Refreshes package-index metadata | Run before install/upgrade when I want current repository information |
| ✅ | `sudo apt upgrade` | Upgrades installed packages | Apply available package updates after refreshing metadata |
| ✅ | `sudo apt install <package>` | Installs software and dependencies | Use when adding software to the machine |
| ✅ | `sudo apt purge <package>` | Removes package plus package-managed config | Use when I want a more complete uninstall |
| ✅ | `apt list --installed` | Lists installed packages | Verify installed software; this is the corrected form instead of `apt --installed` |
| ✅ | `sudo apt-get update` | Refreshes package metadata using `apt-get` | Recognize/use the lower-level/stable interface often seen in scripts and docs |
| 🟡 | `apt search <name>` | Searches available packages | Find the package name before installation |
| 🟡 | `apt show <package>` | Shows package details | Inspect description/version/dependencies |
| 🟡 | `sudo apt remove <package>` | Removes package while generally keeping package config | Use when uninstalling without purging package-managed configuration |
| 🟡 | `sudo apt autoremove` | Removes no-longer-needed auto-installed dependencies | Clean unused dependencies after package changes |

Example discussed:

```bash
sudo apt install apache2
```

This installs Apache HTTP Server on Ubuntu/Debian-based systems.

---

## SSH

| Status | Command | What it does | Why / when I use it |
|---|---|---|---|
| ✅ | `ssh username@server-address` | Opens an encrypted remote shell session | Use to administer a remote Linux server from my own machine |
| ✅ | `ssh ubuntu@SERVER_IP` | Example SSH login form | Common pattern for a remote Ubuntu server/VM |

SSH commonly uses TCP port `22` by default.

After connecting, commands typed in the session execute on the remote server.

---

## Concepts with no command practice yet

These topics are present in the Linux folder but still pending hands-on study:

- Linux permission management
- Processes
- Linux service management
- General Linux networking
- Logs/log-management tooling
- SSH key generation/configuration lab
- `mv`
- `rm`
