# Task 1 – Terminal Wordle (Easy)

Create a terminal-based clone of Wordle. Reference: [Original Wordle (NYT)](https://www.nytimes.com/games/wordle/index.html)

**Language:** Any language of your choice.

## Objectives

* The system picks a random secret word from a preset word library.
* The player has limited attempts (6 in the original) to guess it.
* Every guess must be a valid English word of the correct length (5 letters). Invalid guesses are rejected and do not use up an attempt.
* After each guess, the system guides the player with feedback for every letter:
  * Correct letter, correct position
  * Correct letter, wrong position
  * Letter not in the word
* Show feedback however you like: colors like the original, letters, numbers, symbols, or anything else that is clear.
* Handle repeated letters correctly (e.g. secret `CRANE`, guess `EERIE`).
* Show a win message, or reveal the word on a loss.

## Example

```
Secret: CRANE
Guess:  CARET
Feedback: C = correct, A = wrong position, R = wrong position, E = wrong position, T = absent
```

## Word Library Sources

* Community copies of the Wordle word lists on GitHub (search "wordle word list")
* [dwyl/english-words](https://github.com/dwyl/english-words) (filter to 5-letter words)
* Python `nltk` words corpus
* `/usr/share/dict/words` on Linux/Mac
* Or build a small list of your own

## Bonus

Don't just copy the original. Add some features of your own.

## Deliverables

* Correct game logic
* Error handling
* Bonus features
* User experience


---

# Task 2 – Themed Game (Medium)

Build a 2D game with a twist. Choose **one** of the two options below.

**Game engine / language:** Any of your choice (Unity, Godot, Pygame, GameMaker etc.).

## Option A – 3-Level Platformer

### Objectives

* Create a platformer with **3 levels**, each harder than the previous one.
* The player must be able to complete a level and unlock the next.
* Use **any two** of the following themes as core mechanics:
  * Unstable world
  * Time rewind
  * Light and dark
  * Shrinking
  * Teleportation
  * Blindness
* Difficulty should increase through level design and how the themes are used (not just more enemies or spikes).
* Include basic controls, a win condition, and a fail/restart condition.

## Option B – Endless Arcade

### Objectives

* Create an endless arcade game that runs until the player loses.
* Difficulty must **increase over time**.
* Include a **scoring system** (display the current score and the best score).
* Use **any two** of the following themes as core mechanics:
  * Rotation
  * Magic
  * Gravity flip
  * Time freeze
  * Slow motion
  * Colours
* Include basic controls, a game-over screen, and a way to restart.

## Notes

* Combine the two chosen themes in an interesting way rather than treating them as separate features.
* Keep the scope realistic. A small, polished game beats a large, unfinished one.
* Free assets are allowed, but credit your sources.

## Deliverables

* Gameplay
* Player experience
* Creative use of the themes
