# AWS EC2 SSH Key Pair Connection Guide

A beginner-friendly, step-by-step guide to connecting to an **AWS EC2 Linux instance using SSH key pairs** on Windows.

## 📌 Project Overview

This project explains how to securely connect to an Amazon EC2 instance using four different SSH clients: Windows Command Prompt (CMD), Git Bash, MobaXterm, and PuTTY.

It covers instance creation, key pair configuration, SSH connectivity, connection verification, and troubleshooting common errors.

## 🎯 Objectives

- Understand SSH and SSH key-pair authentication.
- Launch an Amazon EC2 Linux instance.
- Create and securely manage an SSH key pair.
- Connect to EC2 using four different SSH clients.
- Troubleshoot common SSH connection issues.
- Learn basic AWS cloud security practices.

## 🛠️ Technologies and Tools

- **Cloud Platform:** Amazon Web Services (AWS)
- **Compute Service:** Amazon EC2
- **Operating System:** Amazon Linux 2023
- **Protocol:** SSH (Secure Shell)
- **SSH Port:** 22
- **Clients:** Windows CMD, Git Bash, MobaXterm, PuTTY
- **Key Formats:** `.pem` and `.ppk`

## 🏗️ Architecture

```text
+-------------------------+
|      Windows PC         |
|                         |
|  Private SSH Key        |
|  (.pem / .ppk)          |
+------------+------------+
             |
             | Encrypted SSH Connection
             | Port 22
             |
+------------v------------+
|      AWS EC2 Instance   |
|                         |
|      Amazon Linux 2023  |
|      SSH Authentication |
|      User: ec2-user     |
+-------------------------+
```

## 🔑 SSH Connection Methods

### 1. Windows Command Prompt (CMD)

Open CMD and navigate to the folder containing your private key.

```cmd
cd Downloads
ssh -i "my-all-key.pem" ec2-user@YOUR_EC2_PUBLIC_DNS
```

Replace `YOUR_EC2_PUBLIC_DNS` with your instance's current public DNS name.

### 2. Git Bash

Open Git Bash and run:

```bash
cd ~/Downloads
chmod 400 my-all-key.pem
ssh -i "my-all-key.pem" ec2-user@YOUR_EC2_PUBLIC_DNS
```

### 3. MobaXterm

1. Open MobaXterm.
2. Select **Session → SSH**.
3. Enter your EC2 public IP address.
4. Set the username to `ec2-user`.
5. Set the port to `22`.
6. Under Advanced SSH settings, select your `.pem` private key.
7. Click **OK** to connect.

### 4. PuTTY

PuTTY uses
