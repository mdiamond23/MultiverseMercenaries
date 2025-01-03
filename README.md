# Multiverse Mercenaries  
Repository for Multiverse Mercenaries, a game made in Unity using C# by Matthew Diamond. 

Here is a link to where you can play the game!  
[**Multiverse Mercenaries On Steam**](https://store.steampowered.com/app/2161190/Multiverse_Mercenaries/)

I've attached code examples that were integral to the project. This code was written in 2021 and 2022.

**`BullletScript.cs`**: Handles behavior for both enemy and player bullets. Applies modifiers from items like extra damage or changes in behavior like reflection.

**`CornerLevelGeneration.cs`**: Handles procedural level generation by creating a grid-based layout and generating a valid path between two developer-defined corner points using Dijkstra's algorithm. Each grid cell acts as a node in a graph, with costs determining pathfinding efficiency. The script dynamically places platforms, start and end points at strategic locations. Customizable parameters include grid dimensions, prefab size, and platform types. Platforms are instantiated based on their role (path, start, end, or generic platforms), and walls are conditionally enabled or disabled around each cell based on neighboring tiles. Player spawn placement is dynamically set at the start corner, allowing for flexible and repeatable level designs that enhance replayability in procedurally generated environments.

**`Enemy.cs`**: Serves as the **base class** for enemy behaviors, defining core properties like **health, speed, damage, and poison effects**. Includes movement functionality, damage handling, poison application, and death effects. Supports visual effects for damage states and uses animation parameters for grounded status and velocity-based movement states. Can be extended to create specific enemy behaviors.

**`EnemyGeneration.cs`**: Once a level is complete, this script fills out the level with enemies, which the player fights. 

**`GrappleGun.cs`**: Manages the behavior of the grappling hook gun. Handles aiming, firing, and retracting the grappling hook, along with physics interactions via SpringJoint2D. Supports cooldowns, ammo management, and smooth gun rotation toward the target point. Includes features for launching the player towards the grapple point and adjusting distance constraints dynamically.

**`GrappleRope.cs`**: Handles the visual representation and animation of the grappling hook's rope. Uses a LineRenderer to create dynamic rope effects, including wave animations during the rope's travel phase and a straightened appearance once the grapple is secured. Supports customizable parameters for animation curves, wave size, and rope progression speed, allowing smooth transitions and flexible visual behavior during grappling actions.

**`Item.cs`**: Defines the behavior of **collectible items**, including their **cost, rarity, and duration**. Supports applying item effects to the player, removing them when necessary, and displaying item descriptions when the player is nearby. Includes functionality to disable item visuals after collection. **`OrbitalStrike.cs`**, **`WindItem.cs`**, and **`Textbook.cs`** are three examples of items.

**`ItemDisplay.cs`**: Displays what items the player has in the UI.

**`MeeleEnemy.cs`**: Controls the behavior of melee-type enemies, including movement, tracking, and attacking the player. Handles attack cooldowns, attack range detection, and height-based attack conditions. Enemies will face the player, stop when within melee range, and perform melee attacks when conditions are met. Includes customizable parameters for attack cooldowns, tracking distance, and movement stopping distance. Visual debugging tools are provided via OnDrawGizmosSelected for attack, stop, and tracking ranges.

**`MovingPlatform.cs`**: Manages the behavior of a platform that moves between predefined waypoints. Supports smooth movement, adjustable speed, and waypoint cycling. Automatically detects and attaches/detaches the player to ensure proper movement synchronization when they stand on the platform. Includes optional delays and customizable parameters for movement and player interaction. Designed for seamless integration into platforming levels with dynamic player interaction. This is an example of an obstacle found in a level.

**`PlayerController.cs`**: Manages core player functionality, including movement, jumping, sprinting, dashing, attacking, and shooting. Implements advanced jumping mechanics with jump buffering (allowing jumps to be registered shortly before landing) and coyote time (allowing jumps to be performed shortly after leaving a platform). Handles combat mechanics for both melee and ranged attacks, with support for damage modifiers, cooldowns, and special effects like poison and critical strikes. Includes health regeneration, damage handling, and healing mechanics. Controls player animations, sound effects, and interaction with items and environmental objects. Provides customization for abilities, class-specific features (e.g., ninja mode, grapple gun), and dynamic UI feedback for ability cooldowns and health status. Designed for responsive player control and immersive gameplay experiences.

**`SupportEnemy.cs`**: Manages the behavior of support-type enemies, focusing on healing and strategic positioning. This enemy can teleport to nearby damaged allies within a specified range if they are within a critical health threshold and close to the player. Once teleported, the support enemy heals the targeted ally over time with a cooldown system to prevent rapid healing. After a set duration, the enemy returns to its original spawn location. Parameters like teleport range, player proximity detection, healing cooldown, and health thresholds are customizable. Includes visual debugging via OnDrawGizmos to display the teleportation range.
