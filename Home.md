Pixel Vision 8's core philosophy is to teach retro game development with streamlined workflows. PV8 is also a platform that standardizes 8-bit fantasy console limitations built on top of the open-source C# game engine based on MonoGame. This engine simply provides a standard set of APIs to create authentic-looking 8-bit games with modern programming languages and workflows. It also allows you to define specific limitations that alter the following properties:

* Memory and game size

* Color palettes 

* System colors

* Colors per sprite

* Number of sprites on screen

* Scrolling tilemap

* and more

There are different ways to build and run Pixel Vision 8 games depending on your choice of language and skill level. The most common way is to use the commercial build of the fantasy console itself which you can download from [pixelvision8.com](https://pixelvision8.com) and write your games in Lua. For more advanced developers familiar with C#, Pixel Vision 8 can be compiled in Visual Studio by visiting the [GitHub repo](https://github.com/PixelVision8) as well. There you will find the two components which make up Pixel Vision 8: a Runner and Pixel Vision OS.

The platform was designed to be incredibly modular. This allows you to customize it to your own needs. While there are tools and a dedicated OS to help make games with, there is nothing stopping you from using your own external tools and workflows.

This documentation covers how to build Pixel Vision 8 from its source code, manually install Pixel Vision OS, workflows for using Pixel Vision 8 and Visual Studio, as well as how to export stand-alone Lua PV8 games in dedicated Runners. You’ll also find all the information you need to better understand how Pixel Vision 8 works under the hood and the APIs used to make your own games in C#.

