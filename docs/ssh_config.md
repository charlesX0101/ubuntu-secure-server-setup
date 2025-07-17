# SSH_Config.md

This section outlines the SSH configuration changes made to enhance security on the Ubuntu Server. The aim is to decrease the attack surface and require key-based authentication.

Edit the sshd_config file

Open the SSH daemon configuration:

sudo nano /etc/ssh/sshd_config

Modify or uncomment the following lines:

PermitRootLogin no
PasswordAuthentication no
PubkeyAuthentication yes
AuthorizedKeysFile .ssh/authorized_keys

These changes disable root login, enforce key-based authentication, and confirm the expected authorized keys location.

Save and exit the file, then restart the SSH service:

sudo systemctl restart ssh

Verify active configuration

Ensure the server is using the correct settings:

sudo systemctl status ssh

To confirm key-based login is working and passwords are rejected, attempt to SSH from the host:

ssh -i ~/.ssh/id_ed25519_vm labadmin@192.168.122.198

If key-based authentication works and passwords are disabled, the connection should succeed without prompting for a password.

Final check

You can also use the following command to confirm SSH is listening and properly configured:

ss -tulnp | grep ssh

Expected output includes:

LISTEN 0 128 *:22 *:* users:(("sshd",pid,...))

SSH configuration complete

The system now only allows access with SSH keys. It does not permit root logins and follows stricter defaults. These changes help defend the system against brute-force and credential-based attacks.

