# SSH - Secure Shell

## What is SSH?

**SSH (Secure Shell)** is a protocol used to securely connect to another computer over a network and operate its command-line environment remotely.

This is important in DevOps because engineers frequently manage remote Linux servers and cloud virtual machines without being physically in front of them.

```text
Local Laptop
     │
     │ encrypted SSH connection
     ▼
Remote Linux Server
     │
     ▼
Remote shell
```

SSH commonly uses **TCP port 22** by default.

---

## Basic SSH command format

```bash
ssh username@server-address
```

Example form:

```bash
ssh ubuntu@SERVER_IP
```

### Why it is used

It starts a secure remote login session to the target machine.

### When to use it

Use SSH when administering a remote Linux server, such as a cloud VM/EC2 instance, from my own computer.

After the connection succeeds, commands such as `pwd`, `ls`, `cd`, or `sudo apt update` execute on the **remote server**, not on my local laptop.

---

## Why SSH is secure

SSH encrypts traffic between the client and server, protecting commands, authentication data, and session contents from being read as plain text in transit.

---

## SSH Authentication

SSH can authenticate users in different ways. Two common concepts are:

### Password authentication

A user provides the password for the remote account, if the server allows it.

### SSH key authentication

A key pair is used:

```text
Private key → kept secret on the client
Public key  → placed/authorized on the server
```

The private key should not be shared.

I have learned the concept of SSH and remote login, but I have **not yet completed a dedicated SSH hands-on lab**. Key-generation and SSH configuration commands will be added after I practice them.
