# Bodos Raspberry PI

This is the configuration for my Raspberry PI.

# List of things that get installed

* [Home Assistant](http://home-assistant.io)
* [AirSonos](https://github.com/stephen/airsonos)
* [Plex](https://www.plex.tv/)

This also activates unattended upgrades, the Raspberry
will automatically update packages, but will not
restart. You might want to do that manually for
kernel patches.

# How to use it

Steps to install it on your machine:

* Basic setup on the Raspberry Pi:
  * Install [NOOBS](https://github.com/procount/noobsconfig/) on the Raspberry
  * Select the non ui version of raspbian
  * Wait till it is installed and login using `pi` and `raspberry` as password
  * Activate ssh as described [here](https://www.raspberrypi.org/documentation/remote-access/ssh/README.md).
  * Add your ssh key to the `.ssh/authorized_keys` file on the Raspberry
* Setup and run [ansible](http://ansible.com) on your computer to install everything on the Raspberry:
  * Copy the `config.yml_example` to `config.yml` and configure the values in there
  * Change the IP in the [`hosts`](hosts) file to the IP of your Raspberry
  * Install ansible with `brew install ansible`
  * `sh run.sh` (this will take a bit of time, especially the ruby build)
  * Wait 10-15 minutes for home assistant to finish the installation
  * Open `http://[raspberryip]:8123` to see the Home Assistant wizard


# Home Assistant

The configuration of home assistant can be found in `/home/homeassistant/.homeassistant`.

