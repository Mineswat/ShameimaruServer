1. **Set the Password**: Use `sudo passwd root` to create a password for the root account. 
    
2. **Enable SSH Access**: Edit `/etc/ssh/sshd_config` and change `PermitRootLogin` to `yes` (or `without-password` to allow only SSH key authentication). 
    
3. **Restart Service**: Run `sudo systemctl restart ssh` to apply changes
