# avrdude for platformio

> [!CAUTION]
> This package is ment to work with my machine so it cant not work with yours without modification
> Tested on window 10 x64

Since platformio have outdated avrdude package i try to force it to use new one.

I simply download the latest avrdude package from [here](https://github.com/avrdudes/avrdude/releases/tag/v8.1) and extract it to platformio packages folder.

to patch the platformio add in `platformio.ini` file

```ini
platform_packages =
    platformio/tool-avrdude @ https://github.com/devchew/tool-avrdude
```

example for attiny85 and usbasp programmer

```ini
[env:attiny85]
platform = atmelavr
board = attiny85
platform_packages =
    platformio/tool-avrdude @ https://github.com/devchew/tool-avrdude
framework = arduino
upload_protocol = usbasp
upload_flags =
 -p t85
 -B 5
 -v

```
