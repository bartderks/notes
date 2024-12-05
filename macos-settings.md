# MacOS Settings

Applying the following settings to MacOS for better experience (just my opinion :-))

* Show only active applications in Dock. No need for other stuff in Dock since we launch everything through Spotlight or terminal.
```
defaults write com.apple.dock static-only -bool true; killall Dock
```
* Always show scroll bars
```
defaults write NSGlobalDomain AppleShowScrollBars -string "Always"; killall Finder
```
* Show path in the header of Finder
```
defaults write com.apple.finder _FXShowPosixPathInTitle -bool true; killall Finder
```
* Auto hide dock
```
defaults write com.apple.dock autohide -bool true && killall Dock
defaults write com.apple.dock no-bouncing -bool TRUE && killall Dock
```
