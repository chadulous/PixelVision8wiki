# Making C# Games

Let’s take a look at how you can use Pixel Vision OS and Visual Studio to make a PV8 game with C#. When it comes to making Pixel Vision 8 games in C#,  you will need to adopt a hybrid workflow. This tutorial assumes you are using Visual Studio on a PC. You can also follow the same steps on Visual Studio for the Mac or Jetbrain’s Rider. To get started, you’ll want to download a zip copy of the Github repo instead of cloning.

![image alt text](images/MakingCSharpGames_image_0.png)

Once it’s downloaded, unzip the file, move it to your Documents folder, and rename it to `PixelVision8Games`. You can work on multiple Pixel Vision 8 C# games in the same Visual Studio solution.

![image alt text](images/MakingCSharpGames_image_1.png)

Next, you’ll want to open up the `MonoGameRunner.sln` file in Visual Studio. This solution contains two Runners, one for C# and the other for Lua. Remove the Lua project since we won’t be needing it.

![image alt text](images/MakingCSharpGames_image_2.png)

Now we’ll need to make a copy of the default C# project and import it back into our solution. On the file system, open up the `PixelVision8Games/Runners/` directory and make a copy of the `CSharpRunner` folder. Rename the folder to MyGame and the project file inside to `MyGame.Desktop.csproj`. 

![image alt text](images/MakingCSharpGames_image_3.png)

Before we import this in Visual Studio, we’ll need to make a few changes to the `MyGame.Desktop.csproj` file you just renamed.  Look for the `ProjectGuid` node. We need to give this a unique ID so we don’t get a conflict with other projects in the solution.

![image alt text](images/MakingCSharpGames_image_4.png)

You can use an [online generator](https://guidgenerator.com/) to or make it up yourself. You can also use this opportunity to make changes to any of the project’s other values such as its name and version number. After you’ve made your changes, add the project to the solution by right-clicking on the `Runner` folder and selecting `Add > Existing Project` from the menu.

![image alt text](images/MakingCSharpGames_image_5.png)

At this point, you should have a solution with the default C# project and the new one you created.

![image alt text](images/MakingCSharpGames_image_6.png)

Currently, the MyGame project is referencing a default project in the `Disks` folder which is not part of the solution. If you go back into the `MyGame.Desktop` project file, you’ll see where it is being referenced by looking for a reference to `\Disks\PixelVision8System\`. 

![image alt text](images/MakingCSharpGames_image_7.png)

If you are using Visual Studio, you will need to unload the project first, or you can just find the file in the `Runners/CSharpRunner/CSharpRunner.Desktop.csproj` and edit outside of Visual Studio.

In order to make a new game, we need to copy the `PixelVision8System` folder then renaming it to `MyGame`. To make things easier, you should put all of your games in the `Disks` folder to keep it in the same project folder. 

![image alt text](images/MakingCSharpGames_image_8.png)

Once you’ve created the new project folder, change the path in the `MyGame.Desktop` file. You can also delete the `code.lua` file in the game folder since we won’t be using it in C#.

![image alt text](images/MakingCSharpGames_image_9.png)

Now, when you return to Visual Studio and reload the solution, you’ll see all of the files from the `MyGame` folder, referenced in the project’s `Content` folder.

![image alt text](images/MakingCSharpGames_image_10.png)

Let’s go ahead and rename the `ExampleGameChip.cs` file as well. You’ll want to go in and change the class name to `MyGameChip` by clicking on the file and selecting rename in the drop-down menu. This will automatically update all references to that class.

![image alt text](images/MakingCSharpGames_image_11.png)

At this point, we should be able to run the game. But, before we do that, open up the `MyGameChip.cs` file and change the message to read "MY NEW GAME" instead of “EMPTY GAME”. When you compile your game, you’ll see the following.

![image alt text](images/MakingCSharpGames_image_12.png)

At this point, you should have everything you need to start building your new C# game in Visual Studio. If you don’t have a copy of Pixel Vision 8 installed yet, [get a copy from the site](https://www.pixelvision8.com/play) and [install Pixel Vision OS](https://www.pixelvision8.com/getting-started). We’ll be using the Pixel Vision OS tools to help us build our C# game.

![image alt text](images/MakingCSharpGames_image_13.png)

The last thing we’ll cover is how to use Pixel Vision OS’s tool to make changes to your game files. Once you have Pixel Vision 8 booted up, you’ll want to drag the `MyGame` folder you created in the `Disks` directory onto the Pixel Vision 8 window. That should mount your game as a disk on the desktop. Open the disk and you’ll see all of the files inside of the folder from your computer.

![image alt text](images/MakingCSharpGames_image_14.png)

Now you can use Pixel Vision OS’s built-in tools, including the Pro Tools if you have them installed, to edit your games files. With this workflow, you’ll do all of your coding in Visual Studio, and all of your configuration and game file editing in Pixel Vision 8. When you want to see any changes, you’ll need to rebuild the game in Visual Studio.

It’s important to note that if you are adding or deleting files outside of Visual Studio, you may need to unload and reload the project to see the changes in the `Contents` folder. Since we are using a pattern to match all files inside of the `Disks/MyGame/` directory and copy them over to the Contents directory during a build, Visual Studio sometimes loses track of the external changes.

When you are ready to make a new C# game, you can simply copy the default project and rename it just like we did before. This way, you can keep all of your C# PV8 games in one Visual Studio Solution.


