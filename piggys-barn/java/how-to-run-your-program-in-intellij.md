# How to run your program in IntelliJ

Running your program inside of IntelliJ is a fairly trivial process. We can do so via the run configuration system. First step is to actually create a configuration, which can be done by clicking the `ADD CONFIGURATION` button in the top right corner of your IDE.

![](../../.gitbook/assets/image.png)

Upon clicking this, a modal will open where you can create a new configuration from a template. Specifically, we want to create a "JAR Application" configuration, so that's the template we'll use. Click the + in the top left of the modal, then scroll down to JAR Application and click it.

![](../../.gitbook/assets/image%20%281%29.png)

Call it whatever you want, for the purpose of this tutorial, I'll simply be naming mine "run". Set the path to jar to where ever your jar is. I personally run the jar inside it's build folder, and for gradle, that's build/libs. So for this project, I'd be setting the path to jar to `/media/piggy/HDD/Documents/Github/hotswapdemo/build/libs/hotswapdemo-1.0.0-all.jar`.

You'll usually want the working directory to be the same as the directory the jar is in, however this isn't a strict requirement. Things can just get a bit funky if you don't do this.

Finally, you'll want to fill out any other options required for your application \(such as vm options & program arguments\), and then set the JRE. Hit apply & ok in the bottom right when you're finished.

You can run the program via shift + f10, or by clicking the play button in the top right.

