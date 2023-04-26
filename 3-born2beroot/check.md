# Born2beRoot

## First Checks
- [ ] Check if sha1sum is equal
- [ ] Check linux release $> lsb_release -a || cat /etc/os-release
- [ ] Check the partitions $> lsblk
- [ ] Check if sudo in on $> dpkg -l | grep sudo
- [ ] Check the hostname $> hostnamectl
- [ ] Check the password policy $> sudo chage -l username
- [ ] Check UFW $> sudo ufw status numbered
- [ ] Check SSH $> sudo systemctl status ssh
- [ ] Check sudo log $> cd /var/log/sudo/sudo.log | cat -e
- [ ] Check if user is on sudo $> getent group sudo
- [ ] Check if user is on user42 $> getent group user42
- [ ] Run monitoring - cd /usr/local/bin && bash monitoring.sh

## During evaluation:
- [ ] Create a new user $> sudo adduser username
- [ ] Create a new group $> sudo groupadd evaluating
- [ ] Add the user to new group $> sudo usermod -aG evaluating username
- [ ] Add the user to sudo $> sudo usermod -aG sudo username
- [ ] Check the change $> getent group evaluating
- [ ] Change the hostname $> sudo hostnamectl set-hostname name && sudo nano /etc/hosts
- [ ] reboot, see and see the change $> sudo reboot | hostnamectl
- [ ] Restore the original hostname
- [ ] Add the 8080 port $> sudo ufw allow 8080
- [ ] See the changes $> sudo ufw status numbered
- [ ] Delete the port added $> sudo ufw delete 4
- [ ] Connect to new user $> ssh new_user@127.0.0.1 -p 4242
- [ ] Try to connect to root (Must ne fail) - ssh hostname@127.0.0.1 -p 4242 
- [ ] Change time to 1 - sudo crontab -u root -e 
- [ ] Stop cron - sudo cronstop
- [ ] Restart cron - sudo cronstart