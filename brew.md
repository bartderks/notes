# brew.sh

Using the brew package manager (https://brew.sh) to install different applications on my MacBook Pro.

## Install

Install of brew:

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

After installation has finished (will also be displayed in installation output):

```
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> /Users/bart/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

## Packages

```
brew install git wget curl
brew install --cask firefox 1password wireshark vlc cleanshot whatsapp postman microsoft-remote-desktop microsoft-word microsoft-teams microsoft-excel microsoft-auto-update microsoft-outlook microsoft-powerpoint onedrive dbeaver-community miro tailscale
brew install --cask chromium --no-quarantine
```

## Notes

I'm using individual microsoft-* packages since the microsoft-office / microsoft-office-businesspro packages also contain microsoft-onenote and I don't need that. Unfortunately Microsoft To Do looks like to be unavailable within homebrew. Maybe look for an alternative.

When installing chromium you need to pass the --no-quarantine parameter otherwise the application won't start (error that the application is damaged) [1]

## Links
[1] https://www.reddit.com/r/MacOS/comments/q9d772/homebrew_chromium_is_damaged_and_cant_be_openend/
