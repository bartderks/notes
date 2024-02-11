# Changing the shell to bash on MacOS

Default shell on MacOS is zsh since a long time. Using bash is more in line when you want to use same files (bashrc, bash_profile etc.) on different systems that have bash shell available by default (like Ubuntu for example).

To make sure we use the latest version, we use brew to install bash (MacOS has bash by default but it's a very old version):

```
brew install bash
```

After installation, you need to add the path to brew bash (/opt/homebrew/bin/bash) in /etc/shells.

Then you change the shell of your user with the following command:

```
chsh -s /opt/homebrew/bin/bash
```

Restart the terminal app and your back on bash. Make sure you run the following command to make brew working again:

```
eval "$(/opt/homebrew/bin/brew shellenv)"
```
