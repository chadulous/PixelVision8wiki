# Pixel Vision Engine

Before digging into the MonoGame runner example, let's walk through the general code architecture of Pixel Vision 8. We’ll start with the `PixelVisionEngine` class. This is the main wrapper for running a game. The engine accepts a reference an instance of the ServiceManager, the chips it needs to run, and an optional name.

The `ServiceManager`, which implements `IServiceLocator`, allows the engine to share services between itself and any chips. A chip is similar to a plugin. They all share a base architecture that integrates into Pixel Vision 8's lifecycle. Each chip expands the core engine by adding new features or enhancing existing ones. 

For example, you can use chips to create wrappers for displaying pixel data natively, capturing input and playing back sound in conjunction with the runner. The SDK contains all of the core chips you’ll need to run a game. You can find these in the /`SDK/Engine/Chips/` directory.

<table>
  <tr>
    <td>Function</td>
    <td>Class</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>Colors</td>
    <td>ColorChip</td>
    <td>Manages all of the system colors used in the game.</td>
  </tr>
  <tr>
    <td>Input</td>
    <td>ControllerChip</td>
    <td>Abstracts input from controllers, the keyboard and mouse in a way that all games can easily access</td>
  </tr>
  <tr>
    <td>Music</td>
    <td>MusicChip</td>
    <td>Responsible for playing back patterns and songs for a game’s music.</td>
  </tr>
  <tr>
    <td>Rendering</td>
    <td>DisplayChip</td>
    <td>Manages draw calls on each frame and rendering them down to a single pixel buffer representing the display.</td>
  </tr>
  <tr>
    <td>Sprites</td>
    <td>SpriteChip</td>
    <td>Stores all of the sprite data which is used to render graphics to the display.</td>
  </tr>
  <tr>
    <td>Sounds</td>
    <td>SoundChip</td>
    <td>Stores sound effect data that can be accessed at runtime or to use in music.</td>
  </tr>
  <tr>
    <td>Text</td>
    <td>FontChip</td>
    <td>Responsible for storing and retrieving font characters in order to display text.</td>
  </tr>
  <tr>
    <td>Tilemaps</td>
    <td>TilemapChip</td>
    <td>Stores the tilemap data and exposes APIs to manipulate that data.</td>
  </tr>
</table>


The Pixel Vision Engine has its own lifecycle which the Runner is responsible for triggering. There are four main lifecycle APIs for the engine.

<table>
  <tr>
    <td>Name</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>Init()</td>
    <td>Called when a game is started allowing it to be configured.</td>
  </tr>
  <tr>
    <td>Update(timeDelta)</td>
    <td>Called on every frame and receives a reference to the time between each frame.</td>
  </tr>
  <tr>
    <td>Draw()</td>
    <td>Called after Update() and is where render logic should go.</td>
  </tr>
  <tr>
    <td>Shutdown()</td>
    <td>Called when a game is shutting down allowing it an opportunity to save any data before being removed from memory.</td>
  </tr>
</table>


Each chip is called different times of the lifecycle based on which interface it implements. Chips that implement the IUpdate interface, like the ControllerChip, are updated on each frame. The `Update()` method accepts an argument called `timeDelta`. This value represents the difference in milliseconds between the last frame and the current one. This value is pass in by the runner and can be used to determine the timing of execution in your game to keep a consistent framerate.

Chips that implement the IDraw interface, like the DisplayChip, will be triggered by the engine's `Draw()` method when `Update()` has completed. In the case of the DisplayChip, calling Draw will render all of the draws calls into a single pixel buffer for the screens display. Displaying the pixel data will vary based on the framework you use to build Pixel Vision 8 games. Once you have the `Update()` and `Draw()` methods connected to the runner, and can render the `DisplayChip`’s pixel data, your engine is complete. 

