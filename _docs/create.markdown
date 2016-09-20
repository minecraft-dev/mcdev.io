---
title: Creating a New Project
order: 1
---

Creating a new project is very easy with Minecraft Dev IntelliJ. You can either create a new standalone project, or
create it as a new module in an existing (or empty) project. To create a new standalone project, choose
`File > New > Project`, and you'll be presented with a window similar to this. You may not have all the same options for
project types, but as long as you have Minecraft Dev IntelliJ installed, you should see the `Minecraft Project`
category.

![Project Type Select](/assets/gettingstarted/projecttype.png)

Select the `Minecraft Plugin` category, and you will have these different options for platforms to choose from. You can
select multiple options together if that's what makes sense for your project. For example, in the image above, I have
`Sponge` and `Forge` selected, since I want to make a Sponge plugin that also uses some of the Forge modding API's. You
are free to mix and match however you need, and it will create the project accordingly.

When we click next, in this case, we'll be asked what kind of combined project we wish to create.

![Combo Project Select](/assets/gettingstarted/comboproject.png)

This is only true for the `Sponge` and `Forge` combination, since it is a special case. In all other cases we know
assume you want separate modules for your projects, since that's usually what makes sense. If that's not what you want,
it's always very easy to merge the modules together after they have been created.

Since I want to create separate modules, I'll select the second option and click next. Here it will ask for the build
system settings, such as `groupId`, `artifiactId`, and `version`. In some cases it will allow you to choose between
`Maven` and `Gradle`, but it doesn't allow us to choose for two reasons in this case:

 1. We selected a combination project, and Gradle is the only build system supported for such builds
 2. We selected Forge as one of our platforms, which requires Gradle
 
If you select a Bukkit, Sponge, or BungeeCord project you will be able to change the build system to Maven if you wish

The `groupId` and `artifactId` fields should follow certain guidelines. You can view these guidelines
[here](https://maven.apache.org/guides/mini/guide-naming-conventions.html). It's a short read, so please take a few
seconds to read and understand it so you follow the standard conventions.

After I filled in my info, I click next and I am presented with an initial settings page for Sponge.

![Sponge Settings Page](/assets/gettingstarted/spongesettings.png)

The required fields are all pre-filled in based off of the settings from the build system page we just entered. Here I
entered the `groupID` `com.demonwav` and the `artifactId` `example`, so it assumed the project name is `Example`, and
built the main class name off of that as well.

You may fill in the other optional settings if you wish, and click next when you are ready to continue. The next page
is much the same, but for Forge. There's a few more required settings (which are also automatically set) for Forge,
and it's set by calling the Forge API, which may take a few seconds.

![Forge Settings Page](/assets/gettingstarted/forgesettings.png)

This is much the same as last time, feel free to input or change whichever settings you want. The `Plugin Name` field is
grayed out because that was already set in the previous screen and can't be changed again. You cna go back to the
previous page if you want to change the plugin name.

After clicking next on this page you will be presented with the module info page, asking what to call the project and
where to put it.

![Project Settings Page](/assets/gettingstarted/projectsettings.png)

Once you have set the name and path to what you want, and click next, it will automatically create your project based
on the settings you gave it. For `Forge` and `LiteLoader` projects this may take a considerable amount of time, as the
automatic project creator will run `./gradlew setupDecompWorkspace` for you, which can take a lot of time, especially
if you haven't ran it before.

Once it has finished building the project skeleton, it will import it with `Maven` or `Gradle`, depending on what you
chose. Maven import is very fast and is automatic, Gradle import opens a dialog window asking you to verify some
settings first.

![Gradle Settings Page](/assets/gettingstarted/gradlesettings.png)

Fill out this page however you normally would, there is nothing special about it.

And after that you will have a blank project to work with!

![Blank Project](/assets/gettingstarted/blankproject.png)
