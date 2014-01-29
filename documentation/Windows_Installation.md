Windows Installation
================

### Install Cygwin ##
Cygwin is a large collection of GNU and other tools which provide Linux distribution-like functionality for Windows. 

Install [Cygwin](http://cygwin.com/install.html) to get a Linux feel on Windows.

### Update Java ##
Install the [latest Java](http://java.com/en/download/index.jsp). This guide was written using Java Version 7 Update 51.

### Install JDK ##
Install the [latest JDK](http://www.oracle.com/technetwork/java/javase/downloads/index.html). This guide was written using JDK 7u51.

### Install Ruby ##
Install [latest Ruby for Windows](http://rubyinstaller.org/). This guide was written using Ruby 2.0.0-p353.

### Install Git ##
Install [Git for Windows](http://git-scm.com/download/win)

## Android Installation #

### Install Android Studio ##
Install the [latest Android Studio for Windows](http://developer.android.com/sdk/installing/studio.html) on your system.

>*Known issue:* On some Windows systems, the launcher script does not find where Java is installed.

>If you encounter this problem, you need to set an environment variable indicating the correct location. Select **Start menu > Computer > System Properties > Advanced System Properties**. Then open **Advanced tab > Environment Variables** and add a new system variable **JAVA_HOME** that points to your JDK folder, for example C:\Program Files\Java\jdk1.7.0_21. 

### Install Android SDK ##
You'll want to install the [latest Android SDK for Windows](https://developer.android.com/sdk/index.html) on your system.

 * Download Android SDK

 * Copy 'sdk' subfolder of the Android SDK you downloaded to /Users/&lt;username>/Android/sdk

 * Set environment variable ANDROID_HOME to ~/Android/sdk

        export ANDROID_HOME=~/Android/sdk

### Update PATH ##
Add Ruby and Android SDK to your path. To make these changes permanent, add the **PATH** commands to your .cshrc file (for csh and tcsh), .profile file (for sh and ksh), or .bash_profile file (for bash).

	.bash_profile example:
	PATH="/cygdrive/c/Ruby200/bin:/cygdrive/c/Android/sdk/platform-tools:${PATH}"

### Add alias commands ##
Add aliases for `gem` and `calabash-android` commands. To make these changes permanent, add the **alias** commands to your .cshrc file (for csh and tcsh), .profile file (for sh and ksh), or .bash_profile file (for bash).

	.bash_profile example:
	alias gem='C:/Ruby200/bin/gem'
	alias calabash-android='C:/Ruby200/bin/calabash-android'

Update `~/.bashrc` and alias `gem` and `calabash-android` commands.
     
        alias gem='C:/Ruby200/bin/gem'
        alias calabash-android='..../calabash-android'

### Install RSpec ##
Install [RSpec](http://rspec.info/)

    gem install rspec

### Calabash Android ##
We use [Calabash Android](https://github.com/calabash/calabash-android/blob/master/documentation/installation.md). You'll need to follow their [installation instructions](https://github.com/calabash/calabash-android/blob/master/documentation/installation.md) to get things working on your system.

Unless you set the environment variable ANDROID_HOME, the `calabash_android` command will fail with a runtime error.
Make sure you set ANDROID_HOME environment variable in the **Install Android SDK** section above.

### Running calabash-android ##
Launch calabash-android console

    calabash-android console <my.apk>

Launch calabash-android on device:

    calabash-android run <my.apk>

>*Known issue:* If you get the following error:
“No keystores found. Please create one or run calabash-android setup to configure calabash-android to use an existing keystore.”
>
>debug.keystore is missing, it can be recreated in ANDROID_HOME with the following command
>
>       keytool -genkey -v -keystore ~/.android/debug.keystore -alias androiddebugkey -storepass android -keypass \
>       android -keyalg RSA -keysize 2048 -validity 10000 -dname "CN=Android Debug,O=Android,C=US"
