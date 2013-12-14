yocotpuce-munin
===============

Munin Plugins for yoctopuce.com sensors


How to install
--------------

Copy plugins from the 'plugins' folder:

    cp plugins/* /usr/share/munin/plugins

Create symlink for your devices

    cd /etc/munin/plugins
    ln -s /usr/share/munin/plugins/METEOMK1_ METEOMK1_<yourserialnumber>-temperature
    ln -s /usr/share/munin/plugins/METEOMK1_ METEOMK1_<yourserialnumber>-pressure
    ln -s /usr/share/munin/plugins/METEOMK1_ METEOMK1_<yourserialnumber>-humidity
    ln -s /usr/share/munin/plugins/YCO2MK01_ YCO2MK01_<yourserialnumber>
    ln -s /usr/share/munin/plugins/PT100MK1_ PT100MK1_<yourserialnumber>

Copy plugin config
    cp plugin-conf.d/* /etc/munin/plugin-conf.d/

Munin Autoconfigure
-------------------
The modules can be configured automatically

    munin-node-configure --suggest --shell

How to find the serialnumber
----------------------------

This step is only needed if you do not like to use the munin autoconf functionality.

You need to install the yVirtualhub software. This will listen on port 4444 and you can directly conect with the browser of your choice. All yoctopuce devices wil show up like 'PT100MK1-14BD3'. The first part is the module type and the second one the serialnumber. In this example the link will be:

    ln -s /usr/share/munin/plugins/PT100MK1_ PT100MK1_14BD3
