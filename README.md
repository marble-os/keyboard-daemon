# Keyd
## Installation

### Gentoo

#### Adding Repository
	echo "\n\n[marble-os]\nlocation = \/var\/db\/repos\/marble-os\nsync-type = git\nsync-uri = https:\/\/github.com\/marble-os\/ebuild-repository.git" >> /etc/portage/repos.conf/marble-os.conf
	emerge --sync marble-os
#### Emerging
	emerge keyboard-daemon
	

### From Source
#### OpenRC
	git clone https://github.com/marble-os/keyboard-daemon.git
	cd keyd
	make && doas make install
	doas rc-update add keyd && rc-service keyd start
	
#### SystemD
    git clone https://github.com/marble-os/keyboard-daemon.git
    cd keyd
    make && sudo make install
    sudo systemctl enable keyd && sudo systemctl start keyd


## Quickstart

1. Install and start keyd (e.g `sudo systemctl enable keyd`)

2. Put the following in `/etc/keyd/default.conf`:

```
[ids]

*

[main]

# Maps capslock to escape when pressed and control when held.
capslock = overload(control, esc)

# Remaps the escape key to capslock
esc = capslock
```
