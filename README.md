# Android device tree for samsung SM-A057F A057FXX[U7]CXK6 (a05s)


# How-to compile it:

## twrp-14 Manifest
    repo init --depth=1 -u https://github.com/MrFluffyOven/platform_manifest_twrp_aosp.git -b twrp-14
## Sync
    repo sync
## Clone galaxy A057F tree
    git clone https://github.com/galaxy-a05s/android_device_samsung_a05s.git -b common-crypton device/samsung/a05s
## Clone a05s common tree
    git clone https://github.com/galaxy-a05s/android_device_samsung_a05s-common.git -b android-14 device/samsung/a05s-common
## Prepare
    export ALLOW_MISSING_DEPENDENCIES=true; . build/envsetup.sh; lunch twrp_a05s-eng
## Repopick Patches
    repopick -Q "branch:android-14+status:open+-change:7371+-change:7543+-change:7553+-change:7671+-change:7717+-change:7718"
## Run the Build Command
    mka recoveryimage
