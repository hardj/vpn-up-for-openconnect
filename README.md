# vpn-up-for-openconnect
VPN Up - Shell Script for OpenConnect for Mac OS | Command-Line Client for Cisco AnyConnect

### Features ###

A shell script for OpenConnect which allows:</br>
- to define multiple VPN connections, using different protocols</br>
- to run openconnect without entering the username and password</br>
- to run in the background / quietly</br>
- to authenticate with a certificate</br>
- to authenticate using Two-Factor Authentication (2FA) from Duo
- to check the status of the vpn connection

### What's new ###
- 🆒 added support for Two-Factor Authentication (2FA) from Duo
- added support for using different protocols</br>
- added options (start, stop, status, restart, status)</br>
- can check status of the vpn connection

### Sample configuration section ###
set options in file ~/.vpn/.env
```
VPN_NAME="VPN connection name"
VPN_HOST="vpn_server"
VPN_GROUP="vpn_group"
VPN_USER="vpn_login"
VPN_PASSWD=vpn_password
VPN_DUO2FAMETHOD=push #two factor method
SERVER_CERTIFICATE=""
PROTOCOL="anyconnect"
    # anyconnect       Compatible with Cisco AnyConnect SSL VPN, as well as ocserv (default)
    # nc               Compatible with Juniper Network Connect
    # gp               Compatible with Palo Alto Networks (PAN) GlobalProtect SSL VPN
    # pulse            Compatible with Pulse Connect Secure SSL VPN

BACKGROUND=TRUE
    # TRUE          Runs in background after startup
    # FALSE         Runs in foreground after startup
QUIET=TRUE
    # TRUE          Less output
    # FALSE         Detailed output
SUDO=FALSE
    # TRUE          
    # FALSE         
SUDO_PASSWORD=""

```

### Run VPN Up ###

1. Please make sure you have `openconnect` installed before moving on. Follow the instructions [here](https://formulae.brew.sh/formula/openconnect).
3. Copy the `vpn-up.command` file to the `bin` folder.
4. Create .env file in ~/.vpn 
5. Make an alias `alias vpn-up='~/bin/vpn-up.command start'` in `bash` or `zsh` shell. Follow the instructions [here](https://wpbeaches.com/make-an-alias-in-bash-or-zsh-shell-in-macos-with-terminal/?__cf_chl_jschl_tk__=60015f4af93b104457efe3f2c7cd70de60ea05aa-1620807543-0-Ab8kPRiPbnWqJwPgGZ3k9zQ7t6ZrVnGiWZZGwLH1zmtS0Z2_I9_4k3484HAUDxe0WrYTgXZcYJg86SM895qayJYySOYhh0XdTBtOZwfa-KKLrgR-KJ9rvQmIas6UVdqHdedjUmCgljtFoxzGKguvu1TZ0NA_WAt8FrrfYo8aYhaXFXFVPkhvarI2mI1vWHc06ROepAwLTHfibEXn6VIiC02c0s3RD_5h_NsByw_6eWHESbqdUTnahAA-ls6lgQ7wY556EShckoVIvPGgnLWlYb4diIXOKntvTKMrPAtndHnB1oGY9RC8tZlfDlRrdnB4d6aaKgyp1uKgL77BPmmuRP9TDI3cnqGJoKc9_-Og5t5H2mOPjgo7La9F6Nja6Pn6jnyExLDsYvoASWdOG6mlYdP8IVQ9MXKJcoYphsdiZNuv4WxieW9GY7rPIdMQ0y2Rq9Rae04fi0JFl7GdQKEbC0uEY5umB5Bd9Dsc1aY6xb85).
6. Run `vpn-up` to start and voilà.
