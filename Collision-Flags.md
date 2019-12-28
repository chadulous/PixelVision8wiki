# Collision Flags

The Tilemap Tool can also help you add collision flags to your tilemap. These special flags start at 0 and go up to 15. Tiles without collision flags are automatically set to `-1`. You can check a tile’s flag during runtime by calling the `Flag()` API. It requires a column and row ID. You can also pass in a 3rd parameter which allows you to change the value when a game is running. This is useful for a collectible such as a coin. You may set the flag id in the tilemap editor and when the player collects it, clear the value so it can’t be collected a second time.

Collision flags should only be used for fixed objects that are part of the tilemap and do not move. You wouldn’t want to use them for enemies for example. While you can change collision flags at runtime, they do not provide the most accurate way of checking collision between two objects such as a player and an enemy. They are however useful for anything solid or that can affect the physics of entities in your game.

Each tile can have its own unique collision flag so keep that in mind. There is no performance penalty for changing a collision flag at runtime since it doesn’t force the tilemap cache to update. In situations where you need to use tiles for objects in your game, such as coins, be sure to call the Tile() API and pass in a new sprite ID when changing the collision flag so it updates on the tilemap cache correctly and disappears.

