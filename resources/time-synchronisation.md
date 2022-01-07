# Network Time Protocol
NTP is a good way to synchronise clocks across different machines (and the only one I'm really aware of).

# Install
On ubuntu:  
`sudo apt install chrony`  

# Setup
Edit `/etc/chrony/chrony.conf` to add/remove server lines.   
There will be a line of servers shown each looking like:
`pool 2.ubuntu.pool.ntp.org iburst maxsources 2`  

## UCL CS
For UCL CS the NTP server is found [here](http://www0.cs.ucl.ac.uk/staff/Richard.Smith/tips.html), try ping the server first to make sure it's still there.

## Finally
After configuration run `sudo systemctl restart chrony.service`  
  

# More info
[NTP homepage](http://www.ntp.org/) 
[Chrony faqs](https://chrony.tuxfamily.org/faq.html)

