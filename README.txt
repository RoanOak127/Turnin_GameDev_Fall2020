-----------------------------------------------------------------------------------
Assignment 3: Tower Defense-Like Game README
-----------------------------------------------------------------------------------
Student Name: Roan Dominguez
Student abc123: ppb219
-----------------------------------------------------------------------------------
Links to Project (if you used Google Drive, OneDrive, or Dropbox for submission)
-----------------------------------------------------------------------------------
Please provide your Google Drive, OneDrive, or Dropbox link here if you used it for 
your submission, otherwise you may skip this section if you just submitted your
assignment on Blackboard (zipped up). (Make sure the link does not expire and the 
link permissions allow us to download, otherwise you may receive a grade of 0 on 
your assignment submission if we cannot download it.)

Place this Link to Your Unity Project Here: https://github.com/RoanOak127/Turnin_GameDev_Fall2020/blob/master/NeverEnding_TowerDefense.zip



-----------------------------------------------------------------------------------
Version of Unity You Used for Your Game
-----------------------------------------------------------------------------------
Please write down the version of Unity you used when making your game here (e.g.
2019.4, 2020.1, 2020.2, etc...): 2020.1.2f


-----------------------------------------------------------------------------------
Which Operating System You Made Your Game In
-----------------------------------------------------------------------------------
Please write down which operating system the computer you used while you worked in 
Unity has.  Are you using a MS Windows PC, or a Mac, or a Linux computer, etc.?  
(This matters because when you build the game, some of the files Unity produces 
will be different and your grader needs to know this in order to properly open 
your project): MS Windows PC


-----------------------------------------------------------------------------------
Game Controls 
-----------------------------------------------------------------------------------
Please explain what your buttons do. (You do not have to use all of these buttons.
If you use buttons other than these, please mention them to let us know.)

Mouse Movement: Moves the mouse pointer
Mouse Click: Can interact with various buttons on screen
W or ↑: NA
A or ←: NA
D or →: NA
S or ↓: NA
Spacebar: NA
Esc: NA


-----------------------------------------------------------------------------------
Assets Downloaded for Game
-----------------------------------------------------------------------------------
Any assets that you downloaded and used from the Asset Store needs to be documented.
Please provide any links to these assets from the Asset Store you downloaded here:

https://assetstore.unity.com/packages/audio/sound-fx/free-sound-effects-pack-155776

https://assetstore.unity.com/packages/3d/characters/humanoids/fantasy/modular-rpg-heroes-polyart-138600

https://assetstore.unity.com/packages/3d/environments/fantasy/awesome-stylized-mage-tower-53793

https://assetstore.unity.com/packages/3d/vegetation/trees/low-poly-tree-pack-57866


-----------------------------------------------------------------------------------
Instructions for Students
-----------------------------------------------------------------------------------
Please make sure you place all of your written scripts within a folder called 
"Scripts" to make it easier for the professor and/or TA/grader to find your 
written code for grading.

The following sections are divided into each grading criteria for your assignment
submission. For each section where you must briefly describe something, a sentence
or two is all that is needed just to get your point across. If you did not
implement a particular feature (grading criteria), such as the extra credits, then 
simply mention "Did not do".


-----------------------------------------------------------------------------------
1. Point and Click Interface for Placing/Upgrading Towers (15 pts)
-----------------------------------------------------------------------------------
Briefly describe how you implemented your point-and-click interface for placing/
upgrading towers. e.g. Which script did you write that implements this? (Mention 
whether this script was attached to any game object and which ones.)

***I created various buttons that have an onclick event function with the GameManager object set as its object.It then goes into the GameControl script attached to the GM for the game over and play button to call on functions to play a new level, quit the game, or restart the game. The Buy Menu has its buttons attached to the Buy Towers script, and the Upgrade Menu has the Upgrade Towers script.


-----------------------------------------------------------------------------------
2. 3 Types of Towers with Different Statistics (20 pts)
-----------------------------------------------------------------------------------
Mention your tower types here. (Minimum of 3) Mention which folder in your 
project that you have placed these prefabs so that we can view them.

Name of Folder with Tower Prefabs: Assets/Prefabs
Tower 1: Red Tower
Tower 2: Green Tower
Tower 3: Blue Tower


-----------------------------------------------------------------------------------
3. Towers Should be Upgradable 3 Times Based on Use of Points/Coins/Magic (20 pts)
-----------------------------------------------------------------------------------
Briefly describe how you implemented your towers being upgradable 3 times. e.g. 
Which script did you write that implements this? (Mention whether this script was 
attached to any game object and which ones.)

***I have a Tower Menus script attached to each tower placement button. When a button is pressed, it tells the game control script its location and enables the buy/upgrade menus depending on if there's a tower there. A tower is there so it does upgrade menu, and also displays the number of upgrades this tower has. If the player has enough money and less than 3 upgrades for that tower then they can buy the upgrade and it updates the tower. It auto closes the menu, tells the game controller that the activated tower is null. 


-----------------------------------------------------------------------------------
4. 3 Types of Enemies with Different Stats (20 pts)
-----------------------------------------------------------------------------------
Mention your enemy types here. (Minimum of 3) Mention which folder in your 
project that you have placed these prefabs so that we can view them.

Name of Folder with Enemy Prefabs: Assets/Prefabs
Enemy 1: TwoHandsSword
Enemy 2: DoubleSword
Enemy 3: SwordShield


-----------------------------------------------------------------------------------
5. Target Position That Decreases "Life" if Enemies Cross (10 pts)
-----------------------------------------------------------------------------------
Briefly describe how you implemented a target position that decreases life if
enemies cross this. e.g. Which script did you write that implements this? (Mention 
whether this script was attached to any game object and which ones.)

***Enemy script attached to each enemy has an update function that checks its location based to the next waypoint. Once it's at the last waypoint it dissapears and takes away health (a public variable from the game control script attached to the GM) and updates the display with the new health value. The last position is created in the Path Generator script attached to the game manager. It creates a random 15x15 path from left to right the last waypoint is where the enemies die. 

Please give the x, y, and z coordinate of this target position where enemies will
drain your life if they cross (for the first level at least): Unknown, the path is random each time. Under GameManager in the hierarchy you can scroll down and it's the last number. 


-----------------------------------------------------------------------------------
6. Nice Textured Assets (10 pts)
-----------------------------------------------------------------------------------
It is up to you which assets you would like to add to your game.  Please just
mention a few that you used here:

I like my towers. I got one tower and changed the color to green and blue to create two more towers. 

my enemies all came with interchangable models and animations. They're the Modular RPG Heroes

Fantasy Skybox was used for the skybox that I didn't use in the end, but it also had some grass that I added to my terrain which looks nice. 


-----------------------------------------------------------------------------------
7. Advancing Levels When All Enemies are "Dead" (10 pts)
-----------------------------------------------------------------------------------
Briefly describe how you implemented your character advancing to the next level
after all of the enemies are "dead". e.g. Which script did you write that 
implements this? (Mention whether this script was attached to any game object and
which ones.)

***In the Game Control script in Game Manager, have two Variables: isNextLevelReady and totalEnemiesAlive. isNextLevelReady is only set to true once the Enemy Spawner (attached to Game Manager)  finishes spawning enemies in the coroutine. TotalEnemiesAlive is set to the total number of enemies for this level, and the player isn't able to go to the next level until that number is 0. In the Enemy script attacehd to each enemy is where it checks if it's either dead or crossed the "finish line", either option brings total enemies down by 1. Once isNextLevelReady is true and the total is 0, it sets isNextLevelReady back to false, and then calls setNextLevel. That increases the enemies based on what level number we're on, updates the EnemySpawner so it knows the new number of enemies, updates the total, and then enables the play button again. 


Briefly describe what pops up when you advance to the next level. If there is a 
script associated with this, what is it and what game object is it attached to?

***The play button on the button right corner goes from the waiting sand clock to the play symbol triangle.


Briefly describe how each level has more or stronger enemies. e.g. Which script did
you write that implements this? (Mention whether this script was attached to any
game object and which ones.)

***It has more, I touched on it earlier but in the setNextLevel, it adds 3 more easy enemies, 2 more medium enemies every 2 turns, and 1 more hard enemy every 3 turns.


-----------------------------------------------------------------------------------
8. Audio FX and Music (10 pts)
-----------------------------------------------------------------------------------
-Audio-
You are free to use whatever 3D audio FX sounds you like. You can use as many sounds 
as you would like for things like your towers shooting, enemies shooting/attacking,
enemies dying, etc. Please list the sounds you used in your game here:

         Audio FX Sound Effect       |      When Audio FX is Used
1) Flare Gun		    	     | Green Tower Shoots
2) Laser Gun			     | Red Tower Shoots
3) Magic Spell - turn to stone	     | Blue Tower Shoots
4) Walking in Chain Mail	     | Hard Enemy Walks


-Music-
You are free to add whatever music you wish to your game. Please list the name of 
the songs used and where they appear in your game. If you downloaded them from a 
website, please document the source. If you used more than 2 songs, please list 
them and their source as well.

1) Music Song Name: Main Music
   Where This Appears in Your Game: Attached to Music Player in Game Manager object, constantly playing for most of the game run
   Music Song Source: https://tallbeard.itch.io/music-loop-bundle

2) Music Song Name: Death Music
   Where This Appears in Your Game: When player dies and game over menu appears
   Music Song Source: https://tallbeard.itch.io/music-loop-bundle
	****I FORGOT TO ATTACH THIS OMG. I have it in my sounds folder but I forgot to do the thing. Did not Do :(


-----------------------------------------------------------------------------------
9. Terrain With Nice Trees and Stuff (10 pts)
-----------------------------------------------------------------------------------
Mention which folder you have placed your textures for your terrain here:
Assets/Textures/SurfaceTextures

Mention which folder you have placed your tree prefabs that you used:
Assets/Textures

If you used, any other stuff, please mention the folder you placed these prefabs
here:
Assets/Textures


-----------------------------------------------------------------------------------
10. Particle Effects (10 pts)
-----------------------------------------------------------------------------------
Mention which folder you have placed your particle effects here:

You are free to add whatever particle effects you want for your game, such as
explosions or spells, but please list them below:

          Particle Effect       		 
1)  "RedTowerFire" fast and small, red particles shoot up from tower				   
2)  "Green Tower Fire" slower and longer green particles shoot up from tower
3)  "AOE" blue ring expands from tower
4)  "Death Particles" yellow lights floating away from dead enemy                             

-----------------------------------------------------------------------------------
11. Game Should Run With Reasonable Performance (40-60 fps) (15 pts)
-----------------------------------------------------------------------------------
Your game should be playable in 40 to 60 frames per second. Please make sure that 
you test your game with this frame rate before submitting your assignment.


-----------------------------------------------------------------------------------
*Extra Credit* Fully Featured HUD (5 pts)
-----------------------------------------------------------------------------------
Please fill in the following list for your HUD features and their locations within
the HUD (such as top-left, bottom-right, top-center, bottom-center, etc.):

       		 HUD Feature        		  |      Location within HUD
1) Current Level       				  | Bottom Right to the left of Play Button
2) Number of Enemies Left to Kill in Current Wave | Top Middle
3) Icons for Current Points/Coins/Gold etc.       | Bottom Middle ($)
4) Icon for "Life"                                | Bottom Left (the progress bar)

Please mention the scripts that are associated with each of these HUD features.
***They're all attached to the GameControl script in GM which sets them, the Enemy script changes number of enemies and health and money 

What is your character's life based on (i.e. hit points, money left, etc.)?
***Hit Points


-----------------------------------------------------------------------------------
*Extra Credit* Game Menus, Nice Title Screen, Change/Restart Level (5 pts)
-----------------------------------------------------------------------------------
You are free to add whatever buttons or controls you want for your title screen, 
but you at least must implement some sort of "Play" or "Start" button. You must 
also implement some sort of "Quit" button that quits the game application entirely.
Which script(s) is associated with your Title Screen?

***My "title" screen is the regular screen but the game won't start until you hit the orange play button in the bottom right corner. It's maintained by the game controller in GM.


In addition to your title screen menu, what other game menus did you implement 
(such as a pause menu, a game over menu, etc)?

game over menu: you can quit the game or restart the game.


Which script(s) are associated with each of these menus?
game control attached to GM.


-----------------------------------------------------------------------------------
*Extra Credit* Choose Any Two of the Following for 5pts Each (10 pts)
-----------------------------------------------------------------------------------
----------First-Person Mode----------
Explain how to the player is able to do this. (i.e. Do we need to click something 
or press a button on the keyboard, etc.?)


Which script(s) is associated with this?



----------Pathfinding AI for Enemies----------
Did you use a NavMesh:
(Answer Yes or No)

***YES

If not, then how did you accomplish this?



----------Animation for Characters----------
Briefly describe how you implemented your animation for the characters within the 
game. e.g. Which script did you write that implements this? (Mention whether this 
script was attached to any game object and which ones.)

***There is only one animation, it's run. It plays when created and doesn't stop until the enemy is in the death function where the animator is disabled. This function is in the Enemy script.



-----------------------------------------------------------------------------------
Any Notes or Things the Professor or TA/Grader Should Be Aware Of
-----------------------------------------------------------------------------------
If there are any other concerns that you have about your submission or any known
bugs/glitches in your game that could potentially come up, please explain them here:

Super sorry the music is annoying, I thought it was fine until I had to hear it for awhile and then I just turned off the music player in GM (I recommend)

I know I still get an out of bounds error with my blue tower, but it can play the first 3 levels without a problem. 

I chose to keep the blue tower's sound play on awake because it's cool and it's my new favourite sound.

The screen is resizable

