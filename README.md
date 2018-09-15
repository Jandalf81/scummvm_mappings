# scummvm_mappings
Patch to change the default joystick mappings in ScummVM for RetroPie

First things first, I did *NOT* create this. The credit goes to u/theheadfl over at Reddit. See [this thread](https://www.reddit.com/r/RetroPie/comments/90rv8u/guide_make_scummvm_joypad_mappings/) for his original patch targetting RetroPie-Setup 4.4.0
I merely updated the patch to work with RetroPie-Setup 4.4.2

# How to apply
## Get the patch file
In this file there are all the changes necessary to change the default joystick mappings

    cd ~
    wget https://raw.githubusercontent.com/Jandalf81/scummvm_mappings/v4.4.2/scummvm_joystick_retroarch_autoconfig.patch

## Apply the patch
Now, change into the _RetroPie-Setup_ directory and apply the patch file to the setup scripts there

    cd RetroPie-Setup
    sudo git apply --whitespace=nowarn ../scummvm_joystick_retroarch_autoconfig.patch
    
## Get the ScummVM source code
The changes will have to be compiled into the binaries. In order to do that, you first have to get the source code to ScummVM

    sudo ./retropie_packages.sh scummvm sources

## Compile, install and configure ScummVM
Now you have everything needed to compile ScummVM with the changes. This will take quite some time. Do not interrupt the build process

    sudo ./retropie_packages.sh scummvm build
    sudo ./retropie_packages.sh scummvm install
    sudo ./retropie_packages.sh scummvm configure
    
# How to use
Simply start ScummVM like you are used to. The patch makes it so the controller JS0 will be configured to use in ScummVM. The default mappings are:

    action_lclick="a"
    action_rclick="b"
    action_vkeybd="select"
    action_svmmenu="start"
    action_escape="l"
    action_period="x"
    action_space="y"

# How to change the mappings
Open the following file and change the mapping there

   nano /opt/retropie/emulators/scummvm/controller_map.sh

