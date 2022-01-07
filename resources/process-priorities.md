# Process Priorities
Occasionally some processes are more important than another. This doesn't mean the process runs any faster (though it may), but it means that if the system has too many processes running the scheduler will attempt to keep this running at the correct rate.  
  
There are multiple ways to do this but one of least intrusive ways to start is with Nice.

## Nice
Nice sits more in the userspace and is similar to the approach with lowlatency and rt kernels, try this before moving into actual priorities.
Nice goes between -20 and 19 (-20 is the highest priority and the least nice), and can be set as a prefix before the command you want to run.  
### Running a process
For example to run at -10 it would be:  
`sudo nice -n -10 <command>`  

To run without sudo and allow users to directly set the niceness of processes  
Add to `/etc/security/limits.conf` with your username  
`<username>  -    nice   -15`  
  
### Checking a process
You can use `top` or `htop` to check the niceness of a process it is normally the 4th column of the output.  

### Inside a container
Using Nice within a container requires it to be added as a capability `--cap-add=sys_nice`.  
There is more information on docker sit about priorities in the container [here](https://docs.docker.com/config/containers/resource_constraints/#configure-the-realtime-scheduler) 