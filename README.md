# foundry-helpers
random collection of things for foundry-vtt


systemd-unit file how to:
This is a simple way to have a dedicated foundry server running as a service using node js and a systemd unit file

1. follow the official installation guide for linux https://foundryvtt.com/article/installation/ up until "Running FVTT as a Service"

2. either copy the file from this repo or open your favourite text editor and put the info in. Adapt paths to accurately reflect your setup.

3. run 'sudo cp foundryvtt.service /etc/systemd/system' to copy the systemd unit file to your unit files
4. run 'sudo systemctl daemon-reload' to make sure systemd knows about the new unit file
5. run 'sudo systemctl start foundryvtt'

if everything was done correctly you should now get an "active" status when you execute 'sudo systemctl status foundryvtt'.

to permanently enable it (autostart after reboot) use 'sudo systemctl enable foundryvtt'

6. Done. Your foundry dedicated server should now autoboot on system restart and you can start, stop, enable, disable it like any other systemd service.

if you encounter any issues check the output of systemctl status, this should show the last lines of journald, if anything node-related is tripping you up,
here is a very handy guide on how to use systemd unit files for your node applications: https://nodesource.com/blog/running-your-node-js-app-with-systemd-part-1/

other links:
https://man7.org/linux/man-pages/man1/systemctl.1.html
