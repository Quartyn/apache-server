# Apache Server from current directory
Moving all files you want to host locally to `/var/www/html` can be really annoying.

This script will allow you to run the apache server from the current working directory.

## How to run a server
Enter the directory you want to host the apache server from.

And then run the command bellow:
```zsh
apache-server
```
## How does it work
When you run the command, new temporary configuration will be created and copied to the apache server configuration.

As soon as you stop the server (Ctrl+C), configuration will be removed, and if there is no other apache host running, the apache service will be automatically stopped. - So you are not always hosting the default directory at `localhost`.

## How to install
Clone this repo to your system.
```zsh
git clone https://github.com/Quartyn/apache-server
```
Move the `apacheServerConfig` directory into the `/usr/local/bin` or `/usr/bin` directory (Your choice. I recommend `/usr/local/bin`).
```zsh
sudo mv apacheServerConfig /usr/local/bin
```
After it's done, you will create a new symbolic link to the `apacheServerConfig/run-server` file.
```zsh
sudo ln -s /usr/local/bin/apacheServerConfig/run-server /usr/local/bin/apache-server
```
Here, you can also rename the symbolic link `apache-server` with your preferred command name. Then, you will be able to start this command with your "own name".

For example, if you decide your symbolic link to be `run-server`, you will then start the server with command
```zsh
run-server
```

And that's all! Enjoy.