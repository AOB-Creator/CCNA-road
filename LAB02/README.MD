1. switch> 📡 User EXEC Mode
2. switch# 📡 Privileged EXEC Mode
3. switch(configure)# 📡 Global Configuration Mode
4. switch(configure-if)#  📡 Additional Sub-Modes:


✅  Changing modes

switch> - switch#
switch> enable

switch# -> switch(configure)#
switch# configure terminal

switch(config)#  ->  switch (config-if)# 
switch(config)# interface FastEthernet0/1



📡 Privileged EXEC Mode

switch# show running-config
switch# show ip interface brief
switch# show version
switch# copy running-config startup-config
switch# write
switch# reload


📡 Global Configuration Mode ⬇️

switch(config)# hostname 1cisco_floor
1cisco_floor(config)# nohostname
switch(config)# enable password cisco
switch(config)# enable secret password cisco
switch(config)# no enable password
switch(config)# no enable secret
switch(config)# line console 0
switch(config)# service password-encryption
switch(config)# banner motd #Unauthorized access is prohibited#
switch(config)# interface vlan 1
switch(config)# no shutdown
switch(config)# ip address 192.168.1.100 255.255.255.0








