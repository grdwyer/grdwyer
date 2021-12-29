# Docker

I use docker for most of my development work, it's a bit of a pain to setup but I think it works nicely when you have different projects running that have conflicting dependencies (e.g. ROS1 and ROS2).  

## Installation
This is mainly self explanatory however there are some different versions depending on the system setup.  
Normal docker is installed from [here](https://docs.docker.com/engine/install/ubuntu/)  
Easiest (but not the safest) thing to do is use the convenience script:
```
curl https://get.docker.com | sh \
&& sudo systemctl --now enable docker 
```  

Nvidia docker is needed if you want to use an nvidia graphics card in the container installation instructions can be found [here](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html)  
  
**In Aug 2021** there was an issue with the install on pop os 20.04 the fix/workaround can be found [here](https://github.com/pop-os/pop/issues/1708#issuecomment-877830843)  

After install make sure you add the user to the docker group  
`sudo usermod -aG docker $USER`  

Testing after installation  
`docker run --rm hello-world`  
`docker run --rm --gpus all nvidia/cuda:11.0-base nvidia-smi`  
  
### Dev configuration
My current setup for containers essentially uses the user profile on the computer. It is probably not a secure way of doing things but works nicely for what I want to do - essentially be me in a container (access to ssh keys, x server etc).  

Old presentation I did on docker setup [drive link](https://docs.google.com/presentation/d/1vqrBtB6Zph0s6RMmVBtn7c7_h4slr2ukAp-EScLhPBs/edit?usp=sharing)  
TODO: add more info on the current setup  
  
Alt setup from rosworld2021 described [here](https://www.allisonthackston.com/articles/vscode-docker-ros2.html)  
