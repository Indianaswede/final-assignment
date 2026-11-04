# Bomberman World — Bomberman Escape

**Student:** Aifwen Stromblad

> Replace the prompts below and remove these instructions. Keep answers brief. Your implementation explanations and reflection belong in the presentation; you do not need to write them out here. Complete the final section only if seeking Pass with Distinction (VG).

## How to play

- **Controls:** Move with WASD or Arrow keys. Place a bomb with the spacebar. Press Q to quit the game. In a menu, press space to restart the game, and Q if you want to quit.
- **Objective and rules:** If you run out of health (which you can see as red pips in the top right corner), you die and thus lose. Get 500 points and get to the exit in the bottom right corner of the map to win!
- **Configurations / demo setup:** Press C to see turn off and on diagnostics. Press M to switch into the demo mode.

## Features and validation


| Feature | Check, observed result, and expected behaviour |
| --- | --- |
| 1. Player damage and death | I spent three rounds trying to die by running into enemies and getting caught in my bomb explosons, while occasionally running into boxes and bombs to ensure they didn't deal damage. Each time I took damage when it was expected (running into enemies and getting caught by explosions) and eventually lost every time. |
| 2. Round states and objective | I tried to win the game by destroying the enemies and then saw if the state would change suddenly from win to lose when I set a bomb near the exit that would kill me if the game updated. I was able to win and the game did not change from a lose to a win state, which is what's supposed to happen.  |
| 3. Safe restart | I restarted the game multiple times, seeing if there was an unexpected increase in entities and if there was anything that carried over that shouldn't have. I did not observe any irregularities, the map was different each time and the number of enemies stayed around 300 or so each time. This was expected. |
| 4. Solid bombs with owner escape | I set down bombs that I would stand in and let enemies run into them to see if they registered as solid. Then I would set down another, step off of it, and run back into it to see if I collided with it. The enemies acted accordingly and I found that if I stepped off of it, I would collide with it when I ran back. I did notice that sometimes I would place a bomb and I was already outside of it when it was placed, and thus I collided with it immediately.|
| 5. Blast-range pickup | I blew up multiple crates and enemies to see if the power up would spawn regularly. Then I would check the range of a bomb, drop a bomb and then collide with the power up to pick them up and checked that each one increased the range of the bomb explosion by one. I found the powerups spawned frequently enough and the blast range increase would only happen after I picked up the powerup, so long as I didn't place a bomb before (which would retain the old range). This is what was expected. |
| 8. Shield or Temporary Invulnerability | I ran into enemies and checked how long it would take them to kill me. They did not kill me instantly. I then tested various combinations of being caught in bomb explosions and running into multiple enemies to see if there was a way to take damage when I should e protected by the invincibility frames. I found that no damage would be taken until the invincibility frames ended. |
| 10. Exit or Progression Gate | I got to the gate to see if I could end the game before I got 500 points. I found that I could not do so. I then checked to see if it worked when I got 500 points. It did and I was able to get to the win state by doing so.|
| 11. Scoring and Combos | I tried killing multiple enemies in short succession, either by getting multiple in the same explosion or moving quickly to place a bomb shortly after the last one blew up. Each time, the combo score would go up and the timer would reset. My points increased appropriately, increasing initally by 10 and then increasing the points I got from killing an enemy by 5 per each subsequent kill as long as the combo timer ran out. |

**Known issues:** Sometimes enemies got caught in the wall or by the deft placement of a bomb and were stuck. Similarly, a bomb would be placed on a tile next to where most of the player was, sometimes even inside a crate. Perhaps improving the way enemies spawn and how bombs are placed could fix this.

## Sources and assistance

This project builds on the shared Kotte foundations.

Outside of Class Resources, I referred to the Raylib Documentation and the C++ documentation to remind myself of the algorithms and methods used.


<!-- Submission: commit and push this README with your source to GitHub or the internal Gitea server. Submit the final commit link and a runnable Release ZIP from that version in Studium. Ensure the teacher can access the repository throughout assessment. -->
