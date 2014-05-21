yocotpuce-munin
===============

Munin Plugins for yoctopuce.com sensors

## Jump to Section
* [How to install](#how-to-install)
* [Notes](#notes)
* [License](#license)
* [Donate Me ![](https://www.paypalobjects.com/de_DE/DE/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=TZMF3HP322F5U)

## How to install
---
[[Back To Top]](#jump-to-section)

Copy plugins from the 'plugins' folder and add the IP of the yoctopuce virtualhub or YoctoHub, e.g:

    cp plugins/YOCTOPUCE_ /usr/share/munin/plugins/YOCTOPUCE_127_0_0_1_
    cp plugins/YOCTOPUCE_ /usr/share/munin/plugins/YOCTOPUCE_192_168_0_1_

For USB power consumption:

    cp plugins/YOCTOUSBPOWER_ /usr/share/munin/plugins/YOCTOUSBPOWER_127_0_0_1
    cp plugins/YOCTOUSBPOWER_ /usr/share/munin/plugins/YOCTOUSBPOWER_10_0_1_17

Create symlink for your devices (run as root)
    
    munin-node-configure --suggest --shell

Create list of threshold keys (run as root)

    /usr/share/munin/plugins/YOCTOPUCE_ suggest env >> /etc/munin/plugin-conf.d/yoctopuce 

Afterwards you need to set to proper values for these keys, according to your needs.

## Notes
---
YOCTOPUCE\_ is a universal plugin, which will most likely work for all yoctopuce sensors. If your sensors does not work, feel free to file a bug and please do add the following debug information:

    wget -q -O - http://127.0.0.1:4444/api.json|python -mjson.tool
    wget -q -O - http://127.0.0.1:4444/bySerial/<your-modulename>-<your-serial>/api.json|python -mjson.tool

## License
---
[[Back To Top]](#jump-to-section)

Copyright © 2013 Sascha Curth

This software is licensed under [MIT License](http://scurth.mit-license.org/).
