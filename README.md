# gitpod-po-util

Just trying to get po working on Gitpod.io


https://gitpod.io/#github.com/hpssjellis/gitpod-po-util



This works, latest snapshot

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io#snapshot/52976b37-ce98-4d38-818f-38a1c36135c3)

In the above snapshot, my Oct 2019 Particle Argon build has already generated the .bin file, however you can't flash from a browser so the file will need to be downloaded to your machine and then install particle-cli and flash from your machine

```
particle flash --usb myArgonProject-argon.bin

```


Old generic instructions

```

sudo apt install curl
bash <(curl -sL get.po-util.com)

po init argon myProjectName
cd myProjectName


## monolithic Build of Mesh Devices (full load of firmware to device)
po config mesh-develop

po setup-mesh

MODULAR=n po argon build



## normal building of Mesh Devices
## po config v0.8.0-rc.27 
## po argon build


particle cloud login
## enter your particle userName then password

## see if your Argon is flashing cyan and online
particle list

## flash your code to the Argon over the air
po argon ota myArgonName

## actually nowI am preferring to use DFU mode since it acknowledges success
## on cloud9 I download the .bin and then use particle-cli to do the command
## on a local machine just run this
## dfu mode flashing yellow hold mode button tap reset about 5 seconds past flashing purple safe mode.
particle flash --usb  myArgonName.firmware.bin


```
