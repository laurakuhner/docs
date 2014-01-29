Mac Installation
================

### Install Homebrew ##
Install the [latest Homebrew](http://brew.sh/) on your system.

    ruby -e "$(curl –fsSL https://raw.github.com/mxcl/homebrew/go/install)"

### Install Ruby ##
Install [latest ruby 2.0.0](https://www.ruby-lang.org/en/downloads/) using RVM (“Ruby Version Manager”).

    \curl -L https://get.rvm.io | bash -s stable --ruby

### Install RSpec ##
Install [RSpec](http://rspec.info/)

    gem install rspec

## Android Installation #

### Install Android Studio ##
Install the [latest Android Studio](http://developer.android.com/sdk/installing/studio.html) on your system.

>*Known issue:* Depending on your security settings, when you attempt to open Android Studio, you might see a warning that says the package is damaged and should be moved to the trash _OR_ "Android Studio" can't be opened because it is from an unidentified developer.

>If this happens, go to Mac **System Preferences > Security & Privacy > General** and under **Allow applications downloaded from:**, select **Anywhere**. Then open Android Studio again.

### Install Android SDK ##
You'll want to install the [latest Android SDK](https://developer.android.com/sdk/index.html) on your system.

 * Download Android SDK

 * Copy 'sdk' subfolder of the Android SDK you downloaded to /Users/&lt;username>/Android/sdk

 * Set environment variable ANDROID_HOME to ~/Android/sdk

        export ANDROID_HOME=~/Android/sdk

### Calabash Android ##
We use [Calabash Android](https://github.com/calabash/calabash-android/blob/master/documentation/installation.md). You'll need to follow their [installation instructions](https://github.com/calabash/calabash-android/blob/master/documentation/installation.md) to get things working on your system.

Unless you set the environment variable ANDROID_HOME, the `calabash_android` command will fail with a runtime error.
Make sure you set ANDROID_HOME environment variable in the **Install Android SDK** section above.

