wake-up
=======

Daily wake up server on pre-defined times

In my scenario (Ubuntu Server 14.04) the three files in this repository go here:

/usr/bin/wake-up

This is the main script. You can shedule ONE wake-up for each weekday. 

/etc/init/wake-up.conf

This upstart configuration file triggers the execution of the main script each time the server boots up. 

/home/tobias/.wake-up

This (hidden) one-line text file, located in my home directory, is needed for the timed execution of /usr/bin/wake-up in case the server boots before the wake-up time given for the same day. See the following line in the main script:

at -f /home/tobias/.wake-up $boot_time

You have to change the path in the main script, if you put .wake-up elsewhere - which is very likely ;-)

You also have to change the location of the log file rtcwake.log to your needs in wake-up.conf and .wake-up.
