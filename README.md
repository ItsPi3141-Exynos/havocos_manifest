# Havoc-OS

> [!WARNING]
> **This is ONLY for the Exynos 8895 devices!** This includes `dreamlte`, `dream2lte`, and `greatlte`.
>
> It will not work with other devices unless you make your own modifications.

## Getting Started

To get started with the Havoc-OS sources, you'll need to get
familiar with [Git and Repo](https://source.android.com/setup/develop).

## Create the Directories

You will need to set up some directories in your build environment.

To create them run:

```bash
mkdir -p ~/bin
mkdir -p ~/havoc
```

## Install `repo`

Enter the following to download the `repo` binary and make it executable:

```bash
curl <http://commondatastorage.googleapis.com/git-repo-downloads/repo> > ~/bin/repo && chmod a+x ~/bin/repo
```

You may need to reboot for these changes to take effect.
Now enter the following to initialize the repository:

## Initialise the repository

```bash
cd ~/havoc
repo init -u https://github.com/ItsPi3141-Exynos/android_manifest.git -b thirteen --git-lfs
```
  
## Sync the repository

```bash
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```

## Build

> [!NOTE]
> Please note that if you are building on Mac OS X, you are required to install coreutils from MacPorts before you continue.

Initialize the environment with the envsetup.sh script.

```bash
. build/envsetup.sh
brunch lineage_<codename>-userdebug
```

Enter one of the following for `<codename>`

- `dreamlte`
- `dream2lte`
- `greatlte`
