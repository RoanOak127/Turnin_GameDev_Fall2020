-----------------------------------------------------------------------------------
Assignment 2: Survival-Like Game README
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

Place this Link to Your Unity Project Here:
https://github.com/RoanOak127/Turnin_GameDev_Fall2020/blob/master/PPB219_Toon_Shooter_Survival.zip


-----------------------------------------------------------------------------------
Version of Unity You Used for Your Game
-----------------------------------------------------------------------------------
Please write down the version of Unity you used when making your game here (e.g.
2019.4, 2020.1, 2020.2, etc...):

Unity 2020.1.2f1


-----------------------------------------------------------------------------------
Which Operating System You Made Your Game In
-----------------------------------------------------------------------------------
Please write down which operating system the computer you used while you worked in 
Unity has.  Are you using a MS Windows PC, or a Mac, or a Linux computer, etc.?  
(This matters because when you build the game, some of the files Unity produces 
will be different and your grader needs to know this in order to properly open 
your project):

MS Windows PC


-----------------------------------------------------------------------------------
Game Controls 
-----------------------------------------------------------------------------------
Please explain what your buttons do. (You do not have to use all of these buttons.
If you use buttons other than these, please mention them to let us know.)

Mouse Movement: controls camera movement
Mouse LeftClick: shoots laser
W or ↑: moves character up
A or ←: moves character left
D or →: moves character right
S or ↓: moves character backwards
Spacebar: jump
Esc: NA
leftAlt: pause the game
1 : hold gun1
2 : hold gun2
3 : hold gun3


-----------------------------------------------------------------------------------
Assets Downloaded for Game
-----------------------------------------------------------------------------------
Any assets that you downloaded and used from the Asset Store needs to be documented.
Please provide any links to these assets from the Asset Store you downloaded here:
https://assetstore.unity.com/packages/3d/props/weapons/weapon-master-scifi-weapon-1-lite-134423
https://assetstore.unity.com/packages/essentials/asset-packs/standard-assets-for-unity-2018-4-32351
https://assetstore.unity.com/packages/2d/textures-materials/sky/skybox-series-free-103633
https://assetstore.unity.com/packages/3d/props/guns/sci-fi-gun-heavy-87878
https://assetstore.unity.com/packages/2d/fonts/free-pixel-art-font-pack-blackbold-and-greybold-181381
https://assetstore.unity.com/packages/2d/textures-materials/sky/fantasy-skybox-free-18353

and models and animations from mixamo.com
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
1. Movement - Mouse Look + Keyboard (10 pts)
-----------------------------------------------------------------------------------
Briefly describe how you implemented your mouse look and your character movement. 
e.g. Which script did you write that implements this? (Mention whether this script 
was attached to any game object and which ones.)

I used a character controller instead of rigid body for my character this way they could handle stairs easily, in doing so I had to recreate movement and apply my own gravity. These are handled in the update function of my PlayerMovement Script attached to the player Sporty Granny. They technically both have functions inside of that to handle it. camControl() operates the mouse look and rotates the player left or right. PlayerMove() actually moves the character in the WASD and jump and handles the falling from gravity.
-----------------------------------------------------------------------------------
2. Raycasting - Shooting Enemies or Vice-Versa or 3D Object Selection, etc (20 pts)
-----------------------------------------------------------------------------------
Briefly describe how you implemented your raycasting for things in your game such
as shooting enemies or vice-versa. e.g. Which script did you write that implements
this? (Mention whether this script was attached to any game object and which ones.)

For Player: Shoot script attached to guns used by the player is used to shoot out from the gun, I have a line renderer to show where the laser is being shot at, and then the raycast is created to actually get data on if something was shot.

For Enemy: In EnemyCtrl there's a shoot() function that acts the same way but checks if it's the player being shot at instead of vice versa.
-----------------------------------------------------------------------------------
3. 3 Types of Weapons/Items and a Way to Select Them (20 pts)
-----------------------------------------------------------------------------------
Briefly describe how you implemented your 3 types of weapons/items and how your
selection system works. e.g. Which script did you write that implements this and 
also what button or mechanism do you use to switch between these weapons/items? 
(Mention whether this script was attached to any game object and which ones.)


In Change Guns script attached to the player, pressing guns 1, 2, or 3 will switch the guns. Each gun has it's own shoot script which takes care of that weapons stats. All 3 guns are already attached to the player and so they are just enabled/disabled as needed.
-----------------------------------------------------------------------------------
4. Randomly Spawning Never-Ending Enemies (20 pts)
-----------------------------------------------------------------------------------
Briefly describe how you implemented a stream of randomly spawning (and never-
ending enemies). e.g. Which script did you write that implements this? (Mention 
whether this script was attached to any game object and which ones.)

I wrote the script SpawnEnemies attached the the GameManager Object. It takes in how many are allowed for each level and has a coroutine to spread out the spawn rates. Once a player kills an enemey, the enemy's EnemyCtrl Script knows that it died, figures out which enemy it is (currently by what laser color it's using) and then spawn a replacement.

Did you use spawn points for these enemies?  If so, give the x, y, and z 
coordinates of these spawn points.

Vector3(-39.5999985,-1.60000002,44.5999985)
Vector3(-4.5999999,29.2000008,17.8999996)
Vector3(43.7999992,-1.59000003,-30.3999996)



-----------------------------------------------------------------------------------
5. 3 Enemy Types (10 pts)
-----------------------------------------------------------------------------------
Mention your enemy types here.  (Minimum of 3)  Mention which folder in your 
project that you have placed these prefabs so that we can view them.

all 3 enemies are shooting at the player. Bobbert is fast, not a lot of damage, and terrible aim. Mort is slow, lots of damage, great aim. Seymour is inbetween.

Name of Folder with Enemy Prefabs:
Enemy 1: Prefabs/BobbertZombie
Enemy 2: Prefabs/SeymourOtter
Enemy 3: Prefabs/MortMouse


-----------------------------------------------------------------------------------
6. Pathfinding AI for Enemies (20 pts)
-----------------------------------------------------------------------------------
Please indicate that you indeed used a NavMesh and that there are places on your
map where you must jump to where enemies can follow using off-mesh links: ***YES
(Answer Yes or No)

How many locations on your map did you create where enemies can follow you using 
off-mesh links? 

***2 General locations (the stairs to a platform) but each location has 3 stair jump points to 1 platform end point.

Mention at least one general location with a x, y, and z coordinate that is 
close to where you placed an off-mesh link: (4.66, 9.92, 15.39) 
***(I think based off the world location value. You can find all of these under LevelDesign game object, under Stairs, and are labled Plat1_OffMesh and Plat2_OffMesh
-----------------------------------------------------------------------------------
7. Randomly Spawning Power-Ups (including a "healing" power-up) (20 pts)
-----------------------------------------------------------------------------------
List the power-ups that you implemented in your game (minimum of 3, in
addition to the healing power-up) and the object associated with that power-up
(Explain what your object looks like, such as a yellow coin, blue star, etc.). 
Fill in the following-chart and mention how much health your character gains back 
from a healing power-up:

HealthUp is a red cylinder, SpeedUp is green sphere, SlowEnemy is cyan square, gunDmgUp is orange cylinder

        Power-Up Object	        |                Power-Up Effect
1) HealthUp                     | Healing Effect: Heals _50_ amount of health back
2)   SpeedUp                    | Increases player's Speed by 3
3)   SlowEnemy                  | Slow's all currently active enemies speed by 3
4)   GunDmgUp                   | Increases Player's damage multiplier by +5

Briefly describe how you implemented this being displayed somewhere on the screen,
especially how you randomized the objects and placement of these objects. e.g. 
Which script did you write that implements this? (Mention whether this script was 
attached to any game object and which ones.)

*** I created 5 power up spawn points and placed them in an array in the SpawnPowerUps script attached to the Game Manager object, it starts by putting a health up at index 0. Then every 5 seconds it randomly chooses a powerup to fill the next index, waits 5 seconds and repeats the process until all powerups spawn points are filled. 

HealthUp is 50% likely to show, speedup is 20%, slowEnemy is 20% and gunDmgUp is 10%.


-----------------------------------------------------------------------------------
8. Mecanim-Based Character Animation for Both Enemies and Main Character (20 pts)
-----------------------------------------------------------------------------------
Please list the folder(s) in your project where your animations are stored for your
character/enemies:
 
Player: Assets/Models/Mixamo/Granny/BasicShooterPack
Enemies Assets/Animations (each character has their own folder so BobbertAnims/SeymourAnims/MortAnims

Please list the folder(s) where your Animator Controllers for your character/enemies
are stored: 

Assets/Animations/AnimatorCtrl


-----------------------------------------------------------------------------------
9. Advancing Levels When All Enemies are "Dead" (20 pts)
-----------------------------------------------------------------------------------
Briefly describe how you implemented your character advancing to the next level
after all of the enemies are "dead". e.g. Which script did you write that 
implements this? (Mention whether this script was attached to any game object and
which ones.)

***I decided that each level required the player to kill a certain number of the enemy type each level. In the GameManagerScript attached to GameManager, the update function checks if num(bobbert/seymour/morts) are all 0 or less and if so player has won. These variables are public and the EnemyCtrl script takes one away in the same area that it respawns a replacement.


Briefly describe what pops up when you advance to the next level. If there is a 
script associated with this, what is it and what game object is it attached to?

***The Level Won panel attached to the Canvas attached to the Game Manager pops up to display the current score and if the player wants to continue or leave the game. This is handled by the GameManagerScript attached to GameManager.


Briefly describe how each level has more or stronger enemies. e.g. Which script did
you write that implements this? (Mention whether this script was attached to any
game object and which ones.)

***Each new level reloads the same level with more enemies (+3 to Bobberts, +2 to seymours, +1 to morts). This is handled in the NextLevel() method in the GameManagerScript attached to the GameManager.


-----------------------------------------------------------------------------------
10. Fully Featured HUD (10 pts)
-----------------------------------------------------------------------------------
Please fill in the following list for your HUD features and their locations within
the HUD (such as top-left, bottom-right, top-center, bottom-center, etc.): I created a UI text because I ran out of time

       		 HUD Feature        		  |      Location within HUD
1) Current Level       				  | Top Left Corner
2) Number of Enemies Left to Kill in Current Wave | Middle Left Side
3) Icons for Current Weapons / Items Available    | Did Not Do
4) Icon for "Life"                                | No Icon just text, health is bottom Left

Please mention the scripts that are associated with each of these HUD features.
***GameManagerScript is in charge of all the initial displays. EnemyCtrl will update player's health if shot, player's points (top middle location), and how many enemies are left to kill to win the level. PlayerMovement script updates health if player takes a healthUp powerup.


What is your character's life based on (i.e. hit points, money left, etc.)?
***Hit Points


-----------------------------------------------------------------------------------
11. Game Menus and Nice Title Screen (10 pts)
-----------------------------------------------------------------------------------
You are free to add whatever buttons or controls you want for your title screen, 
but you at least must implement some sort of "Play" or "Start" button. You must 
also implement some sort of "Quit" button that quits the game application entirely.
Which script(s) is associated with your Title Screen?
***GameManagerScript, the quit button is only on the pause, game over, and win menues.


In addition to your title screen menu, what other game menus did you implement 
(such as a pause menu, a game over menu, etc)?
Pause, game over, and win.


Which script(s) are associated with each of these menus?
GameManagerScript handles these as well, including the button press for pause/unpause. Each menu also has some functions attached to the buttons on them.


-----------------------------------------------------------------------------------
12. Nice Textured Assets (10 pts)
-----------------------------------------------------------------------------------
It is up to you which assets you would like to add to your game.  Please just
mention a few that you used here:
All the guns used, background images for the scene and win/gameover/title menues.


-----------------------------------------------------------------------------------
13. Music and 3D Audio FX (10 pts)
-----------------------------------------------------------------------------------
-Music-
You are free to add whatever music you wish to your game. However, there must be 
at least 2 music sources. One for your title screen and the other for in-game.
Please list the name of the songs used. If you downloaded them from a website, 
please document the source. If you used more than 2 songs, please list them and
their source as well.

***Did Not Do

1) Title Screen Music Name:
   Title Screen Music Source:

2) In-Game Music Name:
   In-Game Music Source:


-Audio-
You are free to use whatever 3D audio FX sounds you like. You can use as many sounds 
as you would like for things like your character dying, enemies shooting/attacking,
enemies dying, etc. You MUST use a sound for your weapon/gun firing.   
Please list the sounds you used in your game here:

         Audio FX Sound Effect       |      When Audio FX is Used
1) Weapon/Gun Shot		     | Used whenever the player fires their weapon
2) 				     | 
3) 				     |
4) 				     |


-----------------------------------------------------------------------------------
*Extra Credit* Terrain (5 pts)
-----------------------------------------------------------------------------------
If you implemented a terrain, then please just mention which folder you have placed 
your textures for it here:

Assets/Textures/BaseWorld
-----------------------------------------------------------------------------------
*Extra Credit* Lightmapping (5 pts)
-----------------------------------------------------------------------------------
If you implemented any lightmaps, then please just mention which folder you have 
placed your lightmaps here:

I think I did? I added point lights? They're attached to the PowerUpSpawnPoints (under the LevelDesign game object).


-----------------------------------------------------------------------------------
*Extra Credit* Particles (5 pts)
-----------------------------------------------------------------------------------
If you implemented any particles, then please just mention which folder you have 
placed your particle prefabs here:


-----------------------------------------------------------------------------------
*Extra Credit* Image Effects (5 pts)
-----------------------------------------------------------------------------------
If you implemented any image effects, then please mention what these are and what
game objects they are attached to:


-----------------------------------------------------------------------------------
Any Notes or Things the Professor or TA/Grader Should Be Aware Of
-----------------------------------------------------------------------------------
If there are any other concerns that you have about your submission or any known
bugs/glitches in your game that could potentially come up, please explain them here:

Death Animation for enemies is weird, doing an animation event wasn't working for some reason so had to do a time, but even though they're all using the same death animation from mixamo their times are slightly off so some of them shoot back up after death

Player Model is wack. I don't know why she's like this in scene manager. She's fine once the game starts playing.

Could not animate a humanoid rig according to unity and was unable to make character look up or down. the player can still shoot up or down it just looks wonky

Did not check if player decides to climb over mountain and fall to death. Will have to manually exit out of game or pause  quit/restart game.
