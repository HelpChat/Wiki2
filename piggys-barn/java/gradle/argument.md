---
description: Gradle vs Maven
---

# Argument

## Introduction

Sadly, Gradle isn't very commonly used in the spigot community, mainly due to misconceptions spread around the community by notable members, as far as I can tell. The main arguments are the following:

* Gradle isn't faster than Maven
* Gradle is confusing

[For example, here's spigot's maintainer, spreading factually incorrect information, and his own opinion:](https://www.spigotmc.org/threads/gradle-vs-maven.370756/#post-3384265)

> Imperative v Declarative.
>
> A build system should be the latter, therefore Maven wins.
>
> \(Also Gradle is almost invariably slower at actually building\).

## Gradle vs Maven

Here's my stance:

Pros:

| Gradle | Maven |
| :--- | :--- |
| Faster than maven | Widely used; i.e. has good community support, and you'll be able to find resources online with ease. |
| More concise configuration language, leading to simpler & smaller configuration files. |  |
| Portable |  |
| Groovy is a fully functional language, meaning you can easily extend your build process with custom logic. |  |

Cons:

| Gradle | Maven |
| :--- | :--- |
| Groovy isn't the ideal language \(it's not very nice to work with\), for configuration or general development. The Kotlin DSL battles this issue, but it's not perfect either. | Extremely verbose and counter-intuitive configuration format |
|  | Slow |
|  | Not portable \(technically portable with a third-party plugin, let's stick with vanilla features though\) |

Now, considering I criticise personal opinion in the next section, I should explain why saying "gradle is simpler" isn't completely opinion based \(although I'd be lying if I said it wasn't at least partially\), but has factual roots. Let's start off with a dependency declaration:

{% code title="build.gradle" %}
```groovy
dependencies {
    compileOnly 'org.spigotmc:spigot-api:1.15.2-R0.1-SNAPSHOT'
}
```
{% endcode %}

{% code title="pom.xml" %}
```markup
<dependencies>
  <dependency>
    <groupId>org.spigotmc</groupId>
    <groupId>spigot-api</groupId>
    <groupId>1.15.2-R0.1-SNAPSHOT</groupId>
    <scope>PROVIDED</scope>
  </dependency>
</dependencies>
```
{% endcode %}

There's an obvious winner here regarding concise syntax. Perhaps you're still not convinced, so let's look at two identical configs:

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
	maven {
		url = 'https://hub.spigotmc.org/nexus/content/groups/public/'
	}
}

dependencies {
	compileOnly 'org.spigotmc:spigot-api:1.15.2-R0.1-SNAPSHOT'
}
```
{% endcode %}

```markup
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
				 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
				 xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>

	<groupId>me.piggypiglet</groupId>
	<artifactId>test</artifactId>
	<version>1.0.0</version>

	<properties>
		<maven.compiler.source>1.8</maven.compiler.source>
		<project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
	</properties>

	<repositories>
		<repository>
			<id>spigot-repo</id>
			<url>https://hub.spigotmc.org/nexus/content/groups/public/</url>
		</repository>
	</repositories>

	<dependencies>
		<dependency>
			<groupId>org.spigotmc</groupId>
			<artifactId>spigot-api</artifactId>
			<version>1.15.2-R0.1-SNAPSHOT</version>
			<scope>PROVIDED</scope>
		</dependency>
	</dependencies>
</project>
```

When comparing line counts, the maven config has 12 more lines, or is ~63% bigger. This difference becomes even more drastic on large projects, where maven plugin configurations are present. Not to mention, which one is easier to remember? I could most certainly write the former from memory, but I highly doubt people actually remember what the XML namespaces are.

## Responses

Let's disassemble the arguments I could find, and explain why they're wrong. Starting off with the quote linked above:

#### MD\_5

> Imperative v Declarative.
>
> A build system should be the latter, therefore Maven wins.
>
> \(Also Gradle is almost invariably slower at actually building\).

First off, there's no reason a build system should be declarative. This 100% personal opinion, and therefore should never have been presented as an argument by the original author. He then proceeds to say that Gradle isn't faster, but is infact actually slower than Maven. Feel free to look at the official benchmarks yourself: [https://gradle.org/gradle-vs-maven-performance/](https://gradle.org/gradle-vs-maven-performance/)

Hell, even with the cache disabled, gradle still beats maven by a longshot.

Another argument I found from MD, is this:

> Maven is clearly a better build system for most projects, especially because of its declarative nature. Groovy only wins out if for some reason you need to actually execute custom code as part of the build process \(read: very rarely\)

Once again, this post is riddled with personal opinion.

#### MiniDigger

Unlike MD, MiniDigger actually presented a real reason why you may not want to use gradle, although there are workarounds. Let's see what he said:

> Does Gradle have the concept of parent poms?  
> like, a super pom outside of the project used by multiple projects  
> To manage plugin configs and dependency versions globally for example

Well, strictly speaking, no, gradle doesn't have a direct replacement for maven's super parent poms, however there are workarounds. Before getting into that though, I'd just like to mention my personal opinion. I think the concept of having a "super parent pom", is absolutely terrible, and would just lead to issues. The company he works at uses them on all of their projects. Imagine having one pom, ontop of hundreds of potentially unrelated projects. That's where my issue with it is, needlessly grouping all these projects together simply because they're developed by the same entity. Sure, you may use the exact same dependencies in all of your unrelated projects, but what if one day you don't need one of those dependencies. You'd then separate this one project from the parent pom, creating an inconsistency. Yuck!

Anyway, enough complaining, let's get onto the gradle alternatives. Supposedly you're meant to use gradle plugins to achieve this sort of functionality, which is understandable, but possibly a bit of a hassle. I was recently made aware of another method, which is actually really intuitive, and works perfectly for this sort of situation. Simply providing the parent build configuration, via the apply keyword. For example,

{% code title="build.gradle" %}
```groovy
plugins {
  id 'java'
}

apply from: 'https://cdn.piggypiglet.me/gradle/paper.gradle'
```
{% endcode %}

As you can see, I've got a gradle script hosted on my cdn, with the paper dependency configuration. This can then be applied using the apply keyword in gradle. AFAIK anything can be configured in these applied configs, so you should be able to emulate that super parent pom behaviour from maven without issue.

{% hint style="info" %}
[More examples](https://github.com/VoxMcNetwork/gradle)
{% endhint %}

