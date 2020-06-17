---
layout: page
title: Install Minecraft Dev
permalink: /install/
---

## Installing

You can download and install these builds directly from `Plugins > Browse repositories` screen in your IDE.

Hopefully you won't find any bugs, but if you do, we would appreciate if you opened an
[issue](https://github.com/minecraft-dev/MinecraftDev/issues).

## Setting up nightly builds

In addition to normal releases, we also ship nightly builds of _Minecraft Dev_ in separate channels.

To configure nightly builds open the `Find Action` dialog by pressing the key combo `Ctrl-Alt-A`
(or `Cmd-Alt-A` on Mac). Type `Configure Minecraft Development Plugin Updates` and press `Enter`. This will bring up a
window which will allow you to change your channel at any time.

Due to a quirk with how IntelliJ handles plugin updates, you may not be able to automatically move from a pre-release
channel back to stable. If this happens, you will need to manually uninstall the plugin and reinstall it after selecting
the stable channel.

Nightly builds are built every night whenever there are changes since the previous night. If you find issues with a
nightly build please file a bug report on our [issue](https://github.com/minecraft-dev/MinecraftDev/issues) tracker.

## Compatible IDEs

The plugin is compatible with Intellij IDEA Ultimate or Community Edition.
