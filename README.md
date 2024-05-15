#Pirate Game
My current progress on my pirate game; ship and melee combat implemented.
Download the Word document which contains a link to the Unity Package on Google Drive. Follow this link and download the package to import to Unity.
***Playing the game***
This is a Unity package, so import the package into Unity. There are two scenes to play with, named "The Sea" and "Town." The Town scene is actually two ships where you and your crew can fight against the enemy pirates. To get the full experience, play starting from the Sea scene; if you wish to fight hand to hand, steer your ship into the enemy ship and the other scene will open.
***Controls***
Ships: W to accelerate, S to slow, A and D to turn left and right; you do not need to hold W to keep moving as W adds forward force. To fire, press Z or X to fire a larboard or starboard broadside, and SPACE to fire all cannons at once (only if all cannons are loaded!)
Melee: WASD to move, look around with mouse. Click to attack. Cutlass equipped by default. Equip pistol by pressing 2, and cutlass by pressing 1. There is also a small swivel cannon near you when you start. You can control it by moving to it and pressing F. Press G to unmount. Use WASD to move the cannon around and SPACE to fire. Your allies are in blue and your enemies in red and white.

***To use the GOAP tool***
To access the sample level, navigate to Assets>Pirate Game>Mansion Screen. Use WASD to control the player pirate (in blue); get the NPC to chase you beyond the door to see the planner in action. Adjust cost values of the GOAP scripts (in the scene, under the GOAPScripts GameObject) to see different plans executed.
The planner displays the plan at the bottom of the screen, displaying the names of the actions in order with their contexts, with the current action being executed highlighted in green.
The necessary GOAP files are located in the Assets>Pirate Game>GOAP folder, along with some actions needed for the sample level.
To create a new action for the planner to use:
1.	Create a new script as a subclass of the GOAPActionParent.cs file, and program your action for the NPC to take from there. The contents of the action are entirely up to the developer, as long as it supplies values to the necessary variables for the planner script to use: a. Prerequisites and PrereqOpposites, both string[] variables that contain the “ready” and “not ready” states of other actions. b. Effect and OppEffect, both string variables that are the “ready” and “not ready” states of this particular action. c. Cost: Int that determines how difficult it would be for this action to be performed, with 0 meaning no difficulty. d. Name: String containing the name of this action e. Func: Lambda function which tells the planner which function from this script to run when this action needs to be executed. f. Context: Optional string variable that supplies context of action being performed to be displayed on screen (for developers only)
2.	Create an instance of this script in the game world under the GOAPScripts GameObject and add it to the Planner’s array of actions, as well as either its “ready” or “not ready” state to the Planner’s game state array as needed.
3.	Call the planner’s parseAction() and planAction() functions and input this action’s entry in the planner’s actions array to create and execute a plan based on it (see scripts in objects from sample level for examples).
For an explanation of the GOAP system and how the planner works, see the attached PowerPoint:
https://docs.google.com/presentation/d/1V9ilDW-cpSI1QhgKpai7BaZ2IIVLr9rv7zMyMjOwHxU/edit#slide=id.g2d0059b83c7_2_111

