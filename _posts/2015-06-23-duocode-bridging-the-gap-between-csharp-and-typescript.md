---
layout: post
title: "Here's your game changer: DuoCode 1.0 bridges the gap between C# and TypeScript!"
---
This just in: DuoCode 1.0 has been [released](http://duoco.de/download)! And now, with 100% more **TypeScript support**!

### **C# <3 TypeScript**!

Ever wanted to use .NET types or methods, like `StringBuilder` or `String.Format` in your TypeScript code? With DuoCode, now you can!

We are happy to unveil our newest addition to DuoCode - TypeScript definition (`.d.ts`) generation for C# types, allowing you to create hybrid C#/TypeScript applications in a single project!

#### Let's get started!

Create a new TypeScript Application project from a DuoCode template:

<img src="/images/duocode-typescript/new-project.png" class="screenshot img-responsive">
<br/>

This will create a DuoCode-enabled TypeScript application with a twist: alongside the application code (`app.ts` file) you will find a pure C# class, `RomanUtils.cs`, containing utility methods to convert a number into its <a href="https://en.wikipedia.org/wiki/Roman_numerals">Roman representation</a>:

<img src="/images/duocode-typescript/project.png" class="screenshot img-responsive">
<br/>

When you run the sample, you'll see it in action in a browser window:

<img src="/images/duocode-typescript/browser.gif" class="screenshot img-responsive">
<br/>

#### How does it work?

When you compile the project, our DuoCode compiler does what it does best - translates the C# code into JavaScript, but now it also emits a matching `.d.ts` definition for the generated code:

```
/// <reference path="./mscorlib.d.ts" />

declare module TypeScriptHtmlApp {
    // TypeScriptHtmlApp.RomanUtils
    export interface RomanUtilsTypeFunc extends TypeFunction {
        ConvertNumberToRoman(number: int): string;
        ConvertRomanToNumber(text: string): int;
    }
    var RomanUtils: RomanUtilsTypeFunc;
}
```

This is the definition generated from the C# code in `RomanUtils.cs`, and placed next to it in the file `TypeScriptHtmlApp.d.ts`. Adding the reference to this definition to the main `app.ts` file allows using it straight away, enjoying full code-completion, syntax highlighting and live error checking support, provided by Visual Studio!

This means you can now write C# in your TypeScript project, recompile it, and immediately use it from TypeScript! In addition, you will enjoy all the goodness already provided by DuoCode, such as debugging the original C# code (via generated source-maps), Base Class Library (BCL) support via `mscorlib`, and more.

You can control the generation output (ECMAScript 3/5/6, similar to TypeScript) in the project's Properties dialog, under the **DuoCode** tab.

#### Known issues

There are a few issues that currently exist. We plan to address them in the next version release:

* After creating a project, please rebuild the project once, and reopen the file `app.ts` to eliminate any editor warnings that might appear.

* Generated TypeScript definitions currently support `public` C# types only.

* Some ReSharper warnings may appear, please ignore those for now (the code compiles fine).

* Requires TypeScript 1.4 - Visual Studio 2013 users can install an updated version from the [Extension Gallery](https://visualstudiogallery.msdn.microsoft.com/2d42d8dc-e085-45eb-a30b-3f7d50d55304).

### DuoCode Release and Trial information

With this version we're getting ready for an official release *very soon*. We've bumped the version number to 1.0, and when you install the new <a href="https://visualstudiogallery.msdn.microsoft.com/473cca1d-60f9-4d7b-8c5c-aa7ff2939ab3">Visual Studio Extension</a> or an updated <a href="https://www.nuget.org/packages/DuoCode/">NuGet package</a>, DuoCode will begin a 30-day trial. After the trial period is over, you will have to purchase a license to continue using DuoCode.

License and pricing information will be posted within a few days!

Happy coding!  
 &nbsp;-The DuoCode Team
