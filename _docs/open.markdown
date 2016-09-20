---
title: Opening an Existing Project
order: 2
---

Minecraft Dev IntelliJ will attempt to recognize existing projects when they are opened, but this is an ongoing process
to perfect this system. Usually with Maven projects it will immediately recognize the project correctly and you can go
from there. Minecraft Dev IntelliJ uses the project's build system dependencies to determine if a project is a suitable
candidate or not.

Gradle projects aren't always so easy to get working. Due to how the Gradle plugin operates, it won't necessarily
refresh the project very time the project is opened. Usually if you open a Gradle project for the first time Minecraft
Dev IntelliJ will have no problem detecting it.

To manually refresh a Gradle project to get it to read as a Minecraft project, open the Gradle tool window by going to
`View > Tool Windows > Gradle`. This will open the Gradle tool window on the right side of the IDE. It will look like
this.

![Gradle Tool Window](/assets/gradletoolwindow.png)

Click the blue refresh button on the top left side of the Gradle tool window and let it finish. For large projects this
could take some time. When it completes this process the project should be correctly marked as a Minecraft project.

If you still have troubles getting a project to be identified, please don't hesitate to open a new issue on our
[issue tracker](https://github.com/DemonWav/MinecraftDevIntelliJ/issues)! We greatly appreciate it when people bring
bugs to our attention, so we can focus on making Minecraft Dev IntelliJ as great as possible.
