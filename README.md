# Wrap stuff in Crosswalk (for Android)

Fist of all: This will probably only work on a Mac. I've tried this on Windows and failed miserably. I will not stop you from trying, but this guide will be the reference for the workflow on MacOS. I'm sorry.

Also, please note that Crosswalk was discontinued on February 2017 so it won't be receiving any updates. If you find critical bugs, fork [their repo](https://github.com/crosswalk-project/crosswalk) and try to fix it yourself.

## Install Crosswalk

As of writing this there are already critical bugs that require an alteration in the installation process of Crosswalk.

**The easy stuff**

Folow this [Guide](https://crosswalk-project.org/documentation/android/system_setup.html#Crosswalk), which involves installing Java JDK, NPM, Apache ANT and NodeJS

**The tricky part**

As mentioned earlier Crosswalk was discontinued and updates on the Android SDK broke it. So we can't just use the Android SDK installed via Android Studio, because that has installed the most recent versions of the SDK which **won't work**.
So before doing anything with Crosswalk, please download and unzip the [Android SDK Tools 25.2.1](https://dl.google.com/android/repository/tools_r25.2.1-macosx.zip) to your Downloads folder. You should now have a folder called `tools` in your Downloads folder (`~/Downloads`, I assume).
Now open a Terminal and do as follows:

 1. Rename  up-to-date SDK folder:
 `$ mv ~/Library/Android/sdk ~/Library/Android/sdk-new`

 2. Create new SDK folder:
 `$ mkdir ~/Library/Android/sdk`

 3. Move old SDK tools version to your Library:
 `$ mv ~/Downloads/tools ~/Library/Android/sdk/tools`

 4. Launch SDK Manager:
 `$ ~/Library/Android/sdk/tools/android sdk`

 5. Now install SDKs API22 and API23 and **deselect** API24 and above if preselected. It might not be an issue if anything above 24 is installed, but, you know, just in case. When prompted that your SDK stuff is outdated and you should update **please don't**.

You can now check your installation with `crosswalk-app check android`. Quoting Crosswalk:

> If any items report missing, add the directory to the program binaries in your PATH. Note: Currently the tool reports an ERROR if lzma is not found. You can safely ignore this for now.

Everything else is according to plan. You can follow this [Guide](https://crosswalk-project.org/documentation/android/build_an_application.html). Godspeed.

## Introduction

Crosswalk is an app runtime based on Chromium/Blink.

It is an open source project started by the Intel Open Source Technology Center
(http://www.01.org)

As of February 2017, Crosswalk is not being developed anymore. The last Crosswalk relase is 23.

## Documents

Check out our [wiki](http://crosswalk-project.org/#wiki).

## Community

How to use Crosswalk you can ask on the mailing list: https://lists.crosswalk-project.org/mailman/listinfo/crosswalk-help

Development of Crosswalk: https://lists.crosswalk-project.org/mailman/listinfo/crosswalk-dev

We are also on IRC: `#crosswalk` @ `chat.freenode.net`

## License

Crosswalk's code uses the 3-clause BSD license, see our `LICENSE` file.
