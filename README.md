<div align="center">

🎮 JumpQuest 3D

<img width="703" height="338" alt="Capture" src="https://github.com/user-attachments/assets/a88042fd-b44b-4d7e-9fae-b0d5cdbe72c8" />


Click for Game play preview: https://drive.google.com/file/d/13MFpc3vxIPlvXScImgaHXa69PfqNdxiJ/view?usp=sharing


A 3D Platformer Game Built with Unity
Jump • Explore • Collect • Survive



A platforming adventure built around precise jumps, collectibles, enemy encounters, and moving platforms.
</div>

📌 Table of Contents
- About the Game
- Gameplay at a Glance
- Features and Mechanics
- Controls
- Technology Stack
- Technical Skills
- Project Structure
- Getting Started
- Gameplay Flow
- Ideas for Future Development
- Credits and Attribution
🕹️ About the Game
JumpQuest 3D is a Unity-based 3D platformer where players move through platform-based levels, jump across gaps, collect coins, avoid hazards, and make their way to the finish.
The project brings together core gameplay systems such as physics-based movement, ground detection, enemy interactions, moving platforms, collectible tracking, audio feedback, and scene transitions.
Project type: Unity game development
Primary language: C#
Engine version recorded in project settings: Unity 2020.3.8f1

⚡ Gameplay at a Glance
Gameplay element	What it does
🏃 Player movement	Move around the 3D level using directional input
⬆️ Jumping	Jump when grounded to cross gaps and reach platforms
🪙 Coin collection	Collect items and increase the on-screen counter
👾 Enemy encounters	Bounce off enemy heads and avoid dangerous body collisions
↔️ Moving platforms	Travel between configured waypoints
🧲 Sticky platforms	Stay attached to a platform while standing on it
☠️ Death and restart	Restart the current level after falling or a dangerous collision
🏁 Level finish	Reach the finish trigger to progress to the next scene


🧩 Features and Mechanics
🏃 Player Movement and Jumping
- Reads Unity's Horizontal, Vertical, and Jump input mappings.
- Uses a Rigidbody for physics-aware movement.
- Checks whether the player is grounded before allowing a jump.
- Uses Physics.CheckSphere with a configured ground layer and ground-check position.
- Plays audio feedback when the player jumps.
🪙 Coin Collection and Score Tracking
- Detects coin pickups through trigger events and the Coin tag.
- Removes the collected coin from the scene.
- Updates the coin count and on-screen UI text.
- Plays a collection sound for immediate feedback.
👾 Enemy Interaction
- Detects contact with an enemy head through the Enemy Head tag.
- Removes the enemy's parent object when the player lands on its head.
- Triggers another jump after a successful head interaction.
- Treats contact with an object tagged Enemy Body as a player-death condition.
↔️ Waypoint-Based Moving Platforms
- Moves a configured object through a list of waypoint transforms.
- Checks the object's distance from its current target.
- Advances to the next waypoint when the target is reached.
- Loops back to the beginning of the waypoint sequence.
- Uses a configurable movement speed.
🧲 Sticky Platform Behaviour
- Parents the player transform to a platform while contact is maintained.
- Removes the parent relationship when the player leaves.
- Helps the player travel with a moving platform while standing on it.
☠️ Death and Restart System
- Checks whether the player has fallen below a configured height.
- Detects enemy-body collisions as a death condition.
- Plays a death sound and guards against repeated death processing.
- On enemy-body collision, hides the player's mesh, makes the Rigidbody kinematic, and disables player movement.
- Reloads the current scene after a short delay.
🔄 Rotating Objects
- Rotates configured objects around the X, Y, and Z axes.
- Exposes rotation speed for each axis.
- Uses frame-time scaling to make rotation less dependent on frame rate.
🏁 Menus and Scene Progression
- Starts the game by loading the next scene in the build order.
- Loads the next scene when the player reaches the finish trigger.
- Includes a quit action on the end menu.
- Contains scene files for a start screen, two levels, and an end screen.
🔊 Audio Feedback
Audio sources provide feedback for key gameplay events, including:
- Jumping
- Collecting coins
- Player death
🎮 Controls
The player controller uses Unity's legacy Input Manager axes. Exact bindings depend on the project's Input Manager configuration.
Action	Input
Move	Horizontal and vertical axes — commonly W, A, S, D or arrow keys
Jump	Configured Jump input — commonly Space


🛠️ Technology Stack
Technology	Purpose
Unity	Game engine, scenes, components, and physics
C#	Gameplay scripts and game logic
Rigidbody & Colliders	Physics, movement, and object interaction
Collision & Trigger Events	Pickups, enemy interactions, and finish detection
Unity UI	Coin counter and menu interactions
AudioSource	Gameplay sound effects
SceneManager	Level loading and scene transitions


💡 Technical Skills
C# and Gameplay Programming
- Unity MonoBehaviour scripting
- Methods, variables, conditionals, and event-driven logic
- Unity lifecycle methods such as Start() and Update()
- Inspector-configurable fields using [SerializeField]
- Component access and script enable/disable behaviour
Physics and Interaction
- Rigidbody-based movement
- Jump velocity and grounded-state checks
- Physics.CheckSphere ground detection
- Collider tags, collision callbacks, and trigger callbacks
- Transform parenting for platform attachment
Game Systems
- Collectible and score-counter logic
- Enemy interaction and player-death conditions
- Delayed scene reload
- Waypoint-driven movement and object rotation
- Audio feedback and UI updates
- Menu actions and scene progression
Unity Editor Workflow
- Configuring components and object references in the Inspector
- Working with tags, layers, colliders, Rigidbody components, waypoints, and audio sources
- Separating gameplay responsibilities across focused scripts
🗂️ Project Structure
The project includes the following principal gameplay scripts:
Script	Responsibility
PlayerMovement.cs	Player movement, grounded jumping, jump audio, and enemy-head interaction
ItemCollector.cs	Coin pickup detection, score count, UI updates, and collection audio
PlayerLife.cs	Falling and enemy-body death conditions, death feedback, and scene reload
WaypointFollower.cs	Movement between configured waypoints
StickyPlatform.cs	Attaches the player to a platform during contact
Rotate.cs	Continuous rotation around configured axes
Finish.cs	Loads the next scene when the player reaches the finish trigger
StartMenu.cs	Starts the game by loading the next scene
EndMenu.cs	Quits the application


The project also contains scenes for the start screen, Level01, Level02, and the end screen, along with audio assets.
🚀 Getting Started
Requirements
- Unity Hub
- A compatible Unity Editor — the project settings identify Unity 2020.3.8f1
Open the Project
1. Clone or download this repository.
2. Open Unity Hub.
3. Select Add project from disk.
4. Choose the project folder containing Assets, Packages, and ProjectSettings.
5. Open the project and allow Unity to import its assets.
6. Open the start-screen scene from the Assets/Scenes folder.
7. In File → Build Settings, confirm that the start screen, levels, and end screen are included in the intended order. The menu and finish scripts use the next build index to change scenes.
8. Press Play in the Unity Editor.
Troubleshooting
If the project does not run as expected:
- Check the Unity Console for errors.
- Verify Inspector references, tags, layers, colliders, and Rigidbody settings.
- Confirm the ground-check position and ground layer.
- Check the Input Manager bindings.
- Confirm that scenes are included in Build Settings in the correct order.
🧭 Gameplay Flow
1. Start the game from the start screen.
2. Move through the level and use jumps to cross gaps and reach platforms.
3. Collect coins to increase the displayed counter.
4. Time jumps around enemies and moving platforms.
5. Avoid enemy bodies and falling off the level.
6. Reach the finish trigger to load the next scene.
7. Continue through the available levels to reach the end screen.
🔮 Ideas for Future Development
The following are potential improvements, not claims about existing functionality:
- Add a pause menu and settings screen.
- Save coin totals or high scores between sessions.
- Introduce checkpoints and a lives system.
- Improve character animations and camera behaviour.
- Add more enemy behaviours and progressive difficulty.
- Add controller or mobile input support.
- Refine the HUD and menus.
- Include gameplay screenshots, a trailer, and a downloadable build.
🙌 Credits and Attribution
If this project uses tutorial-based code, third-party assets, sound effects, or other creators' work, credit the original sources here and follow their licence terms. Be clear about which systems you implemented or modified yourself.
<div align="center">

JumpQuest 3D · Unity · C# · 3D Platformer
Thanks for checking out the project!
</div>
