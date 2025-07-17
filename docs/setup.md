# Setup.md

This section details the initial setup phase of the Ubuntu Server LTS virtual machine after installation. It includes information on logging in, updating, configuring SSH, and installing essential tools.

First boot and login

After rebooting, log in to the system with the username and password you made during installation. You will see the default MOTD summary, which shows system health and package information.

Network connection

Confirm the VM received a valid IP address:

```
ip a
```

If the interface is missing or inactive, use the text-based network manager:

```
sudo nmtui
```

Update packages

Ensure the system is up to date:

```
sudo apt update && sudo apt upgrade -y
```

Install common utilities

These tools are useful for administration and diagnostics:

```
sudo apt install -y fastfetch curl vim net-tools
```

Run fastfetch to verify successful installation:

```
fastfetch
```

SSH key generation (host machine)

On the host (Pop!_OS), generate a dedicated SSH key for this lab:

```
ssh-keygen -t ed25519 -f ~/.ssh/id_ed25519_vm
```

Leave the passphrase blank unless you want to add an extra layer of security.

Copy public key to server

Send the public key to the Ubuntu VM:

```
ssh-copy-id -i ~/.ssh/id_ed25519_vm.pub labadmin@192.168.122.198
```

Test SSH connection:

```
ssh -i ~/.ssh/id_ed25519_vm labadmin@192.168.122.198
```

If successful, the session should open without a password prompt.

Enable ssh service at boot

Ensure the OpenSSH service persists after reboot:

```
sudo systemctl enable ssh
```

Verify the service status:

```
sudo systemctl status ssh
```

Setup complete

At this point, the system is:

- Accessible via SSH using key-based authentication
- Updated with the latest packages
- Equipped with helpful command-line tools

You are now ready to begin hardening and firewall configuration.

