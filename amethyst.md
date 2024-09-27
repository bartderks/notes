# Amethyst - MacOS Window Manager

20240927 UPDATE: SWITCHED TO AEROSPACE INSTEAD OF AMETHYST, SEE AEROSPACE.MD FOR MORE DETAILS

Amethyst is a tiling Window Manager for MacOS. [1]

## Installation

Amethyst can be installed through Homebrew:

```
brew install --cask amethyst
```

## Configuration

### MacOS

I would like to change desktops by keyboard shortcut which is not enabled by default.

Go to MacOS 'System Settings', choose 'Keyboard' and hit the button 'Keyboard Shortcuts'. In the menu on the left, choose 'Mission Control' and in the list on the right that appears, expand the 'Misson Control' dropdown. There you can enable the 'Switch to Desktop X' options (where X is the number of your desktop) and configure a new shortcut. I prefer cmd+1 (for example) instead of the default ^+1. You can change the shortcut by double clicking the shortcut and pressing the desired new key combination.

One other important thing is to tell MacOS to not automatically rearrange Spaces/Desktops which messes up the persistence of your desktops. Go to MacOS 'System Settings' and choose 'Desktop & Dock'. Scroll down to 'Mission Control' and disable the option 'Automatically rearrange Spaces based on most recent use'.

### Amethyst

Within the Amethyst preferences, for now, I enable two options:

* Under Mouse, enable 'Resize windows using mouse'
* Under Floating, add the System Preferences application

'Float small windows' is enabled by default (to make sure stuff like Save dialogs do not get re-arranged) but the System Settings window does not count as 'small' apparently.

## Links

[1] https://github.com/ianyh/Amethyst
