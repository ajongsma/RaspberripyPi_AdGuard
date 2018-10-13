# Raspberripi

# Download Etcher or Apple-Pi-Baker to Flash OS images to SD card(s)
##### https://etcher.io / https://www.tweaking4all.com/hardware/raspberry-pi/macosx-apple-pi-baker/

# Download Raspbian Stretch Lite image
##### https://www.raspberrypi.org/downloads/raspbian/

# Login:
##### $ UserID: pi
##### $ Password: raspberry

# sudo raspi-config
##### $ sudo raspi-config
##### > Interface Options > SSH > Yes
##### > Network Options > Wi-fi
##### > Boot Options -> B1 Desktop / CLI -> B2 Console Autologin
##### > Advanced Options -> A3 Memory Split -> Enter 16

# Upgrade installed packages
##### sudo apt-get update 
##### sudo apt-get upgrade
##### sudo apt-get autoremove
##### sudo apt-get autoclean

# Install git and net-tools packages 
##### sudo apt-get install git net-tools

# Pi-hole
##### https://pi-hole.net

# Pi-hole as All-Around DNS Solution
##### https://docs.pi-hole.net/guides/unbound/

# Other
###### https://blog.sleeplessbeastie.eu/2018/01/11/how-to-install-and-configure-pi-hole/
###### https://itchy.nl/raspberry-pi-3-with-openvpn-pihole-dnscrypt
###### https://www.ct.nl/achtergrond/versleutelde-dns-requests-met-pi-hole/
