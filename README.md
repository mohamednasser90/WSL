# WSL

» `sudo systemctl daemon-reload`

System has not been booted with systemd as init system (PID 1). Can't operate.
Failed to connect to bus: Host is down

==============================================

Edit*

1. Open `/etc/wsl.conf` with any editor:

`sudo nano /etc/wsl.conf`

2. Add the following contents and save them

`[boot]
systemd=true`

3. Close the Linux window
4. Execute the following command in PowerShell

`wsl --shutdown`

`wsl`

5. Problem Solving

==============================================

just try:

`sudo apt-get update && sudo apt-get install -yqq daemonize dbus-user-session fontconfig`

`sudo daemonize /usr/bin/unshare --fork --pid --mount-proc /lib/systemd/systemd --system-unit=basic.target`

`exec sudo nsenter -t $(pidof systemd) -a su - $LOGNAME`

`snap version`
