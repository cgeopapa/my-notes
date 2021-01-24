# Linux

## Extract tar.gz command

`tar -xvf archive.tar.gz -C /where/to/extract`

Where:

* `-x` extract
* `-v` print the names of the files being extracted on the terminal
* `-f` the file to extract
* `-C` where to extract

## Remove

### file

`rm path/to/file`

### directory

`rm -r path/to/directory`

Where:

* `-r` recursive
* `-f` no prompt before delete

## Edit PATH

1. `[code/nano] ~/.profile`
2. Add the new path `export PATH=/path/to/location:$PATH`
3. Reload PATH 
   1. `cd ~`
   2. `. ~/.profile`

## Add permanent alias

Edit file ~/.bashrc `code ~/.bashrc`

and add the line `alias name="command"`

finaly, run bashrc to load the new aliases `source ~/.bashrc`

## Find process that listens to a port

`netstat -ltnp | grep -w ':${PORT}'`

* `l` tells netstat to only show listening sockets
* `t` tells it to display tcp connections
* `n` instructs it show numerical addresses
* `p` enables showing of the process ID and the process name

## Custom service \(for on-startup\)

1. Edit `/etc/systemd/system/my-service.service`

   `sudo nano /etc/systemd/system/my-service.service`

   Paste:

   \`\`\`

   \[Unit\]

   Description=Run minecraft server

   \[Service\]

   User=azureuser

   WorkingDirectory=/home/azureuser

   ExecStart=/usr/bin/java -Xms2G -Xmx4G -jar papermc-1.16.4-335.jar

SuccessExitStatus=143 TimeoutStopSec=10 Restart=on-failure RestartSec=5

\[Install\] WantedBy=multi-user.target

````` 2. Restart```sudo systemctl daemon-reload`to load the new service 3.`sudo systemctl enable my-service\` to enable new service on startup

* `sudo journalctl -f -u my-service` check logs of running service

## Disable/Enable Desktop GUI
Disable
`systemctl set-default multi-user.target`

Enable
`systemctl set-default graphical.target`
