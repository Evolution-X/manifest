![Evolution X](https://github.com/Evolution-X/manifest/raw/ten/EvoBanner.png)

# Evolution X #

[![Download Evolution X](https://img.shields.io/sourceforge/dt/evolution-x.svg)](https://sourceforge.net/projects/evolution-x/files/latest/download)

### Sync ###

```bash

# Clone build repository
$ git clone https://github.com/Evolution-X/build

# Set up environment for sync
$ . build/envsetup.sh

# Sync for the first time
$ repofirstsync

# Sync for the second times and later on
$ reposync
```

### Build ###

```bash

# Set up environment
$ . build/envsetup.sh

# Choose a target
$ lunch aosp_$device-userdebug

# Build the code
$ mka bacon
```
