---
title: Ghostbusters
level: Level 1
language: en-GB
stylesheet: scratch
embeds: "*.png"
note: "notes for club leaders.md"
...

# Introduction { .intro}
This project is like the game __Whack-a-Mole__. You get points for hitting the ghosts that appear on the screen. The aim is to get as many points as possible in 30 seconds!
# Giới thiệu
Bản kế hoạch này giống như một trò chơi __Whack-a-Mole__. Bạn ghi điểm khi đánh vào những bóng ma xuất hiện trên màn hình. Mục tiêu là ghi thật nhiều điểm trong thời gian 30 giây!
![screenshot](ghostbsuters_screenshot.png)

#STEP 1: Create a flying ghost { .activity}
#BƯỚC 1: Tạo bóng ma bay
## Activity Checklist { .check}
## Bảng liệt kê hoạt động
+ __Start a new scratch project.__
+ __Remove the cat sprite__ and replace the background with the __nature/woods__ background.
+ Use the `Choose sprite from library` {.blockgrey} button to add a new ghoul
sprite to the project (use the __fantasy/ghost1__ costume). 
+ __Bắt đầu một dự án mới.__
+ __Xóa yêu tinh mèo__ và thay thế phông nền thành phông nền __thiên nhiên/cây cối__ 
__Now we want to make our ghost move__
__Bây giờ, chúng ta muốn làm bóng ma di chuyển__
+ Add a `Variable` {.blocklightgrey} for this sprite only called `speed` {.blockorange}.
On the __Stage__, the stage monitor for this variable should say “__Ghost1 speed__”.
If it just says “speed”, delete the variable and create it again, for this sprite only. Uncheck the box next to the speed block in the __Data palette__ so it does not show on the Stage.
The speed variable will control how fast the ghost moves. We use a variable so that we can change how fast the ghost moves as the game progresses.
+ We want the ghost to start moving when the game starts, __so make a script like this__:
+ Thêm một 'Variable' cho yêu tinh mèo, gọi là 'speed'
Trên __Sân đấu__, người điều khiển của variable này nên nói"__Ma1 tốc độ__"
Nếu nó chỉ nói là 'Tốc độ', xóa variable này và làm lại (chỉ đối với con yêu tinh). Bỏ tích ô vuông bên cạnh ô tốc độ trong phần __Data palette__ để nó không hiện trên Sân đấu.
Biến tốc độ sẽ điều khiển sự di chuyển nhanh hay chậm của ma. Chúng ta dùng một biến sao cho có thể thay đổi tốc độ di chuyển của ma cùng với tiến độ của trò chơi.
+ Chúng ta muốn bóng ma bắt đầu di chuyển khi trò chơi khởi động, __nên làm bản script như đây__:

```blocks

	when FLAG clicked
	set [speed v] to [5]
	forever
		move (speed) steps
```
		
##Test Your Project { .flag}
__Click the green flag__ and see what your ghost does. Why does it get stuck on the edge of the screen?
## Kiểm tra tiền trình
__Click vào lá cờ màu xanh__ và xem bóng ma của bạn làm gì. Tại sao nó bị kẹt ở rìa màn hình?
## Activity Checklist { .check}
## Bảng liệt kê hoạt động
+ To stop the ghost getting stuck we need to make her go back the other way when she touches the edge of the screen. Edit your existing script by adding an `if on edge, bounce` {.blockblue} block below your `move ` {.blockblue}`speed` {.blockorange}` steps` {.blockblue} block.
+ Để ngừng tình trạng bóng ma bị kẹt, chúng ta cần đưa nó trở lại một lối khác khi nó đi vào từ rìa màn hình. Edit bản script hiện tại bằng việc gõ thêm một khối gọi là 'if on adge, bounce' bên dưới 'move' 'speed' 'steps'
```blocks

	when FLAG clicked
	set [speed v] to [5]
	forever
		move (speed) steps
		if on edge, bounce
```
+ To stop the ghost flipping upside down, click on the `rotation style: left-right` {.blockgrey} button in the Sprite Summary area.

##Test Your Project { .flag}
__Click the green flag.__ 
Does the ghost move from side to side across the screen?

##Save your project { .save}

##Things to try { .try}
+ __Try changing the value of the speed variable to make the ghost fly faster or slower.__
+ __How would you make the ghost get faster the longer it flies?__
(This is a tricky one, so don’t worry if you can’t see how to do it. You’ll get more clues as you work through the project.)

#STEP 2: Make the ghost appear & vanish randomly { .activity}

To make the game more fun, we want the ghost to appear and vanish randomly. We’ll do that with another script that runs at the same time as the one that moves the ghost. This new script needs to hide the ghost for a random time, then show it for a random time, and repeat that forever (or until the game finishes).

## Activity Checklist { .check}

__Create this script for the ghost:__

```blocks

	when FLAG clicked
	forever
		hide
		wait (pick random (2) to (5)) secs
		show
		wait (pick random (3) to (5)) secs

```
##Test Your Project { .flag}
__Click the green flag.__ 
Does the ghost move from side to side across the screen and vanish and appear again randomly?

##Save your project { .save}

##Things to try { .try}
+ __Try changing the range of the random numbers. What happens if you pick very big numbers or very small numbers?__
(Does this give you any more clues for how to make the ghost speed up the longer the game is played?)

#STEP 3: Make the ghost disappear when it's clicked { .activity}

To turn this into a game, we need to give the player something to do. They need to click on the ghost to make it disappear. When the ghost is clicked, we want it to disappear and play a sound.

## Activity Checklist { .check}

+ In the __Sounds__ tab, add a new sound __Electronic/fairydust__, using the `Choose sound from library` {.blockgrey} button. 

+ __Add this script to the ghost__:

```blocks

	when this sprite clicked
	hide
	play sound [Fairydust v]
```
##Test Your Project { .flag}
__Click the green flag.__ 

Does the ghost disappear and play the sound when you click it?

##Save your project { .save}

##Things to try { .try}
+ __Ask your volunteer if you can record your own sound to play.__

#Step 4: Add a score and timer { .activity}

We’ve got a ghost, but now we want to make a game! We want to score points every time we click on the ghost but we also want to have a time limit on the game. We can use a variable for the score and the timer.

## Activity Checklist { .check}

+ Create a new `Variable` {.blockgrey} for all sprites called __score__, and alter the script for the ghost to increase this variable by one when it is clicked.

```blocks

	when this sprite clicked
	hide
	play sound [Fairydust v]
	change [score v] by (1)
```
+ Switch to the __Stage__ and create a __new variable__ called __timer__. Add a new script that occurs when the green flag is clicked to set `timer` {.blockorange} to __30__ and reset the score to __0__. Then use a `repeat until` {.blockyellow} block to wait a second and then reduce `timer` {.blockorange}  by
one. This should repeat until timer is 0, at which point use `stop all` {.blockyellow} to stop the game.

```blocks

	when FLAG clicked
	set [timer v] to (30)
	set [score v] to (0)
	repeat until <(timer) = [0]>
		wait (1) secs
		change [timer v] by (-1)
	
	stop [all v]
```


##Test Your Project { .flag}
__Click the green flag.__ 

##Save your project { .save}

##Things to try { .try}
1. __How might you make the ghost speed up as the game goes on?__
2. __Well done you’ve finished the basic game. There are more things you can do to your game though. Have a go at this challenge!__

##Challenge: add more ghosts { .challenge}
If one ghost is good, more must be better! __Let’s have three ghosts flying around.__
1. Duplicate the ghost by __right-clicking__ it in the sprite list.
2. For each ghost __adjust the size of the sprite__ so the ghosts are different sizes.
3. For each ghost change the __speed variable__ so that they fly at different speeds.
4. Move the ghosts around the canvas so that they are not all together.

##Test Your Project { .flag}
__Click the green flag.__ 

Do you have three ghosts that move from side to side across the screen, randomly appear and disappear, and disappear when you click on them?

##Save your project { .save}

##Things to try { .try}

1. __How many ghosts is a good number for the game?__
2. __Can you make the ghosts look different? You could either edit their costumes, or use some blocks from the Looks palette to change them.__
3. __Can you make the ghosts be worth different points? How about making the fastest (and smallest) ghost worth 10 points?__


__Well done you’ve finished, now you can enjoy the game!__
Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar!
