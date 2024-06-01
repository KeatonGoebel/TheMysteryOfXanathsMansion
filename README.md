# TheMysteryOfXanathsMansion

Link to the game: https://cloudfin.itch.io/the-mystery-of-xanaths-mansion

The Mystery of Xanath's Mansion is a computer game made over four weeks for a game design course at Transylvania University. 
It was a group project I made alongside three other people implementing an agile development strategy. 
The logic of the game was developed using the game engine Godot while the art was made using the program Aseprite.
I worked on the level design of the game, designing the structure of the mansion and the layout of its 14 rooms. I also contributed a significant amount of the code of the game. At one point I refactored several parts of the to make things permanent where they were not before.
In the game, the player is a young wizard who comes to a mansion in search of magical tutelage, but finds it abandoned. 
They are then tasked with uncovering the mystery of what happened to each of the residents of the mansion, unlocking new abilities, and defeating enemies.
The game was designed to have an open structure. The player can run straight to the final boss immediately and beat the game in a couple minutes. However, they will have a much easier time if they spend more time in the game exploring and solving the puzzles in the environment. The puzzles unlock additional abilities, giving them both offensive and defensive spells. This design philosophy makes it so that we do not overwhelm the player by giving them all their abilities at the start, while also rewarding them for their exploration. It also gives the player the freedom to engage with the game in different ways. Some players will try to beat the game as fast as possible, while some will want to explore the game as much as possible. 

## Playing The Game

Xanath's Mansion is designed to be played on the computer with the mouse and keyboard. It was designed with a 2D perspective in mind where you will be moving primarily left and right with some vertical platformer challenges. Another important aspect of playing the game is the lighting system. We did not want to have health bars cluttering the screen. Therefore in order to represent the health of the player, we have a light orb that follows the player. This orb becomes visually cracked and grows more as the player loses health. Therefore the game becomes more dark as the player takes damage. This design decision provides immediate feedback upon taking damage. In order to keep it from being too punishing, we made sure to add in a healing ability to balance the game. 

**Controls:**
- WSAD and the Arrow Keys move the main character, while W and Up are used to Jump
- Space bar can also be used to jump
- The player uses their light ball by pointing and clicking with a mouse or a trackpad
- The player uses their other abilities with 1,2,3,4,5
- The player can open their spell book to see what spells they currently possess with I
- The player can pause the game with 

<details>
  <summary>Click here to see the puzzle solutions</summary>
  
  **Puzzle Solutions:** 
  - Pick up the staff in the Entryway to unlock light ball
  - Interact with the statue in the Lobby to unlock healing rain
  - Shooting the fireplace in the Parlor with a light ball will light the fireplace and unlock fireball
  - Using healing rain on the furnace in the kitchen will put out the furnace and unlock starbeam
  - Using fireball or starbeam on the moon in the green house will unlock levitate
  - Defeating the first giant plant in the green house will unlock phase
  
</details>

## Xanath Mansion Screenshots 

<a href="https://cloudfin.itch.io/the-mystery-of-xanaths-mansion">
  <img src="https://github.com/KeatonGoebel/TheMysteryOfXanathsMansion/assets/155006422/4214697f-5000-4cb4-a19e-0fdf3c88ec9a" width="800" height="600" alt="The Mystery of Xanath's Mansion">
</a>

<a href="https://cloudfin.itch.io/the-mystery-of-xanaths-mansion">
  <img src="https://github.com/KeatonGoebel/TheMysteryOfXanathsMansion/assets/155006422/7f2c7539-4e58-4644-8d1f-43d0036253fe" width="800" height="auto" alt="WxdBXR">
</a>

<a href="https://cloudfin.itch.io/the-mystery-of-xanaths-mansion">
  <img src="https://github.com/KeatonGoebel/TheMysteryOfXanathsMansion/assets/155006422/026b5060-16ff-485d-b1d5-ca4c428c0891" width="800" height="auto" alt="nkDKu5">
</a>

<a href="https://cloudfin.itch.io/the-mystery-of-xanaths-mansion">
  <img src="https://github.com/KeatonGoebel/TheMysteryOfXanathsMansion/assets/155006422/012c2571-134f-41dd-88ec-aa7bd58abd87" width="800" height="auto" alt="iROUYA">
</a>

<a href="https://cloudfin.itch.io/the-mystery-of-xanaths-mansion">
  <img src="https://github.com/KeatonGoebel/TheMysteryOfXanathsMansion/assets/155006422/64a28601-d144-438e-9762-24de25a3ee1e" width="800" height="auto" alt="wVslFy">
</a>


### Developing the Game

I spend nearly half of the total development time on the environment and level design, coming up with the structure for the mansion and the design of the 14 rooms. The structural design of the mansion maintains a contrast between realistic and fantastical. I decided I needed to place bathrooms on each floor, and believable connectors between each floor. At the same time, there is a giant wizard tower leading to Xanath. Making sure to maintain the magical elements of the mansion allows our audience to more easily suspend their disbelief. Players breaking their suspension of belief when seeing the platforms floating in the air is also less likely because platforms are often blended into the environment using props. Chandlers are hung from the bottom of the platforms in the dining room to make the platforms seem less out of place. A flight of stairs is placed on the top platform in the parlor to make it seem as if the player is climbing up the stairs by jumping up the platforms. In order to build these rooms, I leveraged tile maps in Godot. Tile maps are a way that Godot can organize your sprites into a set of tiles which you can map onto the level. These were so helpful because once we created sprites that could act as backgrounds and walls, we could easily start building rooms. Godot also allows us to place collision layers onto tiles which. Tile maps allowed us to start creating rooms of different sizes and shapes quickly. 

Another big contribution I made to the project was the permanence of data. We had a problem through much of development where if the player went from one room to another, things like their health, the enemies, and their abilities would all reset. This bug was because every time the player entered a new room, the game would create new instances of the scene, resetting the values of the data. In order to fix this problem, I researched how Godot handles global information. I refactored a significant amount of code, writing it into singleton auto-loaded scripts. Singletons are scripts that are automatically loaded every time the game starts. Things such as player health, ability information, and enemy information all had to exist in a singleton so it would have global scope. Therefore if the player killed an enemy the enemy would now be permanently defeated. This also allowed me to make several improvements. 
