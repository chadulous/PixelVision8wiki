# Display Target

The` DisplayTarget` class represents the bridge between Pixel Vision 8’s `DisplayChip` and MonoGame’s renderer. You can use the default one, or modify it to fit your needs. To learn more, we’ll need to walk through how the `DisplayChip` works.

Pixel Vision 8’s `DisplayChip` is in charge of collecting `DrawCalls`, sorting them, and copying them into the display buffer. This buffer is simply an array of colors, representing each pixel, based on the size of the screen. So at PV8’s default resolution of 256 x 240, the display buffer will be 61,440 pixels. While you don’t need to know how the underlying draw logic works, it’s important to note that Pixel Vision 8’s `DisplayChip` is responsible for updating the display buffer’s pixels based on the real colors in the `ColorChip`. This is where the DisplayTarget comes in.

The `DisplayTarget` is responsible for converting the` DisplayChip`’s buffer into a texture that MonoGame can render on the screen. To do that, it will simply push the `DisplayChip`’s pixel buffer into a texture. If you are familiar with how MonoGame works, you can make your own custom `DisplayTarget` class and use the output from the `DisplayChip` to render however you want. Since the` PixelVisionEngine` uses a software renderer to composite the draw calls into a display buffer, there will always be an inherent performance penalty the larger the display gets. You can always make your own custom `DisplayChip` to get around this limitation if you want to optimize the rendering process.

