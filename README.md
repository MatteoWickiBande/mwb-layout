![alt tag](https://raw.githubusercontent.com/MatteoWickiBande/mwb-layout/master/keyboard-layout.png)
Preview of the mwb-layout (programmer dvorak variant)

#Notable features
* Arrow keys on the left side of the home row
* Numpad on the right side
* Navigation keys like Home, End, PgUp and PgDn are easy to acces

#Installation in your $HOME:
```
mkdir -p ~/.xkb/symbols/
cp mwb ~/.xkb/symbols/
```
To enable it:
```
setxkbmap -I ~/.xkb mwb -print | xkbcomp -I$HOME/.xkb - $DISPLAY
```
#Systemwide install:
```
cp mwb /usr/share/X11/xkb/symbols/
```
To enable it:
```
setxkbmap mwb
```
