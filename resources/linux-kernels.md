# Kernels
## Low latency
Always try low latency first as it is quick to setup (unless there is a safety reason that a hard rt kernel is needed)  
Install it using:  
`sudo apt install linux-image-lowlatency`

Reboot then select the kernel in grub.  
If you have a separate boot partition check the size as kernel updates are automatic and you will use up the space in double the time.

## RT Kernel
I have not yet tried this yet but the [franka tutorial](https://frankaemika.github.io/docs/installation_linux.html) seems to be the best tutorial around


 

