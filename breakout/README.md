Introduction to Scratch and Breakout! Walk Through
After you are done with these instructions you will have a full working version of 
the Classic Atari Game, Breakout! It’s ok if you don’t know what any of that means.  
It’s not your fault.  If you get stuck, grab another student who has been here before 
and done that and have them walk you through the issue (don’t let them do it for you... 
that’s not fun and you won’t learn it as well.)

Head to http://scratch.mit.edu and click Create to get going

If you need a refresher on scratch, go to https://github.com/coderdojoindy/tutorials/blob/master/intro_to_scratch/tutorial.md

**Step 1: Delete the cat.  **
The cat is cool and all, but we need a ball.
Select the cat and right click on it.  Click “Delete.”  Adios cat. (That is Spanish for “Good bye cat”).

**Step 2: Let’s create a Ball**
Click the icon that looks like this. ![new sprite](https://raw.githubusercontent.com/coderdojoindy/tutorials/master/breakout/paint-sprite.png) 
It is the “paint new sprite icon.”

A window will come up that might look familiar, we need to draw a filled circle. It can be any color you want.

![new sprite](https://raw.githubusercontent.com/coderdojoindy/tutorials/master/breakout/paint-sprite-ball.png)

and set the center on it. 

![new sprite](https://raw.githubusercontent.com/coderdojoindy/tutorials/master/breakout/paint-sprite-center.png)

It’s a good idea when you program to give things good names.  After you click OK you’ll see your ball 
in the middle of the stage.  And it will be called Sprite1, that is not a very good name.  
It’s a ball, let’s call it what it is. Click the blue i and change the name.

**Step 3: Let’s make the ball move**

The ball we have now isn't cool... it doesn’t do anything.  Let’s point it in a direction and make it move.
The thing that starts our program is clicking on the green flag ().  So the first thing we want to do is 
make something happen when the green flag is clicked.  This happens to be a script block under the 
Events script block category. ![new sprite](https://raw.githubusercontent.com/coderdojoindy/tutorials/master/breakout/flag-clicked-events.png) 
to make ![new sprite](https://raw.githubusercontent.com/coderdojoindy/tutorials/master/breakout/flag-clicked.png)

I want to take the time to point out some of the parts of a script block and how they interact with each other. 
Blocks that connect with each other have a tab and a tab shaped notch. In the picture above the 
[When Green flag clicked] block has a tab on the bottom, and the forever block has a notch in its top. 
Notice that the forever block has a tab inside too. Will the [wait (1) secs] block fit inside the forever block?

This is a lot like Legos. There are also blocks that have pointy ends <> and blocks that have rounded ends (). 
They will fit into holes that have pointy ends and rounded ends. We’ll see more of that later. 
Let’s continue, we want the ball to move in a direction when we click the green arrow. So the first 
thing we need to add is a command to point the ball in the right direction.  

What category do you think changing direction the ball is pointed is under?

It is under the motion category. And it’s called [point in direction] and then there is a drop down.  
The default is 90. The directions are degrees on a circle, there are 360 of them. If you picture a 
clock that will help you think about the directions. 0 degrees is 12 o’clock; 90 is 3 o’clock; 
180 is 6 o’clock; 270 is 9 o’clock; and 360 is 12 o’clock again (a full circle). This is why when 
a skateboarder does a complete rotation off of half pipe it’s called a 360... or in the case of 
Tony Hawk a 720 (2 full circles) or a 900 (2 and ½ circles, 360 + 360 + 180). We want to point 
our ball in any direction... so go ahead and enter any value between 0 and 359 (360 is the same as 0).

The next thing we want to do is move the ball. You might want to move the ball a large number once... 
but that won’t animate the ball across the stage. What we need to do is move the ball a small number 
a bunch of times in a row (with a little break in between). The way we do this is with a loop. The 
type of loop we want is the forever loop.

Add a forever block to your program attached to the [point in direction ()] and then add a 
[move (10) steps] block inside of the loop.

Your program should look something like this:
![new sprite](https://raw.githubusercontent.com/coderdojoindy/tutorials/master/breakout/basic-move.png)

Try experimenting with the value in the [move (10) steps] block. First, what do you think will happen to 
the speed of the ball when you make the number smaller? Make your prediction and then try it. What happens 
when you make the number larger? What happens when you change the direction in the [point in direction ()] block? 

You can click the red circle next to the flag to stop your program and then drag the ball back to the 
middle to reset it in between experiments.

**Step 4: Let’s make the ball bounce when it hits the wall.**

Great, now our ball moves in the direction we tell it to and then sticks to the wall and nothing else 
happens. What a great game! We are going to make it a little more interesting. To do that we need to 
ask a question after every ball move. We need to ask “is the ball touching the wall (or edge)”? If the 
answer is yes then we want the ball to bounce. Luckily this is a block that is built into Scratch. 

The block that we need is called [if on edge, bounce] and it is in the motion category.  It is a single 
block that asks a question and then has an action. We’ll see other cases of asking a question and doing 
something based on the answer later.

Here is what our program looks like now in the Scratch script window:

![new sprite](https://raw.githubusercontent.com/coderdojoindy/tutorials/master/breakout/basic-bounce.png)

When you run your program now your ball will bounce all over the place. This looks more like something 
that we can build a game out of.

**Step 5: Let’s make our Paddle!**

Now we are going to make a paddle so we can control where the ball bounces. The paddle is going to be a 
new sprite, it’s a just a long skinny horizontal rectangle and it needs to have a center. We want to 
position it just above the bottom of the screen. Remember to give it a good meaningful name. Sprite1 
is not descriptive or meaningful.

Here is my paddle in the game preview, and next to it is my sprite library showing my paddle sprite and my ball sprite with good names.

![new sprite](https://raw.githubusercontent.com/coderdojoindy/tutorials/master/breakout/paddle.png)

**Step 6: Let’s make the paddle move left and right with the mouse.**

The paddle needs to do something.  It needs to move back and forth.  There are a couple of ways to do this. 
One way is to have it move left and right based on a key press like pressing left arrow and right arrow. 
The other way, the way we are going to do it, involves moving the paddle with the movement of the mouse cursor. 

The middle of the screen is the point with x value 0 and y value 0. As you move to the left the x value 
becomes less than 0, as you move to the right the x value becomes greater than 0. Up increases the value 
of y greater than zero and down decreases it you can see this by moving your mouse over the preview window. 
In the bottom right hand corner the x and y values of the mouse are displayed as you move the mouse.

We want to attach a script to the paddle that runs when the green flag is clicked.  What we want to do 
is set the x position of the paddle to the value mouse x (you can find this in the sensing category). 
We need to do this continuously (similarly to how we made the ball move.  No picture for this one, I 
think you know enough to get this done.  Remember to ask another student for help if you get stuck (or 
flag down a mentor).

**Step 7: Let’s make the ball bounce off of the paddle.**

We are going to go back to the ball sprite now. Remember how we made the ball ask a question and then 
do something to make it bounce of the edges? There was a single motion block that said “if on edge, bounce.” 
Well now we need to ask a different question. We want to make the ball bounce off of the paddle. 
What question do you think we need to ask?

The question is “am I touching the paddle?” If the answer is yes then we need to do something to make 
the ball bounce. Let’s start by adding the question. You ask a question with an if block. These blocks 
are under the control category. Drag an if block just below the “if on edge, bounce” block from earlier. 
It should look like this now:

![new sprite](https://raw.githubusercontent.com/coderdojoindy/tutorials/master/breakout/if-block.png)

Look at the shape of that hole in the if block. It is kind of a stretched out hexagon, or rectangle with 
pointy ends. That block shape in scratch is for statements that ask a question. The question we want to 
put in there can be found under the Sensing category:

![new sprite](https://raw.githubusercontent.com/coderdojoindy/tutorials/master/breakout/touching-block.png)

See the question mark? Awesome. Except the question mark won’t always be there as we’ll see later. 
However the shape of the block is the same as the shape of the whole in the if statement. The drop 
down lists all of the sprites in your project so far. Good thing you’ve named your sprites well, 
everyone knows what a paddle is and you don’t have to remember that Sprite2 is actually your padde. 
Go ahead and drag that touching block to the hole in the if block and select paddle. This reads 
“if the ball is touching the paddle then i want to do whatever is contained in the if block”.  

To make the block bounce off the paddle in interesting ways without having to do a lot of math we’re going 
to use a pretty effective and easy shortcut. We are going to tell the ball to point towards the paddle and 
then rotate 180 degrees (in either direction).  Pretend that you are facing zero or in our example earlier 
12 o’clock, remember that 180 degrees from 12 o’clock is 6 o’clock, so if you spin to your right 180 degrees 
you’ll be facing the opposite direction. I bet you can figure out which blocks will point the ball at the 
paddle and then turn the ball 180 degrees (hint: you may have to tell the block that does the turning how 
many degrees to turn). Go ahead and drag them into the if block so that they both only happen inside of the 
if block in that specific order; point at the paddle and then rotate.  

Click the green arrow and TEST your program to make sure the ball is doing what you expect it to be doing. 
Any of the mentors will be happy to explain why this works if you ask.

**Step 8: Let’s reset the ball when it hits the bottom of the screen.**

Now we are going to make the reset to a spot when it hits the bottom of the screen and start over. 
There are a couple of ways to do this, you can check the position of the ball and if its y value is 
less than a certain number you can say it’s at the bottom. Or you can do what we’re going to do because 
it’s a little faster.  

Click on the stage in your sprite library and at the top of the screen click on the backgrounds tab.  
Click edit next to the only background in that tab.  draw a thin line at the very bottom of the screen, 
you can make it any color you want other than white or the color that your ball is. This is what mine looks like:

![new sprite](https://raw.githubusercontent.com/coderdojoindy/tutorials/master/breakout/game-screen.png)

Now click on the ball sprite. We’re going to add another question block, this time we want to ask if the 
ball is touching our specific color. If it is then we want to move to roughly the middle of the screen 
just above the path that the paddle moves along pointing straight up. You know everything you need to 
know about if statements and sensing and motion now that you should make a real attempt to do this on 
your own. Of course, ask questions if you get impossibly stumped, a mentor or another student should be 
able to help you get back on the right path.

Step 9: Let’s add a lives and make them decrease when you lose a ball.

We are going to introduce the idea of counting lives and decreasing them when the ball hits the bottom of 
the screen now. To store a value like the number of lives left you use something called a variable. In scratch 
we are going to use the variable on the stage. We also need to introduce another idea called an event. An 
event is like a facebook post to your friends. They decide that they want to see your posts and when you 
make a post it gets delivered to all of them, you don’t have to select who gets it you post it to one 
place and everyone who wants to see it can see it.

To do this we’re going to do something called refactoring, or rewriting part of our program. To start, 
let’s add a variable to the stage. Select the stage in your sprite library and then click the Variables 
script block category. Click the Make a variable button. Give the variable a meaningful name, maybe 
number_of_lives_left? You should see some new blocks in the Variables block library.

![new sprite](https://raw.githubusercontent.com/coderdojoindy/tutorials/master/breakout/variables-lives.png)

You can store a value in the variable, modify the value of the variable, show, and hide the variable 
using the instruction blocks.  You can use the variable by dropping it into holes that match the pill 
shaped block that has the variable’s name. We’ll see that working now.

In the script tab for the stage, add a “When Green Flag Clicked” control block. Then drag the instruction 
block from the Variables category for “set <variable name> to value” underneath of it. I think 3 is a good 
number of lives to start with. You could make your game hard by making it 1. After that drag out a broadcast 
control block and give your message a name, I think a meaningful name of this message is “launch ball”, you’ll 
see why next.

![new sprite](https://raw.githubusercontent.com/coderdojoindy/tutorials/master/breakout/broadcast-launch-ball.png)

Next, click on the ball sprite. We want to replace the “When Green Flag clicked” block with a new block, 
“When I receive “launch ball”. We want to position the ball one time everytime launch ball is called so 
we’ll move the positioning blocks out of the “if touching color” block and put it at the top, right under 
the “When I receive “launch ball”” block.

When we touch the bottom of the screen we we need to decrease the value of the number_of_lives_left 
variable by 1 and then we want to launch the ball. here is what our ball script now looks like this:

![new sprite](https://raw.githubusercontent.com/coderdojoindy/tutorials/master/breakout/launch-ball.png)

Make sure you test your game and make sure that every time the ball hits the bottom of the screen the number 
of lives decreases. If you click the green arrow the count should reset at 3 and the ball should launch from 
its start point.

**Step 10: Let’s add a game over screen.**

Right now the number of lives that we have will just keep on dropping past 0 and beyond everytime the ball 
hits the bottom of the screen. This game, like life, should have consequences. Your fellow ninjas in the 
dojo have found great joy in punishing failure with a game over screen. So let’s create a simple one and 
then show it.

Click on the stage and then select the background tab. Click the paint button and make a simple screen, 
maybe with just a different background color and some text that says game over, once you are done give 
your background a meaningful name, like “game over screen”

Here is what the background tab looks like when you are done.

![new sprite](https://raw.githubusercontent.com/coderdojoindy/tutorials/master/breakout/gameover-backdrop.png)

Now we need to switch to the scripts tab and before we launch the ball after the ball drops and we’ve subtracted 1 from the number_of_lives_left variable we need to ask a question. If the number_of_lives_left is greater than 0 then we need to launch the ball otherwise we need to show the game over screen.

You know how to start asking a question, you use the if block, this time we are going to use the if else block. The thing we need to talk about is the actual heart of the question: Is number_of_lives_left greater than 0? To do that we need to use blocks in the Operators block category. The operator we want is > and we need to drag the number_of_lives_left variable into the left side and set the right side to 0. We want to then move the “broadcast “launch ball”” block inside the if and inside the else we want to add a block that changes look of the stage. What category do you think that is under? See if you can actually find the right block before you look at the following picture.



Now it’s important to test your program. start the program, let the ball hit the bottom three times and then you should see the game over background. What happens if you click the green arrow to start again? The game over background is still there. This is a bug, it’s ok, we can fix it, but it’s why you test. It looks like we need to initialize the background when the green flag is clicked. We can add that either before or after setting the number of lives, but before we broadcast the launch ball message.



Now retest your game. That should be better.

You should take some time to explore some of the other tools and go nuts customizing yours. Maybe add a deriding message or one of encouragement to try again.  Try hiding the ball and the paddle when the game ends. Would you want to broadcast a message for that? Maybe add new sprites to the game over screen that allow you to restart the game? Did you remember to test? Does your game restart correctly with your changes?  It’s up to you, get creative.

**Step 11: Let’s add brick.**

We are going to add a brick for our ball to smash into pieces now. We need to think about how we do this though because we are going to be making copies of this brick and we want to make sure that our one brick works well and that our new bricks will work without having to make specific changes to each one.

Paint a new sprite, name it brick. Here is what my brick looks like on the stage.

![new sprite](https://raw.githubusercontent.com/coderdojoindy/tutorials/master/breakout/brick-on-stage.png)

**Step 12: Let’s make the ball bounce off of the brick.**

The best way we can make the ball bounce off all of the bricks in the same way is to use the color of the bricks.  We need to add another touching color question to the forever loop for the ball. Here we’ll just modify the direction to make it bounce off the brick.  For simplicity’s sake we’ll just point the ball in the direction 180 degrees - the ball’s current direction.  This isn’t the best way to make the ball bounce but it’ll do for now.  Try this one without a picture. Again, grab a mentor or another student when you are done to have them review what you’ve done if you don’t get it.

**Step 13: Let’s make the brick disappear when the ball bounces off of it.**

We need to destroy the brick when the ball hits it.  The brick only has to know about one ball for now so we can ask a question about whether the ball is touching the brick.  The brick should start asking that question when it receives the launch ball message. You want to use the “wait until” control block for this and the question that has to be true is “brick touching ball?”. When that happens then you want to hide the brick.

Test your game, make the brick disappear.  Restart the game. Did the brick show back up? No? You found another bug. We are initializing the ball whenever the launch ball message is broadcast, but we don’t want to re show the brick for every launch ball message (because then all of the bricks would come back every time you dropped the ball). We want to have the stage broadcast another message and then wait for all of the handlers to finish before continuing.  In control there is a “Broadcast [ message ] and wait” control block. Go ahead and broadcast a new game message after the green arrow is clicked on stage and then add a “When I receive [ message ]” block to the brick’s script and attach a show command to it.

Again , ask if you get stuck.

**Step 14: Let’s make a player score that goes up when the ball hits a brick.**

Whenever a brick destroys itself it should just broadcast a message about that event.  The stage can listen for that message and then increase the player’s score.  Add a player_score variable to stage and make sure that it initializes to 0 when the green flag is clicked.

In the brick script add a block to broadcast a message “brick destroyed” either just before or just after the hide block. 

Go back to the stage and add a “when I recieve [brick destroyed]” block and hang off of that incrementing the players score.  I think bricks are worth 100 points each, but you can make it whatever value you want.

**Step 15: Let’s make more bricks.**

Ok, now I think the brick is good enough that we can copy it a bunch of times and arrange them however we want.  Try it.  Right click on your brick, duplicate it. Give your bricks names like brick 1, brick 2, brick 3.  Position them wherever you want on the stage. Notice how you don’t have to modify the code of the brick and they just work when you start the game. Pretty neat.

Step 16: Show a victory screen when all of the bricks are destroyed.

We have losing the game accounted for but how do you win?  Well, we need to keep track of destroyed bricks and then show a win screen when the number of bricks left are 0. Add a variable to stage called number of bricks and initialize it to the number of bricks you have on your stage.  When you receive the brick destroyed message, change the bricks_left variable by -1 and then ask the question if bricks_left is equal to 0.  If it is then show a win screen and maybe broadcast a message to stop the ball (and prevent the game over screen from showing up if the player stops hitting the ball.)

**Next steps**
How would you add another level?  Could you add power ups that drop when the top bricks break?  How would you add a second ball? What changes would that cause you have to make in the rest of your program?  How about making the paddle bigger or smaller?  How about an exploding brick that blows up the bricks around it?

**Solution**

Stage Scripts

![new sprite](https://raw.githubusercontent.com/coderdojoindy/tutorials/master/breakout/stage-scripts.png)

Ball Scripts

![new sprite](https://raw.githubusercontent.com/coderdojoindy/tutorials/master/breakout/ball-scripts.png)

Paddle Scripts

![new sprite](https://raw.githubusercontent.com/coderdojoindy/tutorials/master/breakout/paddle-scripts.png)

Brick Scripts

![new sprite](https://raw.githubusercontent.com/coderdojoindy/tutorials/master/breakout/brick-scripts.png)
