---
title: FAQ
order: 100
permalink: /docs/faqs/
---

{% include h title="What platforms are supported?" tag="platforms" %}

Minecraft Dev supports all of the major Java Minecraft development platforms. These include:

- [![Bukkit Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/dev/src/main/resources/assets/icons/platform/Bukkit.png?raw=true) **Bukkit**](https://hub.spigotmc.org/stash/projects/SPIGOT/repos/bukkit/browse) ([![Spigot Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/dev/src/main/resources/assets/icons/platform/Spigot.png?raw=true) Spigot](https://spigotmc.org/) and [![Paper Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/dev/src/main/resources/assets/icons/platform/Paper.png?raw=true) Paper](https://paper.emc.gs))
- [![Sponge Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/dev/src/main/resources/assets/icons/platform/Sponge_dark.png?raw=true) **Sponge**](https://www.spongepowered.org/)
- [![Forge Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/dev/src/main/resources/assets/icons/platform/Forge.png?raw=true) **Minecraft Forge**](http://minecraftforge.net/forum)
- [![Fabric Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/dev/src/main/resources/assets/icons/platform/Fabric.png?raw=true) **Fabric**](https://fabricmc.net/)
- [![LiteLoader Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/dev/src/main/resources/assets/icons/platform/LiteLoader.png?raw=true) **LiteLoader**](http://www.liteloader.com/)
- [![MCP Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/dev/src/main/resources/assets/icons/platform/MCP.png?raw=true) **MCP**](http://www.modcoderpack.com/)
- [![Mixins Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/dev/src/main/resources/assets/icons/platform/Mixins_dark.png?raw=true) **Mixins**](https://github.com/SpongePowered/Mixin)
- [![BungeeCord Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/dev/src/main/resources/assets/icons/platform/BungeeCord.png?raw=true) **BungeeCord**](https://www.spigotmc.org/wiki/bungeecord/) ([![Waterfall Icon](https://raw.githubusercontent.com/minecraft-dev/MinecraftDev/dev/src/main/resources/assets/icons/platform/Waterfall.png?raw=true) Waterfall](https://github.com/PaperMC/Waterfall))

{% include h title="I found a bug. What should I do?" tag="bug" %}

If you find a problem with the plugin, please report it to our [issue tracker](https://github.com/minecraft-dev/MinecraftDev/issues).
We try to deal with bugs as quickly as possible and take the quality of this plugin very seriously.

In some cases, you may be able to report an exception related to the Minecraft Dev plugin directly through IntelliJ. If you choose to do this, the reported stack traces could include sensitive information such as package names or source code. This data will be publicly accessible and searchable through the issue tracker.

{% include h title="I have an idea for a new feature." tag="feature" %}

If you have any feature requests for any of the supported platforms, please use the [issue tracker](https://github.com/minecraft-dev/MinecraftDev/issues)
to suggest it and we'll let you know if it's in the scope for what we are trying to do. We might not always implement
every feature immediately, but we are always on the lookout for new features to implement and we would love to hear your
ideas!

{% include h title="How do I install this plugin in IntelliJ?" tag="install" %}

Installation instructions are available [here](/install/).

{% include h title="How can I install a nightly build to test in IntelliJ?" tag="install-nightly" %}

Installation instructions for pre-release builds are available [here](/install/).

{% include h title="I installed the plugin and it didn't detect my current projects. What can I do?" tag="detect" %}

Usually projects will be detected immediately on startup. Minecraft Dev checks the individual libraries to determine if
the modules are applicable. If it's not detected immediately on startup, you can try refreshing your build system, to
cause the module structure to update, forcing Minecraft Dev to check the dependencies again.

If that doesn't work, however, you can manually enable Minecraft Dev features on any module by registering the Minecraft
Dev facet on that module. Go to `File -> Project Structure -> Modules`. You want to register the relevant modules which
contain the source set you're interested in. For module groups, this means selecting the child modules, rather than the
parents. This can often be the case for Gradle projects. If you aren't sure, click on the module and check the
dependencies tab on the right. It will show you which dependencies are available for that module. If the module has no
dependencies then it may not be the module you're looking for.

Once you have determined the correct module, right click on it and choose `Add`, and select `Minecraft`. Then you can
de-select `Auto-detect` to manually override Minecraft Dev's detection of that particular platform type for that module.

{% include h title="How do I know if my project is detected as a Minecraft project?" tag="detect-visual" %}

The module icon will change to the icon of the platform contained in the module.

Additionally, the `Minecraft Facet` will automatically be registered for the relevant modules, which allows you to view
and set the correct project types, including hidden project types, such as MCP and Mixins.

To view this, simply go to `File -> Project Structure`, and either check the `Modules` or `Facets` tab.
