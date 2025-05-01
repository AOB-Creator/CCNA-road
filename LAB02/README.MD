# From User EXEC to Privileged EXEC
switch> enable

# From Privileged EXEC to Global Configuration
switch# configure terminal

# From Global Configuration to Interface Configuration
switch(config)# interface FastEthernet0/1


![Timeline2_shutterstock_668209624](https://github.com/AOB-Creator/CCNA-road/blob/first-project/LAB02/image.png?raw=true)

#✅  Changing modes

switch> - switch#
switch> enable

switch# -> switch(configure)#
switch# configure terminal

switch(config)#  ->  switch (config-if)# 
switch(config)# interface FastEthernet0/1



#📡 Privileged EXEC Mode

switch# show running-config
switch# show ip interface brief
switch# show version
switch# copy running-config startup-config
switch# write
switch# reload


#📡 Global Configuration Mode ⬇️

switch(config)# hostname 1cisco_floor        # Set hostname
1cisco_floor(config)# no hostname            # Remove hostname

switch(config)# enable password cisco        # Set enable password
switch(config)# enable secret cisco          # Set encrypted enable password
switch(config)# no enable password           # Remove enable password
switch(config)# no enable secret             # Remove enable secret

switch(config)# service password-encryption  # Encrypt passwords
switch(config)# banner motd #Unauthorized access is prohibited#  # Set login banner

switch(config)# interface vlan 1             # Access VLAN 1
switch(config-if)# no shutdown               # Enable the interface
switch(config-if)# ip address 192.168.1.100 255.255.255.0  # Assign IP









