# Runners

The [Pixel Vision 8 SDK](https://gitlab.com/PixelVision8) was designed to be a self-contained, platform-agnostic C# library. With that in mind, it will need to be wrapped in a runner. A Pixel Vision 8 Runner is any code wrapper that bridges the gap between the core engine and the host OS. The Runner performs the following tasks:

* Facilitates rendering the `DisplayChip`’s pixel data on the screen.

* Provides a native application wrapper so PV8 can run as a self-contained executable.

* Calls the `GameChip`’s `Init()`method on startup as well as the `Update()` and `Draw()` methods during each frame.

* Feeds the engine input data such as the mouse, keyboard and any connected controllers.

* Provides a way to play sounds.

* Manages the loading and playing of games plus their associated files.

Runners are relatively easy to build. There are several examples of how to create Pixel Vision 8 Runners in the Github repo.

