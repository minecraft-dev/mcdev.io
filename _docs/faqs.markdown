---
title: FAQ
order: 100
---

{% include h title="What platforms are supported?" tag="platforms" %}

Minecraft Development IntelliJ supports all of the major Java Minecraft development platforms. These include:

- [![Bukkit Icon](https://github.com/DemonWav/MinecraftDevIntelliJ/raw/master/src/main/resources/assets/platform/icons/Bukkit.png) **Bukkit**](https://hub.spigotmc.org/stash/projects/SPIGOT/repos/bukkit/browse) ([![Spigot Icon](https://github.com/DemonWav/MinecraftDevIntelliJ/raw/master/src/main/resources/assets/platform/icons/Spigot.png) Spigot](https://spigotmc.org/) and [![Paper Icon](https://github.com/DemonWav/MinecraftDevIntelliJ/raw/master/src/main/resources/assets/platform/icons/Paper.png) Paper](https://paper.emc.gs))
- [![Sponge Icon](https://github.com/DemonWav/MinecraftDevIntelliJ/raw/master/src/main/resources/assets/platform/icons/Sponge.png) **Sponge**](https://www.spongepowered.org/)
- [![Forge Icon](https://github.com/DemonWav/MinecraftDevIntelliJ/raw/master/src/main/resources/assets/platform/icons/Forge.png) **Minecraft Forge**](http://minecraftforge.net/forum)
- [![LiteLoader Icon](https://github.com/DemonWav/MinecraftDevIntelliJ/raw/master/src/main/resources/assets/platform/icons/LiteLoader.png) **LiteLoader**](http://www.liteloader.com/)
- [![BungeeCord Icon](https://github.com/DemonWav/MinecraftDevIntelliJ/raw/master/src/main/resources/assets/platform/icons/BungeeCord.png) **BungeeCord**](https://www.spigotmc.org/wiki/bungeecord/)

{% include h title="I found a bug. What should I do?" tag="bug" %}

If you find a problem with the plugin, please report it to our [issue tracker](https://github.com/DemonWav/MinecraftDevIntelliJ/issues).
We try to deal with bugs as quickly as possible and take the quality of this plugin very seriously.

{% include h title="I have an idea for a new feature." tag="feature" %}

If you have any feature requests for any of the supported platforms, please use the [issue tracker](https://github.com/DemonWav/MinecraftDevIntelliJ/issues)
to suggest it and we'll let you know if it's in the scope for what we are trying to do. We might not always implement
every feature immediately, but we are always on the lookout for new features to implement and we would love to hear your
ideas!

{% include h title="How do I install this plugin in IntelliJ?" tag="install" %}

Installation instructions are available [here](https://minecraftdev.org/install.html).

{% include h title="How can I install a pre-release build to test in IntelliJ?" tag="install-pre" %}

Installation instructions for pre-release builds are available [here](https://minecraftdev.org/install.html).

{% include h title="I installed the plugin and it didn't detect my current projects. What can I do?" tag="detect" %}

Usually Maven projects will be detected immediately on startup, but Gradle projects won't always automatically detect.
Minecraft Dev IntelliJ plugs into the Maven and Gradle plugin loading system to gather information about the project, so
sometimes a project refresh is necessary to re-detect the project as a Minecraft project.

For Maven to refresh the project, right click on the `pom.xml` and choose `Maven -> Reimport`.

For Gradle to refresh the project, open the Gradle tool window by going to `View -> Tools Windows -> Gradle` and click
the blue refresh button in the tool window.

{% include h title="How do I know if my project is detected as a Minecraft project?" tag="detect-visual" %}

The module icon will change to the icon of the platform contained in the module.
