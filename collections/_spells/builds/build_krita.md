---
layout: spell
date: 26-12-2024
---

Succesful build on 26th December 2025 on macOS Sonoma 14.6.1

<br>

Requirements:
```shell
brew install --formula cmake
brew install --formula python@V.vv 
brew install --cask qt-creator
```

Install Xcode from App Store, not available in homebrew.  Ensure you open the XCode app to accept terms and to actually install it.
```shell
# Set where to use locate Xcode build tools.
sudo xcode-select -s /Applications/Xcode.app/Contents/Developer
```

<br>

Set up a build environment for Krita:
```shell
# Creates a shell variable relative to users's machine. 
# Variable is temporary and only lasts for the current terminal session.
export BUILDROOT=$HOME/dev_krita
mkdir -p $BUILDROOT
```

```shell
# The Krita repository is hosted on the KDE repository platform as a proxy to GitLab.
cd $BUILDROOT
git clone https://invent.kde.org/graphics/krita.git

# Specific dependency manager and continuous integration utilities need to be included.
# Repositories belong to Dmitry Kazakov who is involved with the development of Krita over multiple years.
# See https://fund.krita.org/grants/ for details.
# Note: this isn't Ramon Miranda who is the usual face on Krita's youtube channel.
cd krita
git clone https://invent.kde.org/dkazakov/krita-deps-management.git krita-deps-management --depth=1
git clone https://invent.kde.org/dkazakov/ci-utilities.git krita-deps-management/ci-utilities --depth=1

# Establish venv environment for running build scripts
# Requirements txt file recursively installs requirements from two locations:
# 1. krita-deps-management/requirements-setup-tools.txt which points to https://github.com/dimula73, Dmitry Kazakov's personal github
## setuptools is a python package similar to pip...
# 2. krita-deps-management/requirements-base.txt which several utilities with hash checks?
python3 -m venv $BUILDROOT/venv --upgrade-deps
source $BUILDROOT/venv/bin/activate
pip install -r krita-deps-management/requirements.txt
```

<br>

More build tools...
```shell
cd $BUILDROOT
# Set up own shell environment variable for EXTERNALS_DOWNLOAD_DIR since it doesn't seem to exist...
export EXTERNALS_DOWNLOAD_DIR=$BUILDROOT/3rd_party
mkdir -p $EXTERNALS_DOWNLOAD_DIR
# The below command now works instead of throwing errors on line 17!
python3 $BUILDROOT/krita/krita-deps-management/tools/download-macos-tools.py
source $BUILDROOT/_krita-tools/activate
```

```shell
cd $BUILDROOT/krita
source $BUILDROOT/venv/bin/activate
source $BUILDROOT/_krita-tools/activate # if you used CI build tools

python krita-deps-management/tools/setup-env.py --full-krita-env -v $BUILDROOT/venv -p $BUILDROOT/$KDECI_CRAFT_PLATFORM/dev-utils/bin/
```

```shell
export BUILDROOT=$HOME/dev_krita
export EXTERNALS_DOWNLOAD_DIR=$BUILDROOT/3rd_party
cd $BUILDROOT/krita
# Activate the build environment (you don't need to activate
# any previous environments, like Python's venv environment;
# everything is included in this ``env`` file)
source $BUILDROOT/krita/env
source $BUILDROOT/_krita-tools/activate # if you used CI build tools

mkdir -p _build
cd _build

# Generates a whole listing inside _build in order to succesfully build Krita
# Configure Krita as usual.
# Note the -GNinja flag which specifies Ninja as the build system generator.
# See cmake --help for more details, look at -G flag. 
# See [CMake and Ninja | Build Automation](https://www.youtube.com/watch?v=4TwW0CgBh9s)
cmake -DCMAKE_BUILD_TYPE=RelWithDebInfo \
      -DHIDE_SAFE_ASSERTS=OFF \
      -DBUILD_TESTING=ON \
      -DCMAKE_INSTALL_PREFIX=$BUILDROOT/krita/_install \
      -DCMAKE_TOOLCHAIN_FILE=$BUILDROOT/krita/krita-deps-management/tools/macos-toolchain-krita.cmake \
      $BUILDROOT/krita -GNinja

# Build and Install krita to $BUILDROOT/krita/_install/bin/krita.app
# -j8 flag runs 8 builds in parallel...
ninja -j8 install
# .
# .
# ... after a long time for building the project for the first time
#
#
# Run Krita for the first time, can take awhile on first boot:
$BUILDROOT/krita/_install/bin/krita.app/Contents/MacOS/krita

# Deactivate the Krita build environment.
source $BUILDROOT/krita/env_deactivate
```

### Quick-Run

Run Krita development environment.
```shell
export BUILDROOT=$HOME/dev_krita
export EXTERNALS_DOWNLOAD_DIR=$BUILDROOT/3rd_party
source $BUILDROOT/krita/env
source $BUILDROOT/_krita-tools/activate
ninja -j8 install
$BUILDROOT/krita/_install/bin/krita.app/Contents/MacOS/krita
source $BUILDROOT/krita/env_deactivate
```

### Footnotes

cmake build generation debriefing:
```shell
# After running:
cmake -DCMAKE_BUILD_TYPE=RelWithDebInfo \
      -DHIDE_SAFE_ASSERTS=OFF \
      -DBUILD_TESTING=ON \
      -DCMAKE_INSTALL_PREFIX=$BUILDROOT/krita/_install \
      -DCMAKE_TOOLCHAIN_FILE=$BUILDROOT/krita/krita-deps-management/tools/macos-toolchain-krita.cmake \
      $BUILDROOT/krita -GNinja

# .
# .
# ... Lots of output and then:

# -- The following features have been disabled:

#  * Hide safe asserts, Don't show message box for "safe" asserts, just ignore them automatically and dump a message to the terminal.
#  * Install benchmarks, Install benchmarks into the installation root to make them packagable
#  * Crash on safe asserts, Crash unconditionally whenever a "safe" assert happens. Useful for running unittests
#  * Foundation Build, A Foundation build is a binary release build that can package some extra things like color themes. Linux distributions that build and install Krita into a default system location should not define this option to true.
#  * Enable Broken Tests, Runs broken test when "make test" is invoked (use -DKRITA_ENABLE_BROKEN_TESTS=ON to enable).
#  * Build Qt Designer plugins, Builds Qt Designer plugins for Krita widgets (use -DBUILD_KRITA_QT_DESIGNER_PLUGINS=ON to enable).
#  * Precompiled Headers, precompiled headers make build process faster on some systems
#  * ASAN address sanitizer, crash Krita if it violates address access rules (-DECM_ENABLE_SANITIZERS=address)
 ```


 ```shell
# The install prefix for Krita with all the deps preinstalled
cd $BUILDROOT/krita/_install
# The build folder for Krita
cd $BUILDROOT/krita/_build 

# Activate build environment
source $BUILDROOT/krita/env
# Deactivate build environment
source $BUILDROOT/krita/env_deactivate
```