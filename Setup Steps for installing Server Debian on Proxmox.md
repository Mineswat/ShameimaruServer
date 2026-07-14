
1. [Install Debian 3](https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-13.5.0-amd64-netinst.iso) on promox local
2. create vm with at least 10GB, Q35,UEFI and over 2GB ram
3. Install debian with only SSH Server
4. sudo apt update && sudo apt upgrade -y
5. Install sudo ufw curl ca-certificates git ca-certificates wget command-not-found git build-essential  

```

ON ROOT
sudo apt install sudo
adduser <username> sudo

ssh-keygen -t ed25519 -C "admin@homelab"
ssh-copy-id youruser@<VM-IP>
# On the VM:
sudoedit /etc/ssh/sshd_config
# Set:
#   PermitRootLogin no
#   PasswordAuthentication no
#   PubkeyAuthentication yes
sudo systemctl restart ssh


```
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

#for Debian 13 Trixie
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian trixie stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
