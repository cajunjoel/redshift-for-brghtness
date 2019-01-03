# Using Redshift for "fake" brightness control

This is a bash script that uses Jon Lund Steffensen's http://jonls.dk/redshift/ to create a software based (fake) brigthness control for LCD displays where Linux cannot directly control the backlight of the LCD display.

# Usage

`brightness up` to increase the brigtness by 0.1

`brightness down` to decrease the brightness by 0.1

# Installation

Copy the brightness script to somewhere in your path, such as `/usr/local/bin`

The script attempts to create a file `~/.config/brightness.txt`, so be sure that the .config folder exists. This is a placeholder for now. I am unsure of where exactly to place the brightness.txt file, but this seems like an OK place for now.

# Dependencies

Redshift v1.11 needs to be installed. A `~/.config/redshift.conf` file is probably good to have around, we might use it later.

# Bugs

* **Redshift can't be running** since its presence will override whatever you are trying to set with the script. I haven't worked out a way around this, but I'm not sure I should.
* On first run, because the `~/.config/brightness.txt` file does not exist, the brightness will be reset to whatever `redshift -p` reports.
* More testing and development is needed, especially to see if we can override what redshift is doing while it's running. Maybe overwrite the redshift.conf file?
* More testing is needed at night, but since it pulls the temp from `redshift -p` this is probably going to work as expected.
