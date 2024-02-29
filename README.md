
# ~/tmux.conf
TMux Configuration
# To make the cipiar hit paste only in MAC, no linux
```
brew install reattach-to-user-namespace
```
# This goes in my .zshrc file
```
function tat {
  name=$(basename `pwd` | sed -e 's/\.//g')
   if tmux ls 2>&1 | grep "$name"; then
     tmux attach -t "$name"
   elif [ -f .envrc ]; then
     direnv exec / tmux new-session -s "$name"
   else
     tmux new-session -s "$name"
   fi
 }
 ````

#Tmux Plugin Manager (Linux/Mac)
```
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

### Prefix: Ctrl + x
### With the prefix, in this case 'Ctrl + x' and then 'Shift + i' the plugins are installed, with the prefix and 'Shift + u' are updated.
