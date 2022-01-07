Netplan is the default network manager now and uses yaml to configure. See [this](https://netplan.io/examples/) for more information.  

**All of this will need to be done with `sudo`**  
  
Find the config in `/etc/netplan/01-netcfg.yaml` or something similar  
If you have to make the file you will need to use `netplan generate` first (I think)
A file looks something like this:
```
network:
    version: 2
    renderer: networkd
    ethernets:
        enp3s0:
            dhcp4: yes
        enp4s0:
            dhcp4: no
            addresses:
                - 10.10.10.2/24
```
  
enp3s0 being dynamic and enp4s0 being static with `<address>/<subnet>`  (subnet needs to be prefix length so 255.255.255.0 is 24) 

After configuration there are two commands:  
  * `netplan apply` - this just straight up applies the setting   
  * `netplan try` - checks the config and provides a timeout before rejecting the new config.

