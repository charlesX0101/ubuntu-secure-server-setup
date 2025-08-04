[[/CharlesX0101]](https://charlesx0101.com/) [[/About]](http://charlesx0101.com/about) [[/Labs]](https://charlesx0101.com/labs) [[/Projects]](https://charlesx0101.com/projects) [[/Contact]](https://charlesx0101.com/contact) 

# Ubuntu Secure Server Setup

This lab shows a clean, simple, and security-focused setup of Ubuntu Server LTS in a virtual machine using QEMU. It covers the steps from partitioning and installation to SSH hardening and firewall setup. This project is part of a larger effort to highlight practical system administration and basic cybersecurity skills through reproducible labs.


## Purpose

The goal of this lab is to imitate a real-world Ubuntu Server deployment and apply initial hardening techniques right after setup. The result is a fully functional virtual server with SSH access that is secured by public key authentication and a basic firewall policy.

## Objectives

- Install Ubuntu Server LTS with a custom disk partition layout
- Enable and verify OpenSSH server functionality
- Configure SSH for secure, key-based authentication
- Set up a basic UFW (Uncomplicated Firewall) rule set
- Document each step with screenshots and config files
- Practice clean Git-based documentation suitable for a job portfolio

## Lab Environment

- **Host OS**: Pop!_OS (Linux)
- **Virtualization**: QEMU with Virt-Manager
- **Guest OS**: Ubuntu Server LTS
- **Architecture**: x86_64
- **Network**: User-mode NAT with assigned IP address

## Features

- Manual partitioning: `/boot`, `/`, `/home`, and `swap`
- Static IP (via DHCP lease reservation or manual config)
- SSH login using ed25519 public key
- UFW configured to allow only port 22
- Password-based SSH login disabled
- Clean project directory with reusable files

## Directory Structure

```
ubuntu-secure-server-setup/
├── README.md
├── LICENSE
├── metadata.json
├── configs/
│   └── ssh.config.hardened
├── docs/
│   ├── introduction.md
│   ├── installation.md
│   ├── setup.md
│   ├── ssh_config.md
│   ├── firewall.md
│   └── conclusion.md
└── screenshots/
    ├── 01_partition_layout.png
    ├── 02_curtin_install_log.png
    ├── 03_login_tty1_screen.png
    ├── 04_ssh_host_view.png
    ├── 05_logged_in_motd_summary.png
    ├── 06_ufw_status_verbose.png
    └── 07_sshd_config_hardening.png

```

## Screenshots

Each step of the setup process is documented with labeled screenshots, including:

- Disk partitioning layout
- Installation log
- First TTY login
- SSH session from host
- MOTD and system summary
- UFW status
- SSH configuration file

## Use Case

This lab is intended for junior system administrators, IT generalists, and cybersecurity beginners who want to build hands-on experience in server setup and network service hardening. It is also suitable as a portfolio piece to demonstrate practical knowledge beyond certifications.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Author

Charlesx0101
Focused on security, infrastructure, and clean system design.



