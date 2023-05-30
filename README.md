# Razr5G Foldable Device Fixes (magisk)
A magisk module that helps the cli display work correctly on GSIs.

This module has been tested on my XT2071-3 but is not guaranteed to work on your XT2071-3.

What the module does:
- defines open and closed states in `device_state_configuration.xml`
- defines which displays should be enabled during each state in `display_layout_configuration.xml`
- adds an overlay that removes the display cutout from the cli display
- adds an overlay that defines which state is folded, the device postures, and prevents both displays from being on at the same time

Bugs:
- for whatever reason, `a2dp_audio_policy_configuration.xml` and `audio_policy_configuration.xml` can get overwritten, breaking audio (I'm working on a fix for that)
- brightness does not work on the cli display
- more that I'm probably missing...

Other things:
- this might not work on your device if your device's display identifiers are different
- the cli display is lacking many System UI tweaks to make it usable
- foldable support is a new feature of Android, so this tweak may stop working with any update
- this is not the same configuration used on the stock firmware
- you will need to install this Xposed module to prevent the system from crashing when the lid is closed: https://github.com/BigZucc420/Razr5G-Cli-Lid-Functions
- you will need to install this magisk module to fix the touch screen: https://github.com/BigZucc420/Razr5G-Synaptics-Touchscreen-Device-Associations

Sources:
- AOSP official documentation (https://source.android.com/s/results?q=display)
- More AOSP official documentation (https://source.android.com/devices/tech/display/display-cutouts)
- Even more AOSP official documentation (https://source.android.com/devices/architecture/rros)
- The Android Open Source Project (https://cs.android.com/android/platform/superproject/+/master:frameworks/base/core/res/res/values/config.xml)
- cuttlefish device specific configuration (https://cs.android.com/android/platform/superproject/+/master:device/google/cuttlefish/shared/foldable/)
- Magisk documentation (https://topjohnwu.github.io/Magisk/guides.html)
