# Package Management with APT

A package manager installs, updates, removes, and tracks software and dependencies.

On Ubuntu/Debian-based Linux distributions, **APT** is commonly used.

---

## `apt`

```bash
apt
```

APT is a command-line frontend for package-management tasks such as updating package information, searching packages, installing software, upgrading installed packages, and removing packages.

Most system-changing APT operations require administrator privileges, so they are commonly run with `sudo`.

---

## `sudo apt update`

```bash
sudo apt update
```

### Why it is used

Downloads the latest package-index metadata from configured repositories.

### When to use it

Run it before installing/upgrading software when I want the system to know the latest available package versions.

> `apt update` updates the package **list/metadata**; it does not itself upgrade all installed packages.

---

## `sudo apt upgrade`

```bash
sudo apt upgrade
```

### Why it is used

Upgrades installed packages to available newer versions according to APT's upgrade rules.

### When to use it

Use it after refreshing package information with `apt update` when I want to apply available package upgrades.

---

## `sudo apt install <package>`

```bash
sudo apt install nginx
```

### Why it is used

Downloads and installs the requested package and required dependencies.

### When to use it

Use it when new software is needed on the system.

Example discussed while learning Apache:

```bash
sudo apt install apache2
```

This installs the Apache HTTP Server package on Ubuntu/Debian-based systems.

---

## `sudo apt purge <package>`

```bash
sudo apt purge nginx
```

### Why it is used

Removes the package and its package-managed configuration files.

### When to use it

Use it when I want a more complete package removal than a normal `remove` operation.

---

## Correct installed-package command

The correct form to list installed packages is:

```bash
apt list --installed
```

The earlier form `apt --installed` is incomplete/incorrect for this purpose.

### Why it is used

Lists packages currently recorded as installed.

### When to use it

Use it when checking whether software is installed or reviewing installed packages.

---

## `sudo apt-get update`

```bash
sudo apt-get update
```

### Why it is used

Like `apt update`, it refreshes package metadata from configured repositories.

### `apt` vs `apt-get`

For beginner interactive administration, `apt` is convenient and human-friendly. `apt-get` is an older, lower-level interface with stable behavior that is still common in scripts, Dockerfiles, documentation, and automation.

I do not need to replace `apt` with `apt-get`; I only need to recognize both.

---

## Useful APT commands to practice next

These were identified as useful additions from the same package-management topic:

```bash
apt search nginx
apt show nginx
sudo apt remove nginx
sudo apt autoremove
```

- `apt search nginx` - search available package names/descriptions.
- `apt show nginx` - display package details.
- `apt remove nginx` - remove the package while generally leaving package-managed configuration files.
- `apt autoremove` - remove dependencies that were installed automatically and are no longer needed.

These are marked as **next-practice commands**, not commands I am claiming to have mastered already.
