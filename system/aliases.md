# Shell Aliases

A collection of shell aliases created to simplify common Docker, Nextcloud, Raspberry Pi, and system administration tasks.

## Docker

alias dps='docker ps'
alias dpa='docker ps -a'
alias di='docker images'
alias dlog='docker logs'
alias dex='docker exec -it'
alias drestart='docker restart'

## Nextcloud

alias occ='docker exec -u www-data nextcloud php occ'
alias nc-log='docker logs nextcloud --tail 100'
alias nc-shell='docker exec -it nextcloud bash'

## Raspberry Pi

alias temp='vcgencmd measure_temp'
alias throttle='vcgencmd get_throttled'

## System

alias fullupgrade='sudo apt update && sudo apt full-upgrade -y'
alias clean='sudo apt autoremove -y && sudo apt autoclean'
alias aliaschange='nano ~/.bashrc'
alias c='clear'
alias shutdownnow='sudo shutdown now'
alias rebootnow='sudo reboot'
alias ll='ls -lah'

These aliases are convenience shortcuts and are not required for the operation of the homelab.
