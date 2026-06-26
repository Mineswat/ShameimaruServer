

```
sudo apt update
sudo apt install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc


#for Debian 13 Trixie
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian trixie stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update

sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```


how to allow root ssh

1. sudo passwd root. create a root password
2. enable ssh password root to be SSH'D by  
```
   nano /etc/ssh/sshd_config 
   # find PermitRootLogin to
```


. **Set the Password**: Use `sudo passwd root` to create a password for the root account. 
    
2. **Enable SSH Access**: Edit `/etc/ssh/sshd_config` and change `PermitRootLogin` to `yes` (or `without-password` to allow only SSH key authentication). 
    
3. **Restart Service**: Run `sudo systemctl restart ssh` to apply changes
