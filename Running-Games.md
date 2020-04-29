If you have Pixel Vision OS installed, you can run any PV8 game project that has a Run icon in the root of its folder.

![image alt text](images/RunningGamesPixelVisionOS_image_0.png)

You can also press `Ctrl + R` in any game folder to run it. If a game folder contains a data.json and info.json file, the Workspace Explorer will automatically assume it is a game and display the Run icon for you. You can also run any PV8 game by clicking on it in the Workspace Explorer.

Disks can also contain multiple games that can be linked together to make a larger experience. For example, Pixel Vision OS itself is simply a collection of games, each one being a specific tool, and the Workspace Explorer is the default game that runs from the Pixel Vision OS.

![image alt text](images/RunningGamesPixelVisionOS_image_1.png)

All disks need an info.json file. This file normally contains metadata about a game but for disks, it can be configured to tell Pixel Vision 8 which game to load first. Let’s take a look at the root of the Pixel Vision OS disk. 

![image alt text](images/RunningGamesPixelVisionOS_image_2.png)

As you can see, in the root of the Pixel Vision OS disk is an info.json file. You can view the contents of this file with the built-in Text Editor.

![image alt text](images/RunningGamesPixelVisionOS_image_3.png)

Inside the `info.json` file are three properties: `name`, `description`, and `AutoRun`. The AutoRun property is set to:

`"AutoRun": "/System/Tools/WorkspaceTool/"`

When you drag this disk onto the Pixel Vision 8 Runner window, it will read the path to the FilePickerTool and load that. If you try to run a disk while Pixel Vision OS is loaded, it will simply mount on the desktop and you’ll need to manually find the game you want to run and launch it by hand. The autorun feature is automatically disabled when a game is running.

