![alt tag](https://raw.githubusercontent.com/MatteoWickiBande/mwb-layout/master/keyboard-layout.png)
Preview of the mwb-layout (programmer dvorak variant). It was designed to be used on ISO keyboards (Mod3-key).

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

#Install console keymap
Note, that the location of the console keymaps differ between distributions.
On Gentoo:
```
cp mwb mwb.map.gz /usr/share/keymaps/i386/dvorak/
```
On Arch/Parabola:
```
cp mwb mwb.map.gz /usr/share/kbd/keymaps/i386/dvorak/
```
To load the keymap temporarily in your tty:
```
loadkeys mwb
```
Permanently set using systemd-localed:
```
localectl set-keymap mwb
```
On other init systems it differs aswell.
On OpenRC you can edit the file /etc/conf.d/keymaps and set
```
keymap="mwb"
```
