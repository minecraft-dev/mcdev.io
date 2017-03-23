---
title: FAQ
order: 100
---

{% include h title="What platforms are supported?" tag="platforms" %}

Minecraft Dev supports all of the major Java Minecraft development platforms. These include:

- [![Bukkit Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/2017.1/src/main/resources/assets/icons/platform/Bukkit.png?raw=true) **Bukkit**](https://hub.spigotmc.org/stash/projects/SPIGOT/repos/bukkit/browse) ([![Spigot Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/2017.1/src/main/resources/assets/icons/platform/Spigot.png?raw=true) Spigot](https://spigotmc.org/) and [![Paper Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/2017.1/src/main/resources/assets/icons/platform/Paper.png?raw=true) Paper](https://paper.emc.gs))
- [![Sponge Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/2017.1/src/main/resources/assets/icons/platform/Sponge_dark.png?raw=true) **Sponge**](https://www.spongepowered.org/)
- [![Forge Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/2017.1/src/main/resources/assets/icons/platform/Forge.png?raw=true) **Minecraft Forge**](http://minecraftforge.net/forum)
- [![LiteLoader Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/2017.1/src/main/resources/assets/icons/platform/LiteLoader.png?raw=true) **LiteLoader**](http://www.liteloader.com/)
- [![MCP Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/2017.1/src/main/resources/assets/icons/platform/MCP.png?raw=true) **MCP**](http://www.modcoderpack.com/)
- [![Mixins Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/2017.1/src/main/resources/assets/icons/platform/Mixins_dark.png?raw=true) **Mixins**](https://github.com/SpongePowered/Mixin)
- [![BungeeCord Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/2017.1/src/main/resources/assets/icons/platform/BungeeCord.png?raw=true) **BungeeCord**](https://www.spigotmc.org/wiki/bungeecord/)
- [![Canary Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/2017.1/src/main/resources/assets/icons/platform/Canary.png?raw=true) **Canary**](https://canarymod.net/) ([![Neptune Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/2017.1/src/main/resources/assets/icons/platform/Neptune.png?raw=true) Neptune](https://www.neptunepowered.org/))

{% include h title="I found a bug. What should I do?" tag="bug" %}

If you find a problem with the plugin, please report it to our [issue tracker](https://github.com/DemonWav/MinecraftDev/issues).
We try to deal with bugs as quickly as possible and take the quality of this plugin very seriously.

{% include h title="I have an idea for a new feature." tag="feature" %}

If you have any feature requests for any of the supported platforms, please use the [issue tracker](https://github.com/DemonWav/MinecraftDev/issues)
to suggest it and we'll let you know if it's in the scope for what we are trying to do. We might not always implement
every feature immediately, but we are always on the lookout for new features to implement and we would love to hear your
ideas!

{% include h title="How do I install this plugin in IntelliJ?" tag="install" %}

Installation instructions are available [here](https://minecraftdev.org/install.html).

{% include h title="How can I install a pre-release build to test in IntelliJ?" tag="install-pre" %}

Installation instructions for pre-release builds are available [here](https://minecraftdev.org/install.html).

{% include h title="I installed the plugin and it didn't detect my current projects. What can I do?" tag="detect" %}

Usually Maven projects will be detected immediately on startup, but Gradle projects won't always automatically detect.
Minecraft Dev plugs into the Maven and Gradle plugin loading system to gather information about the project, so
sometimes a project refresh is necessary to re-detect the project as a Minecraft project.

For Maven to refresh the project, right click on the `pom.xml` and choose `Maven -> Reimport`.

For Gradle to refresh the project, open the Gradle tool window by going to `View -> Tools Windows -> Gradle` and click
the blue refresh button in the tool window.

{% include h title="How do I know if my project is detected as a Minecraft project?" tag="detect-visual" %}

The module icon will change to the icon of the platform contained in the module.
