---
title: Creating a New Project
order: 1
---

Creating a new project is very easy with Minecraft Dev. You can either create a new standalone project, or
create it as a new module in an existing (or empty) project. To create a new standalone project, choose
`File > New > Project`, and you'll be presented with a window similar to this. You may not have all the same options for
project types, but as long as you have Minecraft Dev installed, you should see the `Minecraft` generator.

Select the `Minecraft` generator, you will be presented with the platforms it supports, grouped by kind,
e.g. `Mod` for Forge and Fabric, `Plugin` for Paper and Sponge, `Proxy` for BungeeCord and Velocity.

![Paper Plugin Creator](/assets/gettingstarted/paper-creator.png)

First we want to set the project or module name, some fields below will be updated automatically based on it.
Then we can select the platform we want to generate a project for.

The following fields and options will depend on the selected platform. Most will have an option for the Build System
(`Gradle` or `Maven`) and a language (`Java` and `Kotlin`), choose whichever you would like to use.

Following that is one or more version dropdowns for Minecraft, and maybe the platform and/or libraries or tools that
platform uses.

The `Optional Settings` group (if it is present) will contain a few fields for some common metadata you might want to
set and reuse between different projects, like `Authors` (the creator will remember the values of most fields.)

Make sure to set the `Group ID` (under `Build System Properties`) appropriately. The default one is considered
invalid on purpose, please read the short
[standard naming convention](https://maven.apache.org/guides/mini/guide-naming-conventions.html) for an idea of what
`Group ID` and `Artifact ID` should be.

![Build System Properties](/assets/gettingstarted/creator-build-system-properties.png)

The last thing before creating the project is to make sure we have a compatible JDK installed and configured. If not we
can download one right from the JDK dropdown.

Once this is done we can create the project. The Gradle or Maven project will be imported automatically. This might take
some time depending on the platform, your download speed and computer specs, especially for mod projects.

The main files will also be opened in the editor, ready to be modified. Enjoy!

![Blank Project](/assets/gettingstarted/paper-blank-project.png)
