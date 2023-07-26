![Evolution X](https://github.com/Evolution-X/manifest/raw/tiramisu/EvoBanner.png)

Evolution X
===========

[![Download Evolution X](https://img.shields.io/sourceforge/dt/evolution-x.svg)](https://sourceforge.net/projects/evolution-x/files/latest/download)

### Syncing Evolution X Source Code ###

Please choose one of the following manifest branches

- If you are compiling for a non-pixel device and are not using jemalloc memory allocator:
```bash
repo init -u https://github.com/Evolution-X/manifest -b tiramisu
```

- If you are compiling for a Google Pixel device:
```bash
repo init -u https://github.com/Evolution-X/manifest -b tiramisu-pixel
```

- If you are compiling for a non-pixel device and would like to use the jemalloc memory allocator:
```bash
repo init -u https://github.com/Evolution-X/manifest -b tiramisu-jem
```

Once you have chosen a source branch, you can proceed with the synchronization using the following command:
```bash
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```
**Note:** To save space and reduce download time during the synchronization process, you can also pass `--depth 1` to the `repo sync` command. However, using `--depth 1` will result in the repositories being synced without any commit history.

### Evolution X Build Flags ###

This section comprises a list of available build flags that allow the inclusion or exclusion of specific prebuilts, Runtime Resource Overlays (RROs), and device properties in the Evolution X ROM.

**Note:** To configure these flags for a particular device, make the necessary adjustments in the evolution_codename.mk file of your device tree.


| Flag                          | Use                                           | Default Value |
|-------------------------------|-----------------------------------------------|---------------|
| TARGET_BOOT_ANIMATION_RES     | Specifies the resolution of the boot animation (available values: 1080, 1440, 720) | 1080 |
| TARGET_USES_MINI_GAPPS        | Indicates if the target uses Mini GApps (Gapps are full if unset) | false |
| TARGET_USES_PICO_GAPPS        | Indicates if the target uses Pico GApps (Gapps are full if unset) | false |
| TARGET_FACE_UNLOCK_SUPPORTED  | Indicates if the target supports face unlock| true |
| TARGET_SUPPORTS_QUICK_TAP     | Indicates if the target supports quick tap | false |
| TARGET_SUPPORTS_TOUCHGESTURES | Indicates if the target supports screen off touch gestures | false |
| EXTRA_UDFPS_ANIMATIONS        | Indicates if the target should include UDFPS resources| false |
| TARGET_USES_NOTHING_CAMERA    | Indicates if the target uses Nothing camera | false |
| TARGET_USES_MIUI_CAMERA       | Indicates if the target uses Miui camera | false |
| TARGET_USES_OPLUS_CAMERA      | Indicates if the target uses OPlus camera | false |
| TARGET_CAMERA_NEEDS_CLIENT_INFO_LIB_OPLUS      | Indicates if the target needs client info lib (for OPlus camera) | false |
| TARGET_NEEDS_OPLUS_VENDOR_TAG | Indicates if the target needs OPlus vendor tag (for Oplus camera) | false |
| TARGET_IS_PIXEL               | Indicates if the target is a Google Pixel device | false |
| TARGET_IS_PIXEL_6             | Indicates if the target is a Pixel 6 series device | false |
| TARGET_IS_PIXEL_7             | Indicates if the target is Pixel 7          | false |
| TARGET_IS_PIXEL_7A            | Indicates if the target is Pixel 7A        | false |
| TARGET_IS_PIXEL_FOLD          | Indicates if the target is Pixel Fold       | false |
| TARGET_IS_PIXEL_TABLET        | Indicates if the target is a Pixel Tablet   | false |
| TARGET_PIXEL_STAND_SUPPORTED  | Indicates if the target supports Pixel Stand.| false |

- Flags not listed here & more information regarding listed flags

[Soong](https://github.com/Evolution-X/vendor_evolution/blame/tiramisu/config/BoardConfigSoong.mk) | [Kernel](https://github.com/Evolution-X/vendor_evolution/blame/tiramisu/config/BoardConfigKernel.mk)


### Evolution X Configuration Files ###

This section includes a list of configuration files containing overlayable resources to enable, disable, or configure features in the Evolution X ROM.

**Note:** Any modifications or customizations to these resources should be made in the device tree via product package overlays or runtime resource overlay (RRO) packages.

| Configuration File                       | Description                                    |
|------------------------------------------|------------------------------------------------|
| [AOSP FWB core config](https://github.com/Evolution-X/frameworks_base/blob/tiramisu/core/res/res/values/config.xml) | Overlayable resources for AOSP FWB core features |
| [Evolution FWB core config](https://github.com/Evolution-X/frameworks_base/blob/tiramisu/core/res/res/values/evolution_config.xml) | Overlayable resources for Evolution X FWB core features |
| [AOSP FWB SystemUI config](https://github.com/Evolution-X/frameworks_base/blob/tiramisu/packages/SystemUI/res/values/config.xml) | Overlayable resources for AOSP FWB SystemUI features |
| [Evolution SystemUI config](https://github.com/Evolution-X/frameworks_base/blob/tiramisu/packages/SystemUI/res/values/evolution_config.xml) | Overlayable resources for Evolution X FWB SystemUI features |
| [AOSP Settings config](https://github.com/Evolution-X/packages_apps_Settings/blob/tiramisu/res/values/config.xml) | Overlayable resources for AOSP Settings features |
| [Evolution Settings config](https://github.com/Evolution-X/packages_apps_Settings/blob/tiramisu/res/values/evolution_config.xml) | Overlayable resources for Evolution X Settings features |
| [Evolution Settings strings](https://github.com/Evolution-X/packages_apps_Settings/blob/tiramisu/res/values/evolution_strings.xml) | Overlayable string resources for Evolution X Settings |
| [ AOSP/Evolution SettingsProvider defaults](https://github.com/Evolution-X/frameworks_base/blob/tiramisu/packages/SettingsProvider/res/values/defaults.xml) | Overlayable resources for AOSP/Evolution X SettingsProvider feature defaults |


### Build ###

- Set up the build environment

```bash
. build/envsetup.sh
```

- Choose a target
```bash
lunch evolution_codename-userdebug
```

- To start compiling
```bash
m evolution
```


### Applying for maintainership of a device ###

If you are a device maintainer and are interested in maintaining our ROM for your device, please follow these steps:

Review the [Evolution X Code of Conduct](https://wiki.evolution-x.org/code-of-conduct) carefully. You will be asked questions about it during your interview.

Contact [DarkAngelGR](https://t.me/DarkAngelGR) to schedule an initial interview. During the interview, you will need to provide information about your device, including its name, codename, any current device-side bugs, and the SELinux status. You should also provide links to your device repositories on GitHub, mention your availability, and confirm that you have a reliable means to compile the ROM and provide builds in a timely manner.

Depending on your device manufacturer and other potential factors, you may be redirected to other team members for additional questions during the interview process. This could be to ensure that you are the right fit for the specific requirements of maintaining the ROM for your device.

We are looking for maintainers who are committed to providing quality support and maintaining the ROM effectively, so please only apply if you feel that you meet these requirements. We look forward to hearing from you!


# Credits:

| Project                           | GitHub Organization                        | Project                           | GitHub Organization                  |
|-----------------------------------|-------------------------------------------|-----------------------------------|---------------------------------------|
| LineageOS                         | [Link](https://github.com/LineageOS)      | crDroid                           | [Link](https://github.com/crdroidandroid) |
| ParanoidAndroid                   | [Link](https://github.com/AOSPA)          | Octavi-OS                         | [Link](https://github.com/Octavi-OS) |
| PixelDust                         | [Link](https://github.com/PixelDust-Twelve)   | hentaiOS                          | [Link](https://github.com/hentaiOS) |
| ProtonAOSP                        | [Link](https://github.com/ProtonAOSP)     | POSP                              | [Link](https://github.com/PotatoProject) |
| BlissROMs                         | [Link](https://github.com/BlissRoms)      | StatiXOS                          | [Link](https://github.com/StatiXOS) |
| Syberia Project                   | [Link](https://github.com/syberia-project)| ArrowOS                           | [Link](https://github.com/ArrowOS) |
| PixelExperience                   | [Link](https://github.com/PixelExperience)| AICP                              | [Link](https://github.com/AICP) |
| ShapeShiftOS                      | [Link](https://github.com/ShapeShiftOS)   | YAAP                              | [Link](https://github.com/yaap) |
| PixelExtended                     | [Link](https://github.com/PixelExtended)  | AospExtended                      | [Link](https://github.com/AospExtended) |
| Nitrogen OS                       | [Link](https://github.com/nitrogen-project)| PixysOS                           | [Link](https://github.com/PixysOS) |
| Havoc-OS                          | [Link](https://github.com/Havoc-OS)       | Xtended                           | [Link](https://github.com/Project-Xtended) |
| ColtOS                            | [Link](https://github.com/Colt-Enigma)    | exTHmUI                           | [Link](https://github.com/exTHmUI) |


* And tons of other ROMs not mentioned above

