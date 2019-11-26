# Log Tool

Pixel Vision OS includes a basic tool for viewing Pixel Vision 8’s log file. This file is maintained and updated while Pixel Vision 8 is running. 

<p style="text-align:center"><img src="images/LogTool_image_0.png" /></p>

You can preview this log at any time by opening up the Debug Tool from the Workspace Explorer’s drop-down menu.

<p style="text-align:center"><img src="images/LogTool_image_1.png" /></p>

Here you can read through the log.txt file and see the activity from the engine itself in the form of errors or Lua print() statements in your game. 

<p style="text-align:center"><img src="images/LogTool_image_2.png" /></p>

One thing to keep in mind, however, is that Pixel Vision 8 automatically destroys the `log.txt` file when you shut down Pixel Vision OS. You can access the raw `log.txt` file at any time from Pixel Vision 8’s `Tmp` directory on your computer.

<p style="text-align:center"><img src="images/LogTool_image_3.png" /></p>

The `log.txt` file is located in one of the following locations based on the OS you are running Pixel Vision 8 on.

<table>
  <tr>
    <td>Version</td>
    <td>Path</td>
  </tr>
  <tr>
    <td>Windows</td>
    <td>C:\Users\UserName\AppData\Local\PixelVision8\Tmp\Trash\</td>
  </tr>
  <tr>
    <td>MacOS</td>
    <td>/Users/UserName/.local/share/PixelVision8/Tmp/Trash/</td>
  </tr>
  <tr>
    <td>Linux</td>
    <td>/Users/UserName/.local/share/PixelVision8/Tmp/Trash/</td>
  </tr>
</table>


If you would like to view the log while running Pixel Vision 8, you can open it from the termnial window or use a text editor that automatically refreshes files after external changes are detected.

