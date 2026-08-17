# SSH Hardening Scripts
This folder contains the commands used to configure SSH hardening.

## SSH Configuration Test
sshd -t

### SSH Service
systemctl restart ssh
systemctl status ssh

#### SSH Certificate Login
ssh -i <user-private-key> <user>@<server>

##### Fail2ban
systemctl status fail2ban
fail2ban-client status
fail2ban-client status sshd
