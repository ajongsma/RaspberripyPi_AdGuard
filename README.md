# Raspberry Pi - PiHole edition

# Download Etcher or Apple-Pi-Baker to Flash OS images to SD card(s)
##### https://etcher.io / https://www.tweaking4all.com/hardware/raspberry-pi/macosx-apple-pi-baker/

# Download Raspbian Stretch Lite image
##### https://www.raspberrypi.org/downloads/raspbian/

# Terminal
## Login:
##### $ UserID: pi
##### $ Password: raspberry

## sudo raspi-config
##### $ sudo raspi-config
##### > 5) Interface Options > SSH > Yes
##### > 2) Network Options > Wi-fi
##### > 3) Boot Options > B1 Desktop / CLI -> B2 Console Autologin
##### > 4) Localisation Options > Change Timezone > 
##### > 7) Advanced Options -> A3 Memory Split -> Enter 16

## Upgrade firmware
##### $ sudo raspi-config > 8) Update
##### $ sudo rpi-update

## Upgrade packages and distribution
##### $ sudo apt-get update && sudo apt-get upgrade
##### $ sudo apt-get dist-upgrade

## Cleanup & Install extra tools
##### $ sudo apt-get install -y autoremove autoclean sysstat vnstat screen

## Locales
##### $ sudo dpkg-reconfigure locales
##### >> Enable: en_GB.UTF-8 UTF-8
##### >> Enable: en_US.UTF-8 UTF-8

## Enable NTP time
##### $ timedatectl set-ntp true && timedatectl status
##### $ timedatectl status

## Install AdGuard
##### $ cd $HOME
##### $ wget https://github.com/AdguardTeam/AdGuardHome/releases/download/v0.91/AdGuardHome_v0.91_linux_arm.tar.gz
##### $ tar xvf AdGuardHome_v0.91_linux_arm.tar.gz

## Determine HOSTNAME's IP Adres (write IP adres down for the next step)
##### hostname -I|xargs -n1

## Create file for the Launch service
##### $ sudo nano /etc/systemd/system/adguard-home.service
##### Paste the following text and replace host IP Adress 192.168.1.3 if needed, press CTRL+o to save file, CTRL+x to exit:
```
[Unit]
Description=AdGuard Home
After=syslog.target
After=network.target

[Service]
Type=simple
User=root
Group=root
WorkingDirectory=/home/pi/AdGuardHome
ExecStart=/home/pi/AdGuardHome/AdGuardHome --host 192.168.1.3
Restart=always

[Install]
WantedBy=multi-user.target
```

## Enable and Start Adguard
##### $ sudo systemctl enable adguard-home
##### $ sudo systemctl start adguard-home

## Visit the web interface (replace the IP address with the hosts IP if needed)
##### http://192.168.1.3:3000/

# Other / Notes
###### https://github.com/AdguardTeam/AdGuardHome/wiki/Raspberry-Pi
