# cheat
cheat allows you to create and view interactive cheatsheets on the command-line.

The beautiful thing about cheat is that you can also add your cheatsheets, making easy to remember specifics commands on the fly without leaving the beloved terminal. Your additions are stored in a personal folder located at: /home/$USER/.config/cheat/cheatsheets/personal/. 

As a matter of fact, this is my git repo with my cheat personal folder. 

## Install cheat
Original repo: https://github.com/cheat/cheat

There are several ways to install cheat. After attempting a snap installation, I've decided to go for the unix-like manual installation (my current distro Ubuntu 20.04.5). Copy-paste the following snippet:

```bash
  cd /tmp \
  && wget https://github.com/cheat/cheat/releases/download/4.3.3/cheat-linux-amd64.gz \
  && gunzip cheat-linux-amd64.gz \
  && chmod +x cheat-linux-amd64 \
  && sudo mv cheat-linux-amd64 /usr/local/bin/cheat
```

Now, to install my personal cheat sheets:
`
```bash
  cd ~/.config/cheat/cheatsheets/personal \
  && wget https://github.com/n0rt3y5ur/cheat-personal/archive/refs/heads/main.zip && unzip main.zip \
  && rm main.zip \
  && mv cheat-personal-main/* .  \
  && rm -r cheat-personal-main README.md 
  ```
  
## Start using cheat
To view a cheatsheet:

```sh
cheat tar      # a "top-level" cheatsheet
cheat foo/bar  # a "nested" cheatsheet
```

To edit a cheatsheet:

```sh
cheat -e tar     # opens the "tar" cheatsheet for editing, or creates it if it does not exist
cheat -e foo/bar # nested cheatsheets are accessed like this
```

To view the configured cheatpaths:

```sh
cheat -d
```

To list all available cheatsheets:

```sh
cheat -l
```

To list all cheatsheets that are tagged with "networking":

```sh
cheat -l -t networking
```

To list all cheatsheets on the "personal" path:

```sh
cheat -l -p personal
```

To search for the phrase "ssh" among cheatsheets:

```sh
cheat -s ssh
```

To search (by regex) for cheatsheets that contain an IP address:

```sh
cheat -r -s '(?:[0-9]{1,3}\.){3}[0-9]{1,3}'
```

Flags may be combined in intuitive ways. Example: to search sheets on the
"personal" cheatpath that are tagged with "networking" and match a regex:

```sh
cheat -p personal -t networking --regex -s '(?:[0-9]{1,3}\.){3}[0-9]{1,3}'
```



