
# SSH

The Secure Shell Protocol is a cryptographic network protocol for operating network services securely over an unsecured network. Its most notable applications are remote login and command-line execution. SSH applications are based on a client–server architecture, connecting an SSH client instance with an SSH server

### If working without LAN using USB data cable

+ Connect USB type C cable from __HOST__ to __TARGET__
+ Enter the command in __HOST__
```
ssh-keygen -R 192.168.55.1
```
+ Enter the command again in __HOST__
```
ssh <user>@192.168.55.1
```
+ Now just enter the username and then password

### If working without LAN 

+ Enter the command in __HOST__
```
ssh <user>@192.168.55.1
```
+ Now just enter the username and then password

# VNC

VNC (Virtual Network Computing) enables you to control your Jetson developer kit from another computer on the same network, by viewing and interacting with the desktop of the developer kit from the other computer. </br>

Execute the following commands to enable the VNC server:

+ Enable the VNC server to start each time you log in
```
mkdir -p ~/.config/autostart
cp /usr/share/applications/vino-server.desktop ~/.config/autostart
```
+ Configure the VNC server
```
gsettings set org.gnome.Vino prompt-enabled false
gsettings set org.gnome.Vino require-encryption false
```

+ Set a password to access the VNC server
```
gsettings set org.gnome.Vino authentication-methods "['vnc']"
```

+ Replace thepassword with your desired password
```
gsettings set org.gnome.Vino vnc-password $(echo -n 'thepassword'|base64)
```
+ Reboot the system so that the settings take effect
```
sudo reboot
```
+ The VNC server is only available after you have logged in to Jetson locally. If you wish VNC to be available automatically, use the system settings application to enable automatic login.



