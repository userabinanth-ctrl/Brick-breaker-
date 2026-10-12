# Brick Breaker Game (Java Swing)

A classic arcade Brick Breaker game written in Java using the Swing GUI toolkit.
This is a mini project for B.Sc. Multimedia & Web Technology, Nilgiri College of Arts
and Science (Autonomous), Thaloor.

**Author:** Abinanth Mohan (Register No: 25AH007)
**Guide:** Mr. Muhammad Savad N, M.Sc., (Ph.D.)., NET

## Description

The player controls a paddle at the bottom of the screen and bounces a ball upwards to
break all the bricks. The ball changes direction depending on where it touches the
paddle, and it gets slightly faster as bricks are destroyed and as levels increase.

### Features

- Main menu (Play, Instructions, Exit) and an instructions screen
- Three levels with different brick layouts (40, 48 and 58 bricks)
- Normal bricks (1 hit, 10 points), strong bricks (2 hits, 25 points) and bonus bricks
  (50 points and an extra life)
- Score, lives (3 at the start), level and best score display
- Win and game-over screens, pause, restart and exit
- Keyboard and mouse control
- High score saved in `highscore.txt` (file handling with exception handling)

### Controls

| Key / action              | What it does                 |
|---------------------------|------------------------------|
| LEFT / RIGHT or A / D     | Move the paddle              |
| Mouse                     | Move the paddle              |
| SPACE or mouse click      | Launch the ball / resume     |
| P                         | Pause                        |
| R                         | Restart                      |
| ESC                       | Back to the menu             |

## Java concepts used

Classes and objects, constructors, encapsulation, abstract classes (`GameObject`, `Brick`),
inheritance, polymorphism (`hit()`, `draw()`, `getColor()`), `ArrayList`, enumeration
(`State`), exception handling, file handling (`java.nio.file`), Swing / AWT, and
event handling with listeners and lambda expressions.

## Project structure

```
BrickBreaker/
  src/brickbreaker/
    Main.java               - window and screen switching (CardLayout)
    MenuPanel.java          - main menu
    InstructionsPanel.java  - how to play
    GamePanel.java          - game loop, collisions, scoring
    GameObject.java         - abstract base class
    Paddle.java, Ball.java
    Brick.java              - abstract brick
    NormalBrick.java, StrongBrick.java, BonusBrick.java
    HighScoreManager.java   - file handling
  test/GameTest.java        - automated tests (also creates the screenshots)
  screenshots/              - images used in the report
  README.md, run.sh, run.bat
```

## How to compile and run

Requirements: JDK 17 or later (`java -version` to check). No external libraries are needed.

```
mkdir out
javac -d out src/brickbreaker/*.java
java -cp out brickbreaker.Main
```

Or simply double-click `run.bat` (Windows) or run `./run.sh` (Linux / macOS).

## How to run the tests

```
mkdir out
javac -d out src/brickbreaker/*.java test/GameTest.java
java -Djava.awt.headless=true -cp out brickbreaker.GameTest
```

The test plays the game automatically without opening a window, prints the result of each
test case and regenerates the screenshots in the `screenshots/` folder.
