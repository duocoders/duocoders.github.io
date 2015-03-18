---
layout: post
title: "DuoCode 0.4 beta is now available!"
---
We've been working tirelessly to bring you the first public beta of [DuoCode](http://duoco.de) - our Roslyn-powered C# to JavaScript compiler.

<div class="bg-danger bs-callout bs-callout-warning" id="callout-helper-bg-accessibility">
<p>In this release, we've switched from a standalone executable installer to a Visual Studio Extension (VSIX) distribution, which is incompatible with the previous versions of DuoCode. Please remove any previous installation of DuoCode from <strong>Programs and Features</strong> in Control Panel <strong>before</strong> installing the DuoCode 0.4 beta.</p>
</div>

## Getting Started
Head over to the [DuoCode website](http://duoco.de) and download the DuoCode Visual Studio extension (you can also install it from the Visual Studio Gallery using **Extensions and Updates** under the **Tools** menu in Visual Studio). This will install the necessary project templates for you to get started.

After installing the DuoCode extension, go to File - New Project, under Visual C# you will see the DuoCode entry. You will find the project templates for several kinds of projects: a Class Library, WebGL and Node apps, as well as a Tic-Tac-Toe game and a [Ray Tracer](http://en.wikipedia.org/wiki/Ray_tracing_%28graphics%29) demo:

![](/images/duocode-0.4-beta-is-now-available/new-project.png)

Once a new project is created, simply press F5 to compile and start the project. DuoCode will take care of the rest!

![](/images/duocode-0.4-beta-is-now-available/tic-tac-duo.png)

## Technicalities

The DuoCode compiler is now distributed as a [NuGet package](https://www.nuget.org/packages/DuoCode/). During the compilation process, the DuoCode compiler (called `dcc.exe`) is executed by MSBuild. This means that DuoCode is ready to be included in your project, and is build-server friendly!

The result of the compilation is a `scripts` directory, containing the resulting `.js` file for the assembly, as well as `mscorlib.js`, which is the DuoCode implementation of the core libraries. In addition, DuoCode generates  source map files, allowing you to [debug your C# code right inside the browser](http://duoco.de/#debugging)!

## Questions? Issues? Let us know!

Please don't hesitate to contact us about any questions you might have, or issues you may encounter at our [support website](http://support.duoco.de), or by email to [support@duoco.de.](mailto:support@duoco.de)

Happy coding!  
&nbsp;-The DuoCode Team
