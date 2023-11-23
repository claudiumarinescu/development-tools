1. to clone repo from github execute (maybe you need to install git first). then navigate to that folder:

git clone https://github.com/PixlOne/logiops.git
cd logiops


2. Follow build instructions from repo. This step needs build-essentials:

mkdir build
cd build
cmake .. // install all missing libs
make
sudo make install


3. To create a system deamon which runs the driver in the background follow the instructions from here

create a file /etc/systemd/system/logid.service with the content
[Unit]
Description=Logitech Configuration Daemon

[Service]
Type=simple
ExecStart=/usr/local/bin/logid -c /etc/logid.cfg
User=root
#ExecReload=/bin/kill -HUP $MAINPID

[Install]
WantedBy=multi-user.target
4. You may want to configure the driver via the file /etc/logif.cfg. The following worked for my MX Master 2S. Other configs can be found on github or in the Archwiki. Here you can change the dpi manually in addition to adjusting the system mouse-speed setting.

5. Finally enable the service to run on system startup and start the service:

sudo systemctl enable logid
sudo systemctl start logid


6. To find out more info:

sudo logid -v

-------------------------------------------
https://github.com/PixlOne/logiops/wiki/CIDs
https://wiki.archlinux.org/index.php/Logitech_MX_Master
https://github.com/torvalds/linux/blob/master/include/uapi/linux/input-event-codes.h
