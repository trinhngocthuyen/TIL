Developer Tools, Config and Snippets
=================

### Table of Contents
* [General](#general)
* [iOS](#ios)
* [Others](#others)
* [Commonly used Commands](#commonly-used-commands)

### General
- iTerm: https://www.iterm2.com
- Oh-my-zsh: https://github.com/robbyrussell/oh-my-zsh
- Homebrew: http://brew.sh
- cdto: https://github.com/jbtule/cdto
- Sublime Package Control: https://packagecontrol.io/installation

### iOS
- Fastlane (integration tool): https://github.com/fastlane/fastlane
- ~~Alcatraz (Package manager): http://alcatraz.io/ (not work with XCode8 anymore)~~
- CocoaPods (Library dependency manager): https://github.com/CocoaPods/CocoaPods
- ~~Chisel (Facebook) (LLDB scripts for debugging): https://github.com/facebook/chisel~~

### Others
#### General: Set default application for a specific type
http://www.imore.com/how-change-default-apps-os-x

#### Git: Set "Sublime Text" as git text editor
```
- ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl     <--- Create symlink
- git config --global core.editor "subl -n -w"
```
https://help.github.com/articles/associating-text-editors-with-git/

#### Finder: Show hidden files
```
- defaults write com.apple.finder AppleShowAllFiles YES
- Relaunch Finder
```
http://ianlunn.co.uk/articles/quickly-showhide-hidden-files-mac-os-x-mavericks/

#### Sublime Text: Open new file using a new tab (not a new window)
Preferences → Settings - User → Add: 
```
"open_files_in_new_window": false
```

#### XCode8: Comment/Uncomment issue
```
sudo /use/libexec/xpccachectl → restart
```
(https://twitter.com/eschaton/status/763254753090383872)

### Commonly used Commands
#### Rename file
```
mv old_file new_file
```

#### Batch rename asset files (@1x, @2x, @3x images)
```
for file in *.png; do mv $file ${file/_main/_large}; done   ← Replace _main by _large/medium/small
for file in *.png; do mv $file ${file/@1x/}; done           ← Remove @1x ← XCode does not automatically recognize @1x file
```

#### Search files/directories
```
find . -type f | grep "localization"
find . -type d | grep "KateSpade"
```

#### Sort (text) file alphabetically
```
sort input.txt > output.txt
```

#### Grep & count
```
find . | grep ".swift" | wc -l
```


#### Convert RTF to TXT
```
textutil -convert txt input.rtf
find . -name \*.rtf -print0 | xargs -0 textutil -convert txt
```
