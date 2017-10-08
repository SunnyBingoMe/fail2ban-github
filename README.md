# Usage
The following code considered that the earlier versions of fail2ban is not using 'jail.d' folder.
// Possible needed: `sudo apt-get update`
## ss by wget
```sh
sudo apt-get install -y -qq wget fail2ban && \
sudo wget https://raw.githubusercontent.com/SunnyBingoMe/fail2ban-github/master/filter.d_ss.conf -O /etc/fail2ban/filter.d/ss.conf && \
[ -d "/etc/fail2ban/jail.d" ] && \
sudo wget https://raw.githubusercontent.com/SunnyBingoMe/fail2ban-github/master/jail.d_ss.conf -O /etc/fail2ban/jail.d/ss.conf || \
sudo wget https://raw.githubusercontent.com/SunnyBingoMe/fail2ban-github/master/jail.d_ss.conf -O /etc/fail2ban/jail.local && \
sudo service fail2ban restart && \
/bin/sleep 2s && \
sudo iptables -L
```
Optional param for wget: `--no-check-certificate`

## ss by curl
```sh
sudo apt-get install -y -qq wget fail2ban && \
sudo curl -L --output /etc/fail2ban/filter.d/ss.conf https://raw.githubusercontent.com/SunnyBingoMe/fail2ban-github/master/filter.d_ss.conf && \
[ -d "/etc/fail2ban/jail.d" ] && \
sudo curl -L --output /etc/fail2ban/jail.d/ss.conf https://raw.githubusercontent.com/SunnyBingoMe/fail2ban-github/master/jail.d_ss.conf || \
sudo curl -L --output /etc/fail2ban/jail.local https://raw.githubusercontent.com/SunnyBingoMe/fail2ban-github/master/jail.d_ss.conf && \
sudo service fail2ban restart && \
/bin/sleep 2s && \
sudo iptables -L
```
