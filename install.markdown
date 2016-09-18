---
layout: page
title: Install Minecraft Dev IntelliJ
---

## Getting alpha builds

Minecraft Dev IntelliJ is currently in the _alpha_ stage of development. When we reach some acceptable level of
stability, we publish alpha builds to the IntelliJ's main plugin [repository](https://plugins.jetbrains.com/plugin/8327).
You can download and install these builds directly from `Plugins > Browse repositories` screen in your IDE.

As this is a preview release, something might go wrong. Hopefully you won't find any bugs, but if you do, we would
appreciate very much if you filed an [issue](https://github.com/DemonWav/MinecraftDevIntelliJ/issues)
on our bugtracker or ping us in our [chat](/chat/) (ping DemonWav).

## Setting up pre-release builds

In addition to preview releases, we also ship pre-release builds of _Minecraft Dev IntelliJ_ in separate channels.

To use them, open the `Find Action` dialog by pressing the key combo `Ctrl-Alt-A` (or `Cmd-Alt-A` on Mac). Type
`Configure Minecraft Development Plugin Updates` and press `Enter`. This will bring up a window which will allow you
to change your channel at any time.

Due to a quirk with how IntelliJ handles plugin updates, you may not be able to automatically move from a pre-release
channel back to stable. If this happens, you will need to manually uninstall the plugin and reinstall it after selecting
the stable channel.

Pre-release builds are builds targeting a new feature. They may not have all the latest and greatest features of the
main `Stable` channel, but we try our best to keep them in sync. If you find issues with a pre-release build please
file a bug report on our [issue](https://github.com/DemonWav/MinecraftDevIntelliJ/issues) tracker, or ping us in our
[chat](/chat/) (ping DemonWav).

## Compatible IDEs

The plugin should be compatible with Intellij IDEA Ultimate or Community Edition from 2016.1 or newer.
See `Help > About` menu in the IDE to learn the build version you are using.
