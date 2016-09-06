#How to install
```
mkdir -p ~/.xkb/symbols/
cp mwb ~/.xkb/symbols/
```
#To use as a layout
```
setxkbmap -I ~/.xkb mwb -print | xkbcomp -I$HOME/.xkb - $DISPLAY
```
