# Android device tree for samsung SM-A057F (a05s)

# How-to compile it:

## twrp-14 Manifest
    repo init --depth=1 -u https://github.com/MrFluffyOven/platform_manifest_twrp_aosp.git -b twrp-14
## Sync
    repo sync
## Clone galaxy a05s TWRP tree
    git clone https://github.com/TND-STAGING/android_device_samsung_a05s.git -b staging device/samsung/a05s
## Prepare
    export ALLOW_MISSING_DEPENDENCIES=true; . build/envsetup.sh; lunch twrp_a05s-eng
## Repopick Patches
    repopick -Q "branch:android-14+status:open+-change:7371+-change:7543+-change:7553+-change:7671+-change:7717+-change:7718"
## Run the Build Command
    mka recoveryimage
