# Linux Introduction

## What is DevOps?

**DevOps = Development + Operations.**

DevOps is a combination of practices, tools, collaboration, and automation used to help teams build, test, release, deploy, operate, and monitor software reliably.

A simplified software-delivery flow is:

```text
Developer
   ↓
Git / GitHub
   ↓
CI/CD
   ↓
Build and Test
   ↓
Docker / Artifact
   ↓
Cloud or Linux Server
   ↓
Application
   ↓
Monitoring
```

A DevOps engineer commonly works on questions such as:

- Where will the application run?
- How will servers and cloud infrastructure be created?
- How will new code be tested and deployed?
- How can deployments be automated?
- How will configuration be kept consistent?
- How will failures, logs, and system health be monitored?

Linux is important in DevOps because many servers, containers, cloud workloads, CI/CD runners, and infrastructure tools run on Linux.

---

## What is Linux?

Linux itself is primarily an **open-source kernel**. A usable Linux operating system contains the Linux kernel plus many other components.

```text
Linux Kernel
    +
GNU/Linux utilities and other system tools
    +
Package manager
    +
Shell
    +
Libraries
    +
Applications
    ↓
Linux Distribution
```

Examples of Linux distributions include Ubuntu, Debian, Fedora, Red Hat Enterprise Linux, Rocky Linux, and Amazon Linux.

---

## 1. Linux Kernel

The **kernel** is the core part of the operating system. It sits between software and hardware and controls access to system resources.

```text
Applications
    ↓
Linux Kernel
    ↓
Hardware
```

The kernel is responsible for major tasks such as:

- **CPU/process scheduling** - decides when running processes get CPU time.
- **Memory management** - manages RAM used by programs.
- **Device management** - communicates with hardware through drivers.
- **Filesystem access** - provides the mechanisms programs use to work with files and storage.
- **Networking** - handles low-level network communication such as interfaces, routing, TCP/IP, and sockets.
- **Security/isolation** - controls what processes and users are allowed to access.

Example: when `cat notes.txt` reads a file, the `cat` program ultimately asks the kernel to access the file on storage.

---

## 2. GNU/Linux Utilities

The Linux kernel alone does not provide all the everyday commands needed to conveniently operate a system. Linux distributions include many user-space utilities.

The **GNU Project** provides many traditional command-line tools used on GNU/Linux systems. Examples include tools such as:

```text
ls
cp
cat
mkdir
pwd
```

These commands are programs, not commands built directly into the Linux kernel.

A simplified flow is:

```text
User
 ↓
Shell
 ↓
Utility such as ls
 ↓
Linux kernel
 ↓
Filesystem / hardware
```

> Not every command on a Linux system comes from GNU, but GNU provides an important collection of tools used by many Linux distributions.

---

## 3. Shell

A **shell** is a program that accepts commands from the user and helps execute them.

Common shells include:

- Bash
- Zsh
- `sh`
- Fish

Example:

```bash
mkdir devops
```

The shell reads the command, resolves what should be run, and starts the appropriate program.

```text
You
 ↓
Shell (for example Bash)
 ↓
mkdir program
 ↓
Linux kernel
 ↓
Filesystem
```

### Terminal vs shell

They are related but not identical:

- **Terminal**: the window/interface in which you type.
- **Shell**: the program running inside the terminal that interprets commands.

---

## 4. GNU vs Shell

GNU and a shell are not competing concepts.

- **GNU** is a large software project/ecosystem that provides many tools.
- A **shell** is one type of program used to interpret commands.
- **Bash is a GNU program** and is also a shell.

A useful mental model:

```text
GNU Project
├── Bash     ← shell
├── ls       ← utility
├── cp       ← utility
├── cat      ← utility
├── mkdir    ← utility
└── many other programs
```

So when using Bash to run `ls`, a GNU shell can be launching a GNU utility.

---

## 5. Package Manager

A **package manager** installs, updates, removes, and tracks software packages and their dependencies.

On Ubuntu/Debian-based systems, APT is commonly used.

Example:

```bash
sudo apt install apache2
```

Conceptually:

```text
User
 ↓
APT
 ↓
Package repositories
 ↓
Download package + required dependencies
 ↓
Install software
```

Package managers save administrators from manually downloading, compiling, copying, and tracking every piece of software.

---

## 6. Libraries

A **library** contains reusable code that programs can use instead of implementing the same functionality from scratch.

Applications may depend on libraries for tasks such as:

- encryption
- networking
- compression
- database access
- text processing

```text
Application
    ↓ uses
Library
    ↓
Reusable functionality
```

When software requires another package or library to work, that requirement is called a **dependency**. A package manager can often install required dependencies automatically.

---

## 7. Applications

Applications are programs used to perform useful tasks on top of the operating system.

Examples include:

- Git
- Vim
- Nginx
- Apache HTTP Server
- Docker
- PostgreSQL

Applications are not the Linux kernel; they run in user space and use operating-system services provided through the kernel and libraries.

---

## 8. Linux Distribution

A **Linux distribution (distro)** is a usable operating system assembled around the Linux kernel.

It normally combines:

```text
Linux kernel
+
system utilities
+
shell
+
libraries
+
package-management system
+
default configuration and system software
+
applications/tools
=
Linux distribution
```

Examples:

- Ubuntu
- Debian
- Fedora
- Red Hat Enterprise Linux (RHEL)
- Rocky Linux
- Amazon Linux

A useful analogy is that the **kernel is the engine**, while the **distribution is the complete vehicle** assembled around that engine.

---

## What is Apache?

In this learning context, **Apache** means **Apache HTTP Server**.

Apache is a **web server application**. It receives HTTP/HTTPS requests and can return website content or proxy requests to applications.

```text
Browser
   ↓ HTTP/HTTPS request
Apache HTTP Server
   ↓
Website content / application
   ↓
Response to browser
```

Common default web ports are:

- HTTP: `80`
- HTTPS: `443`

Apache is an application, not part of the Linux kernel. When installed on a Linux machine, it normally runs in the background as a service. Service-management commands have not been studied yet.
