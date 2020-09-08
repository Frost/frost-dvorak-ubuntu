# frost-dvorak-ubuntu
My slightly modified US Dvorak (with åöä on capslock+aoe)


## Installation

* Copy the layout to /usr/share/X11/xkb/symbols
* Add the following in some nice location in /usr/share/X11/xkb/rules/evdev.xml 

``` xml
    <layout>
      <configItem>
        <name>frost</name>
        <!-- Keyboard indicator for Swedish layouts -->
        <shortDescription>frost dvorak</shortDescription>
        <description>Swedish</description>
        <languageList>
          <iso639Id>swe</iso639Id>
        </languageList>
      </configItem>
      <variantList>
        <variant>
          <configItem>
            <name>dvorak</name>
            <description>Swedish (Frost Dvorak)</description>
          </configItem>
        </variant>
      </variantList>
    </layout>
```

* Add the following somewhere under `! layout` in /usr/share/X11/xkb/rules/evdev.lst (I usually put it close to the regular swedish one)


``` 
  frost           Swedish (Frost Dvorak)
```

* Add the following somewhere under `! variant` in the same file

```
  dvorak       frost: Swedish (Frost Dvorak)
```

* Run `sudo dpkg-reconfigure xkb-data`

* Select your (well, my) preferred keyboard layout in the keyboard layout settings

* If you want, also modify `/etc/default/keyboard` to something like this

```
XKBLAYOUT=frost
XKBVARIANT=
BACKSPACE=guess
```

