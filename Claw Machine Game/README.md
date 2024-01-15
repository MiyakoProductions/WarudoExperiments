This experiment is making a simple claw machine-style game using only 2 blueprints and some assets.

An example of it in action can be watched at https://x.com/ChiuYukina/status/1746348404664685054?s=20

To use these blueprints you will first need to setup your scene with at least the following assets:
* Character
    * Needs two animation profiles, a default idle and a second named "Claw Grabbed" using your animation of choice.
      * I am using the idle animation "040_0230"
* Anchor
     * Renamed to Claw Anchor.
     * Do not attach it to anything.
* Screen
    * Renamed to Goal, uses an image.
      * I am using Icons/x.png
* Prop
    * Set to cat paw or anything else and attach it to the Claw Anchor.
      * For the paw the transform should be Position: x 0, y 0.2, z -0.3 Rotation: x 0, y 90, z -90)

Let's start with the first blueprint which controls the logic. For this to work, make sure you add these variables:
* isNear (Boolean)
* isGoal (Boolean)
* isNotGrabbed (Boolean)
* isActive (Boolean)
* CharX (Float
* CharZ (Float
* ClawX (Float)
* ClawZ (Float)

The blueprint is fairly big so I split it up into smaller parts to explain the logic.

First we setup distance checks to see where our character is relative to the claw and goal.
![Part 1](images/Claw%20Machine%201.png)

Then we add a reward for the player based on the distance to the goal.
![Part 2](images/Claw%20Machine%202.png)

Next, we add some logic to move the player with the claw if they are grabbed by it.
![Part 3](images/Claw%20Machine%203.png)

Now we need to simulate moving the claw down to grab our player like a real claw machine.
![Part 4](images/Claw%20Machine%204.png)

Then we add the ability to drop the player.
![Part 5](images/Claw%20Machine%205.png)

Lastly, we add controls in a second blueprint.
![Part 6](images/Claw%20Machine%206.png)
