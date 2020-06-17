---
title: Opening an Existing Project
order: 2
---

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

> To enable certain features for MCP modules, for instance any feature which requires Minecraft Dev to have access to the
> SRG maps, a Gradle re-import will be necessary. This is because Minecraft Dev has to ask ForgeGradle for the location
> of the SRG maps. This only needs to happen once for each project configuration. So, if you have to run
> `setupDecompoWorkspace` then you'll need to re-import the Gradle project in IntelliJ again to update the SRG map
> locations. Since you should already do that anyways to update your dependencies after running `setupDecompWorkspace`,
> this shouldn't be any different than what you already do.
>
> Click the blue refresh button on the top left side of the Gradle tool window and let it finish. For large projects this
> could take some time. When it completes this process the project should be correctly marked as a Minecraft project.

If you still have troubles getting a project to be identified, please don't hesitate to open a new issue on our
[issue tracker](https://github.com/minecraft-dev/MinecraftDev/issues)! We greatly appreciate it when people bring
bugs to our attention, so we can focus on making Minecraft Dev as great as possible.
