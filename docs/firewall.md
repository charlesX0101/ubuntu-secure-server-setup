# Firewall.md

This section explains how to set up a basic firewall using UFW (Uncomplicated Firewall) to protect the Ubuntu Server. UFW provides an easy way to work with iptables, making it simpler to manage firewall rules.

Enable UFW

Start by enabling the firewall:

sudo ufw enable

Set default policies

Block all incoming connections by default, and allow all outgoing:

sudo ufw default deny incoming
sudo ufw default allow outgoing

Allow SSH access

Permit SSH connections to ensure continued remote access:

sudo ufw allow 22/tcp

Enable logging

Activate UFW logging to monitor firewall activity:

sudo ufw logging on

Check firewall status

View the current rule set and defaults:

sudo ufw status verbose

Sample output:

Status: active
Logging: on (low)
Default: deny (incoming), allow (outgoing), disabled (routed)

To                         Action      From
--                         ------      ----
22/tcp (OpenSSH)           ALLOW IN    Anywhere
22/tcp (OpenSSH (v6))      ALLOW IN    Anywhere (v6)

Verify persistence

Reboot the server and confirm UFW remains active:

sudo systemctl status ufw

Firewall setup complete

At this stage, the system is protected by a basic firewall that allows only SSH and blocks all other incoming traffic. This setup works well for lab environments and can be expanded with specific rules as needed for services or segmentation.

