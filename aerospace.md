# AeroSpace - tiling window manager for MacOS

## Introduction

AeroSpace is a tiling window manager for MacOS (inspired on i3 window manager for Linux).

Official page: https://github.com/nikitabobko/AeroSpace
Docs: https://nikitabobko.github.io/AeroSpace/guide

## Installation & configuration

Installation through homebrew (first removed amethyst):

```
brew remove amethyst
brew install --cask nikitabobko/tap/aerospace
```

Create a default config in ~/.config/aerospace/aerospace.toml

I used the following video/blog post as a initial guide to setup a proper first configuration:
https://www.youtube.com/watch?v=-FoWClVHG5g
https://www.josean.com/posts/how-to-setup-aerospace-tiling-window-manager

Primarily made the following changes in the config file:

```
# make sure to start on boot
start-at-login = true
# move mouse focus to other window when changing window focus
on-focus-changed = "move-mouse window-lazy-center"
# add 'gaps' around/between windows
inner.horizontal = 10
inner.vertical =   10
outer.left =       10
outer.bottom =     10
outer.top =        10
outer.right =      10
# move specific applications to specific workspaces (and make sure opening a mail in Outlook also gets tiled):
[[on-window-detected]]
if.app-id = 'com.google.Chrome'
run = "move-node-to-workspace 1"

[[on-window-detected]]
if.app-id = 'org.mozilla.firefox'
run = "move-node-to-workspace 2"

[[on-window-detected]]
if.app-id = 'com.microsoft.Outlook'
check-further-callbacks = true
run = "layout tiling"

[[on-window-detected]]
if.app-id = 'com.microsoft.Outlook'
run = "move-node-to-workspace 3"

[[on-window-detected]]
if.app-id = 'com.microsoft.teams2'
run = "move-node-to-workspace 4"

[[on-window-detected]]
if.app-id = 'com.github.wez.wezterm'
run = "move-node-to-workspace 5"

[[on-window-detected]]
if.app-id = 'net.whatsapp.WhatsApp'
run = "move-node-to-workspace 6"

[[on-window-detected]]
if.app-id = 'com.apple.finder'
run = "move-node-to-workspace 7"

[[on-window-detected]]
if.app-id = 'com.postmanlabs.mac'
run = "move-node-to-workspace 7"

[[on-window-detected]]
if.app-id = 'org.jkiss.dbeaver.core.product'
run = "move-node-to-workspace 7"

[[on-window-detected]]
if.app-id = 'com.sublimetext.4'
run = "move-node-to-workspace 7"

[[on-window-detected]]
if.app-id = 'org.jkiss.dbeaver.core.product'
check-further-callbacks = true
run = "layout tiling"

[[on-window-detected]]
if.app-id = 'com.microsoft.rdc.macos'
run = "move-node-to-workspace 9"
```

Will clean-up/further tweak configuration later, will update this document if so.
