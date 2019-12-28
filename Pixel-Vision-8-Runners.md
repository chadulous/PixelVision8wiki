There are two Pixel Vision 8 Runners you can explore by opening the `PixelVision8Runner.sln`. 

<p style="text-align:center"><img src="images/PixelVision8Runners_image_0.png" /></p>

The first project, `GameRunner.Desktop`, is a stripped-down version of Pixel Vision 8 designed specifically for wrapping a single PV8 game. It’s similar to the MonoGame Lua Runner but includes the Workspace VFS as well as the ability to configure the system via a `bios.json` file. 

The second Runner, in the `PixelVision8.Desktop` project is the full build of Pixel Vision 8. This includes logic to boot, load games from disks, and a virtual file system (VFS) to manage the workspace. This is project represents the full source code for Pixel Vision 8 that you can download from the [main website](https://www.pixelvision8.com) with the exception of a built-in OS installer. If you want to use [Pixel Vision OS](https://github.com/PixelVision8/PixelVisionOS), you’ll need to manually install it.

Both Runners use a stripped-down version of MonoGame called MonoVision which is located in the Shared folder. You’ll need to build this project first since both runners are dependant on it.

<p style="text-align:center"><img src="images/PixelVision8Runners_image_1.png" /></p>

While both of these projects work with MonoGame, this custom version strips out all of the logic that is not critical to running Pixel Vision 8; all the way down to the bare SDL2 wrapper. It’s important to note that no APIs have been changed in MonoVision since the goal is to keep Pixel Vision 8 compatible with any future versions of MonoGame.

You’ll also want to make sure that the NuGet references are downloaded since these are not included in the repo. Pixel Vision 8 requires [SharpZipLib](https://www.nuget.org/packages/SharpZipLib/) and [MoonSharp](https://www.nuget.org/packages/MoonSharp) in order to compile. 

<p style="text-align:center"><img src="images/PixelVision8Runners_image_2.png" /></p>

Once you have all the project reference set up correctly, you should be able to start with the `GameRunner.Desktop` project. This gives you the bare bone functionally needed to load a game. If you look in the `Content` folder, you’ll see references to the three core tools in order to boot, load games, and display errors. 

<p style="text-align:center"><img src="images/PixelVision8Runners_image_3.png" /></p>

There is also an `Effects` folder that allows you to enable Pixel Vision 8’s CRT shader which we’ll talk about later. Finally, the` DefaultGame` folder contains an empty game project. This is where you’ll want to place your Lua PV8 game files in order to run them. If you compile the `GameRunner.Desktop` project, you’ll see the Runner boot and load the contents of the `DefaultGame` folder.

<p style="text-align:center"><img src="images/PixelVision8Runners_image_4.png" /></p>

Finally, the `bios.json` file allows you to configure the Runner as it boots up. You’ll want to change the project name and can even update the paths to a custom boot, error or load tool if you want to customize the look and feel of your game’s Runner.

The `PixelVision8Runner.Desktop` project works in a similar way. The biggest change here is the creation of a `Workspace` folder when the Runner boots up. By default this will be created on your computer in one of these paths based on the OS you are running it on:

<table>
  <tr>
    <td>Version</td>
    <td>Path</td>
  </tr>
  <tr>
    <td>Windows</td>
    <td>C:\Users\UserName\Documents\PixelVision8\Workspace\</td>
  </tr>
  <tr>
    <td>MacOS</td>
    <td>/Users/UserName/PixelVision8/PixelVision8/Workspace/</td>
  </tr>
  <tr>
    <td>Linux</td>
    <td>/Users/UserName/PixelVision8/PixelVision8/Workspace/</td>
  </tr>
</table>


The Workspace directory allows you to install Pixel Vision OS and work on PV8 projects. The `PixelVision8Runner.Desktop` project does not contain a copy of Pixel Vision OS. So after it boots, you’ll be presented with the following screen.

<p style="text-align:center"><img src="images/PixelVision8Runners_image_5.png" /></p>

At this point, you can drop any `.pv8` disk or folder onto the Runner’s window and it will attempt to load it up. The `PixelVision8Runner.Desktop` project has a different structure inside of the `Content` folder than the Game Runner. Here you’ll find a `PixelVisionOS` folder that contains the same boot, load, and error tools the other Runner uses.

<p style="text-align:center"><img src="images/PixelVision8Runners_image_6.png" /></p>

The big difference here is that the PixelVision8 Runner creates a mount point for the OS folder which you can access internally at `/PixelVisionOS/`. For example, you could place the contents of the Pixel Vision OS in this directory and change the `bio.json` file to load the Workspace Tool by default, and the Runner will boot right into the Workspace Explorer desktop. This is how the self-contained builds of [Pixel Vision 8 Draw](https://www.pixelvision8.com/draw) and [Tune](https://www.pixelvision8.com/tune) work. They have all the tools needed to run independently of installing the OS.

If your game needs access to a VFS, requires the `GameEditor`, or the ability to export and save files, you can customize the `PixelVision8Runner.Desktop` project to your own needs.

