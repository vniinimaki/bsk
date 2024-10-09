# BSK
_BSK_ (_Bowling Score Keeper_) is an API that calculates the score of a bowling game. 

Each turn of a bowling game is called a frame. A (bowling) game consists of 10 frames. A game can have up to two bonus throws.

You do not need to know more so far. The _User Stories_ section will provide further details.

## Instructions for You
* FORK this project and make sure your forked repository is PUBLIC. Then, IMPORT the forked project into PyCharm.
* You are asked to develop _BSK_ by following TDD.
* You DO NOT need to develop a GUI.
* You CANNOT change the signature of the provided methods, move the provided methods to other classes, or change the name of the provided classes. However, you CAN add fields, methods (e.g., methods called by the provided methods), or even classes (including other test classes), as long as you comply with the provided API.
* You CAN use the internet to consult Python APIs or QA sites (e.g., StackOverflow).
* You CANNOT use AI tools (e.g., ChatGPT).
* You CANNOT interact with your colleagues. Work alone and do your best!
* The _BSK_ requirements are divided into a set of USER STORIES, which serve as a to-do list (see the _User Stories_ section).
* You should be able to incrementally develop _BSK_ without an upfront comprehension of all its requirements. DO NOT read ahead and handle the requirements (specified in the user stories) one at a time in the provided order. Develop _BSK_ by starting from the first story's requirement. When a story is IMPLEMENTED, move on to the NEXT one. A story is implemented when you are confident that your program correctly implements the functionality stipulated by the story's requirement. This implies that all your test cases for that story and all the test cases for the previous stories pass. You may need to review your program as you progress toward more advanced requirements.
* Each time you end a GREEN or REFACTOR phase, COMMIT.
* If you need to handle error situations (including situations unspecified by the user stories), throw a `BowlingError`.

## API Usage
Take some minutes to understand, in broad terms, how the API works. If you do not fully understand the API, do not worry because further details will be given later in the _User Stories_ section. A typical API usage follows.

```python
# Initialize an empty bowling game.
game = BowlingGame()
# Add 10 frames to the bowling game.
game.add_frame(Frame(1, 5))
game.add_frame(Frame(2, 5))
game.add_frame(Frame(1, 1))
game.add_frame(Frame(4, 2))
game.add_frame(Frame(8, 0))
game.add_frame(Frame(2, 3))
game.add_frame(Frame(1, 3))
game.add_frame(Frame(1, 6))
game.add_frame(Frame(2, 0))
game.add_frame(Frame(10, 0))
# Set the first bonus throw (if any).
game.set_first_bonus_throw(4)
# Set the second bonus throw (if any).
game.set_second_bonus_throw(5)
# Compute the score of the game.
score = game.calculate_score()
```

See the provided source files to improve your understanding of the API before starting to implement the user stories. 

## User Stories
Remember to read and implement the user stories once at a time (in the provided order). Therefore, do not read the next user story, if the current one is not implemented yet.

### User Story 1 -- Game
A single game consists of 10 frames.

**Requirement:**
* Implement `Game.__init__(self)` and `add_frame(self, frame: Frame) -> None` to define a game consisting of 10 frames.
* Implement `get_frame_at(self, i: int) -> Frame` to get the i-th frame of the game. Note that the index ranges from 0 to 9. This implies that 0 allows returning the first frame, 1 allows returning the second frame, and so on.
 
**Example:** The sequence of frames [1, 5] [3, 6] [7, 2] [3, 6] [4, 4] [5, 3] [3, 3] [4, 5] [8, 1] [2, 6] represents a game. [1, 5] is the first frame, [3, 6] is the second frame, and so on. Note that you can reuse this game from now on to represent different scenarios by modifying only a few frames each time.

