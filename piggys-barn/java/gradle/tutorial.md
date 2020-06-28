# Tutorial

## Skeleton Setup

The easiest way to setup a new gradle project, is via the `gradle init` command. This will allow you to easily create 4 types of projects, `basic`, `application`, `library`, and `gradle plugin`.

| Type | Description |
| :--- | :--- |
| Basic | Initializes your directory with the gradle wrapper, a blank build.gradle, and a populated settings.gradle. |
| Application | Basic + populates your build.gradle with your testing framework of choice, main class configuration for the gradle application plugin, and the corresponding plugin for the language you're developing in. |
| Library | Basic + populates your build.gradle with your testing framework of choice, and the gradle `java-library` plugin. |
| Gradle Plugin | Basic + populates your build.gradle with the options needed to develop a gradle plugin. |

`gradle init` uses a questionnaire-esque system for retrieving information from you, about the project it's initializing. While this changes slightly for each project type, all of the questionnaires are fairly similar. For new developers however, the nomenclature may be unfamiliar, so here's what everything means:

| Term | Definition |
| :--- | :--- |
| Implementation Language | Essentially what language you're writing the project in. Whether that's Java, Kotlin, Groovy, Swift, or even C++. |
| Build Script DSL | This is just what language your gradle configuration files will use. Gradle currently supports 2 languages; Groovy, and Kotlin. This tutorial assumes Groovy, but if you're more comfortable with Kotlin, go for it. |
| Testing Framework | A testing framework allows you to automate code testing, to ensure your project's runtime semantic's haven't changed with any updates to the codebase. |
| Project Name | Somewhat similar to maven's artifact ID. Be descriptive, `MinecraftPlugin` isn't a very good name. |
| Source Package | This is the package that gradle will generate for you in your sources root. If you're not sure what this should be, familiarise yourself with your language's naming conventions. For Java, they're [here](https://www.oracle.com/java/technologies/javase/codeconventions-namingconventions.html). |

### Alternatives

While gradle's inbuilt initialization is pretty nifty, it's not necessarily the best option at all times. Your IDE will most likely also have some gradle options, for specific project types, and these may be preferable to use over the `gradle init` ones. For example, IntelliJ's basic gradle project is much more useful than the one from `gradle init`, as it populates the `build.gradle` with some useful properties.

## Syntax

One of the most frequent arguments I hear from people who don't like Gradle, is that it's confusing. Nearly 100% of the time, this is due to a fundamental misunderstanding of Groovy's syntax. Groovy is not complicated, in fact, it's incredibly simple. Arguably far more simpler than Maven's XML configurations. Let's take a look:

{% code title="build.gradle" %}
```groovy
plugins {
	id 'java'
}

group 'me.piggypiglet'
version '1.0.0'
sourceCompatibility = JavaVersion.VERSION_1_8

repositories {
	mavenCentral()
	maven {
		url = 'https://hub.spigotmc.org/nexus/content/groups/public/'
	}
}

dependencies {
	compileOnly 'org.spigotmc:spigot-api:1.15.2-R0.1-SNAPSHOT'
}
```
{% endcode %}

So, what's so daunting about this for people trying to switch to Gradle? Well, the main confusion comes in on where to use specific syntax. For example, you can see that `group` is assigned to `me.piggypiglet`, simply via a space. Whereas, the `sourceCompatibility` is assigned with an `=`. "Where do I use what?".

I'm not going to lie, this will probably take some practice to get used to. Essentially the problem here is that the types we're assigning values to, aren't all the same type, it's a mix of methods and variables. For example, `group`, and `version`, are methods, which accept a parameter; a string. `group 'me.piggypiglet'` is the same as `group('me.piggypiglet')`. `sourceCompatibility` on the other hand, is a variable, and therefore is assigned with `=`.

There's also another piece of syntax that people find confusing, which you often find on modular projects. That's the colon, which is commonly found when applying plugins:

{% code title="build.gradle" %}
```groovy
plugins {
  id 'java'
}

subprojects {
  apply plugin: 'java'
}
```
{% endcode %}

`apply plugin: 'java'`, is actually a method, like `group`, and `version`. `apply` is the function here, and `plugin: 'java'` is a key/pair value you're passing as the parameter. Like an entry from a java map \(You can also think of it as a named parameter\).

## Usage

Most Gradle configs look the same. Let's start off with dissecting this one:

{% code title="build.gradle" %}
```groovy
plugins {
	id 'java'
}

group 'me.piggypiglet'
version '1.0.0'

sourceCompatibility = JavaVersion.VERSION_1_8
compileJava.options.encoding = java.nio.charset.StandardCharsets.UTF_8

repositories {
	mavenCentral()
	maven {
		url = 'https://hub.spigotmc.org/nexus/content/groups/public/'
	}
}

dependencies {
	compileOnly 'org.bukkit:bukkit:1.15.2-R0.1-SNAPSHOT'
}
```
{% endcode %}

Doesn't look like much, but there's actually quite a lot going on in this config. First off, we declare what kind of project this is: it's a java project, so we use the gradle java plugin. We declare the plugin's gradle will use, via the plugins DSL block. The DSL accepts ids of the plugins you're using, and optionally a version, which is usually used for external plugins. e.g:

```groovy
plugins {
  id 'java'
  id 'com.github.johnrengelman.shadow' version '5.2.0'
}
```

Next off is the group and version assignments. The group should be your package. In relation to maven terminology, the group is the same as the group ID. While this may not make sense yet, the group is the first part people will use in a dependency declaration; it should be your unique identifier \(or your company's\). In java, it's conventional to use your domain, but reversed. For example, my domain is `piggypiglet.me`, so my package/group is `me.piggypiglet`. At HelpChat, we use `at.helpch`, as our domain is `helpch.at`. The version, is simply a string. Unlike the group, this has no official convention, although unofficial ones do exist, and I recommend you pick one and stick to it. Version naming may seem like a small thing, but it can reveal a great deal of information regarding the work done between version x, and y, depending on your naming technique.

The sourceCompatibility tells gradle what version of Java to compile your project with. See [here](https://docs.gradle.org/current/javadoc/org/gradle/api/JavaVersion.html) for the versions available in the gradle api.

`compileJava.options.encoding = java.nio.charset.StandardCharsets.UTF_8` has a few parts to it. First off, we're traversing through the compileJava task \(which is a JavaCompile class\), which contains another object called `options` \(of type CompileOptions\), which finally contains an encoding variable, of type String. That's where the second part comes in, we're passing a charset enum from Java here, not a String. This isn't necessary, `compileJava.options.encoding = 'UTF-8'` would function identically; however, hard-coded constants are usually preferable to magic values, which is why I've used the enum.

Here's the first part that really matters, your `repositories` block. Gradle shares a bit of terminology with maven here. It's important to note, as this is something a lot of people get confused with, Gradle uses maven repositories too \(also other repository formats, that's not important yet though\)! Maven repositories should be thought of as a specification; a format, like JSON is a language, but not the actual implementation. Maven repositories may have maven in the name, but that's simply because their format was developed for maven. Maven repositories are in fact, used in other build tools, such as Gradle.

Enough of that, how does this repositories block actually work? First off, you'll notice that we've got 2 repositories in here, although they're declared with a different format. Gradle has shortcut functions for popular maven repositories, such as maven central. Others include maven local, JCenter, and Google. The other format is just a plan maven repository declaration, which includes the url to the repository.

As I mentioned briefly before, gradle doesn't only support maven repositories. It also supports ivy, flatfile, authenticated, and alternative protocol-using \(e.g. https, sftp\) repository types. For the average developer, most of these won't matter, except perhaps the flatfile type, so let's go into that, because it's actually really useful sometimes.

Flatfile is where we start to get into strictly gradle territory. If you're from maven, this will be something completely foreign to you, as maven simply doesn't have this functionality. Gradle actually allows you to make a repository format, from a directory of libraries. For example, imagine this structure:

```yaml
.
|-- build.gradle
|-- gradle
|   `-- wrapper
|-- gradlew
|-- gradlew.bat
|-- libs
|   `-- nanohttpd-2.3.1.jar
|-- settings.gradle
`-- src
    `-- main
```

As you can see, we have a libs folder, containing `nanohttpd-2.3.1.jar`, one of our project's dependencies that unfortunately doesn't have an online maven repository. No worries, gradle's flatfile format can handle this with ease:

{% code title="build.gradle" %}
```groovy
repositories {
  flatDir {
    dirs 'libs'
  }
}
```
{% endcode %}

We can then add the nanohttpd jar as you would with any other dependency.

{% hint style="info" %}
Side note, nanohttpd is actually on maven central, this is merely an example.
{% endhint %}

Speaking of dependencies, let's get into those. The main 4 keywords you'll encounter when declaring dependencies are `compile`\(deprecated\), `compileOnly`, `api`, and `implementation`. With maven terminology, `compile`/`api`/`implementation` is the same as setting your dependency scope to `COMPILE`, and `compileOnly` would be the `PROVIDED` scope. Chances are, you'll be using `compileOnly` and `implementation` the most. If you're unfamiliar with how these scopes work, here's a brief rundown of each:

| Scope | Description |
| :--- | :--- |
| compile | Don't use this, it's deprecated. Same functionality as `api` however. |
| implementation | Essentially a dumbed down version of `api`. This is what you should use 99% of the time, when you're shading dependencies. It should be used for internal components, that don't need to be exposed in the external api. Basically, if you're not writing an api/library, use `implementation`. |
| api | This keyword exposes your dependencies in the external api. For example, if you're writing a library, which behind the scenes uses gson, you may wish to declare the gson dependency using `api`, so the user of your library, can also use your library's gson dependency if they wish to. |
| compileOnly | This keyword simply indicates that the dependency will be provided at runtime. For example, a spigot plugin. Spigot, the dependency, is provided at runtime by spigot itself, as your plugin is running as an extension of spigot. |

{% hint style="info" %}
Appending `test` before keyword, and formatting the new keyword to lowerCamelCase, will allow you to declare dependencies for your testing source.
{% endhint %}

With the keywords in mind, we need to actually know how to use them. All of these keywords are functions, and accept either a string, or the individually named parameters. The repository type also plays a role here. For example, maven repositories will need a group id \(group\), and artifact id \(name\), and a version. The format for which, is either of the following:

```groovy
// group:name:version
implementation 'com.google.inject:guice:+'
// or
implementation group: 'com.google.inject', name: 'guice', version: '+'
```

{% hint style="info" %}
`+` can be used in the version, to retrieve the latest version of that dependency.
{% endhint %}

Seeing as flatfile was discussed earlier, here's the format for that:

```groovy
implementation name: 'nanohttpd-2.3.1'
```

Notice that the group and version is missing? That's because as mentioned earlier, different repository types need different data. The name here, corresponds to the jar name in the dir you specified for your flatDir repository, without the extension though. Keep in mind, you won't be able to use the shortcut \(`group:name:version`\) format for this dependency type, as that's a feature of the maven repository type.

## Building

So, with the configuration setup, and explained, how do you actually go about building with gradle? Well, simply run `gradle build`, and you'll find your binary in `build/libs`.

