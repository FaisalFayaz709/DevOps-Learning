# Users and Groups

Linux is a multi-user operating system. Users identify accounts, while groups make it easier to assign access to multiple users together.

## `whoami`

```bash
whoami
```

### Why it is used

Shows the username of the current effective user.

### When to use it

Use it after logging in, switching users, or using a remote system when I want to confirm which account I am operating as.

---

## `sudo`

`sudo` runs an allowed command with elevated privileges, commonly as the root user.

Example:

```bash
sudo apt update
```

### Why it is used

Normal users should not have unrestricted administrative access all the time. `sudo` provides controlled elevation for administrative tasks.

### When to use it

Use it for tasks that require administrator privileges, such as installing packages, creating users/groups, or changing system configuration.

---

## `sudo adduser harry`

```bash
sudo adduser harry
```

### Why it is used

On Debian/Ubuntu systems, `adduser` is a user-friendly command that interactively creates a user account and normally creates the home directory and asks for account information/password.

### When to use it

Use it when manually creating a normal user on Debian/Ubuntu and I want the convenient interactive workflow.

---

## `sudo useradd -m rohan`

```bash
sudo useradd -m rohan
```

### Why it is used

`useradd` is a lower-level user-creation command. The `-m` option tells it to create the user's home directory.

### When to use it

Use it when I want more direct/control-oriented user creation, especially in administration or automation contexts.

After using `useradd`, I can set the user's password separately:

```bash
sudo passwd rohan
```

---

## `sudo passwd rohan`

```bash
sudo passwd rohan
```

### Why it is used

Sets or changes the password for the specified user.

### When to use it

Use it after creating an account with `useradd` when the account needs password authentication, or when resetting a user's password.

---

## `su - harry`

```bash
su - harry
```

### Why it is used

Switches to the `harry` user and starts a login-style environment for that user.

The `-` is important because it loads the target user's login environment, including the target home directory and shell environment.

### When to use it

Use it when testing what a command or file looks like from another user's account.

---

## `exit`

```bash
exit
```

### Why it is used

Ends the current shell/session.

### When to use it

Use it to leave a shell opened with `su`, end an SSH session, or close the current shell session.

---

## Add a User to the sudo Group

```bash
sudo usermod -aG sudo harry
```

Breakdown:

```text
usermod → modify an existing user
-a      → append; do not remove existing supplementary groups
-G      → specify supplementary group(s)
sudo    → group being added
harry   → user being modified
```

### Why it is used

On Ubuntu/Debian, membership in the `sudo` group normally allows the user to run permitted commands through `sudo`.

### When to use it

Use it when an existing user should receive administrative sudo access.

> Group membership changes may require the user to log out and log back in before the new membership is reflected in a fresh login session.

---

## Create a Group

```bash
sudo groupadd developers
```

### Why it is used

Creates a group named `developers`.

### When to use it

Use groups when multiple users should share ownership/access rules or be managed together.

---

## Add a User to a Group

```bash
sudo usermod -aG developers rohan
```

### Why it is used

Adds `rohan` to the supplementary group `developers` while preserving his existing supplementary groups.

### Why `-aG` matters

Using `-G` without `-a` can replace supplementary group membership instead of appending to it. For this use case, `-aG` is the safer intended form.

---

## Check a User's Groups

```bash
groups rohan
```

### Why it is used

Shows which groups the specified user belongs to.

### When to use it

Use it to verify that a group-membership change succeeded.

For the current user:

```bash
groups
```

---

## Useful verification commands to practice next

These are useful additions from the same users/groups topic:

```bash
id rohan
getent passwd rohan
getent group developers
```

- `id rohan` shows UID, primary GID, and group memberships.
- `getent passwd rohan` checks the system's user database for that user.
- `getent group developers` checks the system's group database and group membership information.

These are marked as **next-practice commands** rather than already-mastered commands.
