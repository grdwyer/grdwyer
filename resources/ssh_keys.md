# Managing multiple keys
Sometimes you need multiple ssh keys, if you are using two sets of keys to access the same site (e.g. you have 2 github accounts) then you can find weird conflicts arise if one key has the default name (`~/.ssh/id_rsa`).  
The way I've gone for is just to be explicit with the keys I'm using so not naming them with the default (though I don't think that's an issue if you have) and setting them with `ssh-add`  
The main commands:  
```
ssh-add <path_to_private_key> # Adds the key to the agent
ssh-add -l # Lists the currently active keys
ssh-add -D # Removes all keys from the agent (doesn't delete the key)
```

# Weird issues I've came across
## Docker no connection to SSH agent
When mounting my .ssh directory to a container and I have a different ssh config setup I get an issue about not being able to connect to the agent.  
```Could not open a connection to your authentication agent.```
This normally means you need to startup the agent (within the container) by running:  
```eval `ssh-agent -s` ```

# References
[multiple keys](https://www.freecodecamp.org/news/how-to-manage-multiple-ssh-keys)  
[starting ssh agent](https://stackoverflow.com/questions/17846529/could-not-open-a-connection-to-your-authentication-agent)

