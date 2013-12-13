yocotpuce-munin
===============

Munin Plugins for yoctopuce.com sensors


-- Copy plugins from the 'plugins' folder:

cp plugins/* /usr/share/munin/plugins

-- Create symlink for your devices

cd /etc/munin/plugins
ln -s /usr/share/munin/plugins/METEOMK1_ METEOMK1_<yourserialnumber>-temperature
ln -s /usr/share/munin/plugins/METEOMK1_ METEOMK1_<yourserialnumber>-pressure
ln -s /usr/share/munin/plugins/METEOMK1_ METEOMK1_<yourserialnumber>-humidity
ln -s /usr/share/munin/plugins/YCO2MK01_ YCO2MK01_<yourserialnumber>
ln -s /usr/share/munin/plugins/PT100MK1_ PT100MK1_<yourserialnumber>

-- Copy plugin config
cp plugin-conf.d/* /etc/munin/plugin-conf.d/


