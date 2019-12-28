While we covered the other core chips needed to configure a `PixelVisionEngine` instance, there is one chip that represents the game itself. When creating a C# PV8 game, you’ll want to extend the `GameChip` and pass that into the engine’s constructor, along with all of the other chips your game needs. The `GameChip` provides access to all of the underlying chips through a common API that is shared by the C# and Lua versions of Pixel Vision8.

The `GameChip` implements both the `IUpdate` and `IDraw` interfaces. This allows you to organize your game’s business and render logic separately. To create your own custom C# game, you can do the following:

    public class MyGameChip : GameChip
    {
        public override void Init()
        {
            // Add custom Init logic.
        }

        public override void Update(int timeDelta)
        {
            // Add custom Update logic.
        }

        public override void Draw()
        {
            // Add custom Draw logic.
        }
    }

You’ll also need a way to configure an instance of the `PixelVisionEngine` by creating a wrapper for the `GameRunner`. Be sure to check out the example `CSharpRunner.Desktop` project to see how to pass in your own game chip or build on top of the existing example game provided in the project.
