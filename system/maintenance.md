# System Maintenance

Commands and procedures used for routine administration of the Raspberry Pi homelab.

## System Updates

sudo apt update
sudo apt full-upgrade -y

## Cleanup

sudo apt autoremove -y
sudo apt autoclean

## Docker

docker ps

docker ps -a

docker logs <container-name>

## Nextcloud

docker exec -u www-data nextcloud php occ

docker exec -it nextcloud bash

## System Monitoring

vcgencmd measure_temp

vcgencmd get_throttled

## Network and Security Checks

sudo ss -tulpn

sudo ufw status verbose

sudo systemctl status fail2ban

These commands were used during routine administration and troubleshooting of the homelab.
