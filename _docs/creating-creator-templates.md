---
title: Creating Creator Templates
order: 3
permalink: /docs/creating-creator-templates/
---

The project creator is based on templates containing [Apache Velocity](https://velocity.apache.org/) files and
properties put together in a JSON descriptor file.

The built-in templates are hosted on [this GitHub repository](https://github.com/minecraft-dev/templates). Feel free
to use them as reference for your making your own.

This documentation will explain the essentials about how to make a project template.


{% include h title="Template Repositories" tag="repositories" %}

A template repository contains one or more descriptors and Velocity templates. You can configure repositories in the
plugin settings. By default, only the `Built In` repository is there, you can add as many as you want.

![Template Repositories Settings](/assets/creator-templates/minecraft-settings.png)

A repository provider is what reads the descriptor and the Velocity templates that the creator will use.
Currently, four providers available:
- `builtin` which is specifically made for the default templates
- `remote` downloads a zip from a URL and then reads its contents like the `archive` provider does
- `local` reads templates from a flat directory
- `archive` reads templates contained in a ZIP archive

Each provider has a configuration, like the URL of the remote ZIP file, or the flat directory to use as a root.

The `remote` provider has a version placeholder `$version` which will be replaced with the descriptor format version.
The goal is to allow users to host templates for multiple versions without requiring them to update the URL by
manually whenever the descriptor format version gets bumped, while allowing users on older versions to still be able
to access older templates.

This means that you as a maintainer will still need to keep up with the template versions. The plugin only supports one
descriptor format version at a time currently, but format changes do not necessarily imply breaking changes so you might
be fine simply pushing your existing templates to a new branch as-is.

![Remote Template Config Example](/assets/creator-templates/remote-provider-config-example.png)

This is what the Built-In template repo would look like using the `remote` provider. You can do something similar if
you host your templates in a GitHub repository. Note that we prepend the branch name with a `v`.


{% include h title="Template Descriptors" tag="descriptors" %}

The template descriptor is a JSON file of a specific format `version` containing the properties exposed to the Velocity
templates and to the user in the creator UI. The descriptor file name must end with `.mcdev.template.json`, and in fact
can be named just that.

For a complete reference see the [descriptor class sources](https://github.com/minecraft-dev/MinecraftDev/blob/dev/src/main/kotlin/creator/custom/TemplateDescriptor.kt).


{% include h lvl=3 title="Template Label and Group" tag="label-and-group" %}

The template label can be provided in multiple ways, evaluated in this order:
1. the `label` property in the descriptor is used, if it exists
2. the name of the file, without its `.mcdev.template.json` ending, if not blank
3. the name of the directory containing the template

The group is an optional string value set in the descriptor's `group` property.

The label and group will be used as a translation key if localization files are present.


{% include h lvl=3 title="Template Properties" tag="properties" %}

Properties are objects defined in the `properties` array. They are accessible to all Velocity templates and some strings
in the same descriptor.

The main values of a property object are:
- a `name` that will be the variable name you will use in the Velocity templates
- a `type` [defined in the plugin.xml](https://github.com/minecraft-dev/MinecraftDev/blob/fed20eb2eeb5e4de4fed49190e051a215918148f/src/main/resources/META-INF/plugin.xml#L141-L155)
- an optional `label` string, if absent it will be the `name` of the property, useful when you are using localization files
- an optional `order` integer, defining where to place the property's UI in the creator, overriding the definition order
- an optional `default` value, its actual value depends completely on the property type
- an optional `visible` boolean, defaulting to `true`
- an optional `editable` boolean, defaulting to `true`
- an optional `remember` boolean, defaulting to `true`
- an optional `options` object or array of arbitrary values the property type will `deserialize`

Property types have an associated Java type that will be the type of the Velocity template variable, and will provide
their own UI in the creator. Most of the custom types are located in the [model package](https://github.com/minecraft-dev/MinecraftDev/tree/dev/src/main/kotlin/creator/custom/model).

They may perform specific validation upon their value and prevent proceeding with project creation if it fails.
Some types also support custom validation rules.

The common types you will use are:
- `boolean`
- `integer`
- `string`, supporting custom regex validation
- `class_fqn` of type [ClassFqn](https://github.com/minecraft-dev/MinecraftDev/blob/dev/src/main/kotlin/creator/custom/model/ClassFqn.kt), which validates that its value is a valid fully qualified class name
- `inline_string_list` of type [StringList](https://github.com/minecraft-dev/MinecraftDev/blob/dev/src/main/kotlin/creator/custom/model/StringList.kt), for a comma-separated list of strings
- `maven_artifact_version` of type [SemanticVersion](https://github.com/minecraft-dev/MinecraftDev/blob/dev/src/main/kotlin/util/SemanticVersion.kt), supports both `options` for hardcoded choices and versions defined in remotes pom.xml
- `build_system_properties` of type [BuildSystemCoordinates](https://github.com/minecraft-dev/MinecraftDev/blob/dev/src/main/kotlin/creator/custom/model/BuildSystemCoordinates.kt), providing standard Maven coordinates' `groupId`, `artifactId` and `version`
- `jdk` of type [CreatorJdk](https://github.com/minecraft-dev/MinecraftDev/blob/dev/src/main/kotlin/creator/custom/model/CreatorJdk.kt), providing a JDK dropdown that can be filtered down with a minimum version defined in another property

Properties are set up in the order they are declared, and are generally only able to access properties defined before them.


{% include h lvl=4 title="Options" tag="property-options" %}

`string` and `maven_artifact_version` properties support `options`, that is a hardcoded array or object of strings.

If it is an array the value is used as both the actual value and the label.

If it is an object, the key is the actual value and the value is the label.


{% include h lvl=4 title="Inheritance and Derivation" tag="property-inherit-derives" %}

Inheritance and derivation are ways to depend upon previously defined properties to automatically set a property's value.

Inheritance is simple, set `inheritFrom` to the name of the property you want to inherit from.
The property's value will be updated every time the parent property changes until this property is modified,
at which point the inheritance will stop and the value won't be updated automatically anymore.

Derivation allows for more complex use cases where you define one or more `parents` and a `method`, available methods
depend on the property type. A method might require `parameters`.

You can also specify with `whenModified` whether the derivation should stop when the property's value is modified
manually (like inheritance does.) `true` means inheritance stops.

Alternatively, for simple cases, you can use a switch-like construct with `select`, an array of simple objects.
Each object has a `value` and a `condition`. They are evaluated in order of appearance. Once a condition is true the
`value` is used as the result of the derivation.


{% include h lvl=4 title="Validation" tag="property-validation" %}

`string` properties support custom validation through a `validator`. The value is a regular expression tested against
the property's value.


{% include h lvl=3 title="Template Files" tag="files" %}

Template files are declared in the `files` array. Each object in this array must contain a `template` and `destination` 
string. Both are paths relative to the template root (the directory of the descriptor.) This means you can have multiple
templates in subdirectories accessing common files in their parent directory. They are also evaluated like a Velocity
template, and have access to all the properties of the template.

A file can also have a `condition` string deciding if it should be included in the created project. It is evaluated like
a Velocity condition, that is close to the regular Java condition syntax, and has access to all template properties.

Additionally, there are two boolean values `openInEditor` (defaults to `false`) and `reformat` (defaults to `true`) that
you can set for each file.


{% include h lvl=3 title="Template Finalizers" tag="finalizers" %}

Template finalizers are actions performed sequentially once the project is fully created and opened in the IDE.

The existing finalizers are:
- `import_gradle_project`, imports the Gradle project.
- `import_maven_project`, imports the Maven project.
- `run_gradle_tasks`, executes Gradle tasks provided in its `tasks` array.
- `git_add_all`, adds all the existing files of the project to the Git repo.

Finalizers can also have a `condition`, which works the same way as in `files`.
