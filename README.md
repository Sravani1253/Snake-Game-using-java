# Snake-and-Ladders-game

### Rules
+ The game will have a six sided dice numbered from 1 to 6 and will always give a random number on rolling it.
+ Each player has a piece which is initially kept outside the board (i.e., at position 0).
+ Each player rolls the dice when their turn comes.
+ Based on the dice value, the player moves their piece forward that number of cells. Ex: If the dice value is 5 and the piece is at position 21, the player will put their piece at position 26 now (21+5).
+ A player wins if it exactly reaches the end Point and the game ends there.
+ After the dice roll, if a piece is supposed to move outside position 100, it does not move
+ The board also contains some snakes and ladders.
+ Each snake will have its head at some number and its tail at a smaller number.
+ Whenever a piece ends up at a position with the head of the snake, the piece should go down to the position of the tail of that snake.
+ Each ladder will have its start position at some number and end position at a larger number.
+ Whenever a piece ends up at a position with the start of the ladder, the piece should go up to the position of the end of that ladder.
+ There could be another snake/ladder at the tail of the snake or the end position of the ladder and the piece should go up/down accordingly.
+ Infinite loop: tail of the snake has a ladder to the head of the snake
+ End point and starting point should not from infinite loop
+ Two snakes cannot start at the same point
+ Two ladders cannot srart at the same point

### USER
+ Board size is defined by the user
+ Number of players is given by the user
+ Input to number of snakes is given by the user
+ Input to number of laders is given by the user
+ According to the input of the snakes and ladders the size of snakes and laders also given
+ That is the head and tail of the snake and start and end of the ladder
+ Names of the players also given

### Using SOLID principles each class is seperately defined 
 + Dice class
 + User class
 + Board class
 + Main class

### Dice class

+ We first make a rolldice method 
+ We are considering one dice so the minimum number will be equal to "1" and maximum number will be "6"
+ If for example we consider two dice the minimum number would be "2" and maximum number will be "12"
+ After assigning minimum and maximum numbers 
+ Using "math.random()" which is an inbuilt method 
+ "random()" method is used to generate a random number between the sepecific range
+ in this rolldice method the range is from 1 to 6
+ our minimum number is 1 and maximum number is 6

### User class

+ Using private variables to store the player position and player name
+ this keyword is used to refer current class instance variable
+ Player method with parameters playerposition is an integer and string playername
+ using this keyword we are referring playerposition as playerpos and playerName and playerName
+ int method to get player position and player position value 
+ string method to get player name

### Board class

##### Board class contains
 
+ Start and end points of the game
+ Dice
+ We store the starting point and ending points of the snakes and ladders using a Hashmap
+ A queue is used to store the players
+ Queue uses the principle of first in first out [FIFO]
+ Once the player completes its turn then the turn goes to the next player and the old player is again added to the queue after completion the turns of all the players the first player gets his turn again
+ Method board with parameters starting position ending position haspmap of starting and ending points of snakes , hashmap of starting and ending points of the ladders , a queue of players
+ using this keyword we refer them 
#### Method game
+ ".poll()" methond of Queue interface returns and removes the element at the frontend of the container
+ oldpos is the current position of the player
+ new position is the new value obtained after rolling the dice , that is old position + value obtained after rolling the dice

#### Conditions

1. If the new position equal to the ending point the player finished the game
2. If the new position is in the map of snake positions then the new position beigins from the snake tail position
3. If the new position is in the map of ladders position then the new position begins from the head of the ladder
4. If the new position is greater than ending point of the board then the new position remains same
5. If none of the conditions are there then the new position is new position + old position
 
 + Then the turn goes to the next player after evaluating the conditions with one player and this player is added back to the player queue again
 
 ### Main class
 
 + Taking the input 
 1. size of the board
 2. No of snakes
 3. Starting a hashmap to take the inputs to store the starting and ending points of the snakes
 4. Starting the for loop to store the inputs by spliting
 5. No of ladders
 6. Starting a hashmap to take the inputs to store the starting and ending points of the ladders
 7. Starting the for loop to store the inputs by spliting
 8. No of players
 9. Queue to store the names of the players
 10. creating a dice object
 
 + board b with starting point as "1" and ending point from the user , dice , snakes , ladders , and playerturn
 + b.game() starting the game.

### Library
 import java.util.*;
