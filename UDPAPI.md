Welcome to the API of the Drone Roots of knowledge game.


Default port:
2509 : Server port to play the game
2508 : Respond of server port with game info


## You can send
- "rc leftright backfront rotateleftright downtop" // Will allows you to move the drone in the game
- "rcf aabbccdd" // will allows you to move the drone in the game with one float. 
- multi 1 rc 0 0 0 0 // If the server allows it. It allows creation of several drone by IP address

- "name:Eloi"  // Will define your name as Eloi. 
- "color:ff0000"  // Will define your drone as red.
- "I want to observe"  // Will register you as observer and sent you information about the game. 
- "exit" //You notify that you leave the game.


## You can receive

```
string.Format("Y✈|{0} {1} {2} {3} {4} {5} {6} {7} {8}|{9}",
                   playerDrone.localPosition.x, 
                   playerDrone.localPosition.y,
                   playerDrone.localPosition.z,
                   0f, // mm of position estimation  0 mm = exact 80 mm around 8cm around this point. 
                   playerDrone.localRotation.x,
                   playerDrone.localRotation.y,
                   playerDrone.localRotation.z,
                   playerDrone.localRotation.w,
                   0f, // angle in ° of estimation of direction in Quaternion 0= exact and 180 we don't know at all
                   time);
```
```
string.Format("✈|{0} {1} {2} {3} {4} {5} {6} {7} {8}|{9}",
                   playerDrone.localPosition.x, 
                   playerDrone.localPosition.y,
                   playerDrone.localPosition.z,
                   0f, // mm of position estimation  0 mm = exact 80 mm around 8cm around this point. 
                   playerDrone.localRotation.x,
                   playerDrone.localRotation.y,
                   playerDrone.localRotation.z,
                   playerDrone.localRotation.w,
                   0f, // angle in ° of estimation of direction in Quaternion 0= exact and 180 we don't know at all
                   time);
```
With default mode precision is always exacte but to prepare the game to be able to be played by real drone for tournament.
You can ask the teacher to have less precise feedback.  Contact us for details. 
The idea: the game is suppose to train you pilote drone in XR and then be able to do the same in real life with random drone.
As the captor that will send drone information are not precise at all and can't know who is who. The game can be set in "real mode"
Meaning that you have an estimatoin based on the sensor and you can also don't know what drone is your.
