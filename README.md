# Ansible Scripts for OctoPrint on Raspbian Stretch

This is simply a set of playbooks and roles that help with installing OctoPrint on a Raspberry Pi.

## Setting Up Your Hosts File

When the SD provisioning playbook is ready, it will **not** require an inventory, since the commands will (probably) run on localhost. However, the actual OctoPrint install will be executed on the running RPi.

If you're using DHCP to obtain an IP address, you'll need to lookup your address on the Pi itself, using:

```
$ ip -4 addr show | grep 'inet '
```

For the uninitiated: you'll probably want to select the address that uses the `192.` or `10.` IP prefix.

Once you know your Pi's IP address, make a copy of the `hosts.template` file and replace `aaa.bbb.ccc.ddd` with your IP address, and you'll be ready to go.

## Provisioning the Raspbian SD Card

To get started, you'll need to download Raspbian from [the Raspberry Pi Foundation download site](https://www.raspberrypi.org/downloads/raspbian/). Once you have the `.img.zip` file, the first step is to unzip it.

### Setup Your Variables

Before provisioning, you'll need to set some variables to tell Ansible the target for copying the .img file, along with some other details.

**TODO**

## Installing On a Running RPi

Once you have a Pi running Raspbian Stretch with SSH enabled, you can install OctoPrint (+webcam support) using the `install-octoprint.yml` playbook:

```
$ ansible-playbook -i ./hosts install-octoprint.yml
```
