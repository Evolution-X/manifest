![Evolution X](https://github.com/Evolution-X/manifest/raw/ten/EvoBanner.png)

# Evolution X #

[![Download Evolution X](https://img.shields.io/sourceforge/dt/evolution-x.svg)](https://sourceforge.net/projects/evolution-x/files/latest/download)

### Sync ###

```bash

# Initialize local repository
repo init -u https://github.com/Evolution-X/manifest -b fod

# Sync
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```

### Build ###

```bash

# Set up environment
$ . build/envsetup.sh

# Choose a target
$ lunch aosp_$device-userdebug

# Build the code
$ mka bacon -jX
```
