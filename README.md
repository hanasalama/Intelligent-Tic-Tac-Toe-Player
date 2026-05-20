# Intelligent-Tic-Tac-Toe-Player

A desktop-based Tic-Tac-Toe game developed in Python that features an intelligent AI opponent. Instead of relying on random move generation, this AI agent analyzes the current state of the board, predicts future moves, and makes strategic decisions to maximize its chances of winning or force a draw. 

The project demonstrates practical applications of Artificial Intelligence in game development, specifically state-space search and decision-making optimization.

---

##  Features

* **Human vs. AI Gameplay:** Users can interact with the game through mouse clicks to compete against the computer.
* **Multiple Difficulty Levels:** Supports multiple AI difficulty modes.
    * **Easy:** Makes random moves.
    * **Medium:** Uses basic heuristic evaluation.
    * **Hard:** Plays optimally using the Minimax algorithm combined with Alpha-Beta pruning.
* **Interactive GUI:** Built with a user-friendly interface that includes real-time feedback, move viewing, and a toggle to switch between heuristic modes.
* **Aesthetic Design:** Features a consistent pink color palette, including the background (#ffc0cb), tiles (#ffb6c1), and distinct player colors.
* **Game Management:** Supports real-time turn management, win/lose/draw detection, and replay functionality without closing the application.

---

##  Technology Stack

* **Language:** Python.
* **GUI Framework:** Tkinter.
* **Libraries:** NumPy (matrix operations), Random (generating random moves in easy mode), Time (measuring execution time and delays), and Math (mathematical calculations).
* **Development Environment:** Visual Studio Code (VS Code).

---

##  How the AI Works

The intelligence of the hard-mode AI relies on a combination of search algorithms and optimizations to guarantee the best possible move without wasting computational resources.

### 1. Minimax Algorithm
The system builds a game tree containing all possible moves, future game states, and final outcomes. The AI acts as the "MAX" player trying to maximize the score, while treating the human as the "MIN" player trying to minimize the score. It evaluates every state until it reaches a terminal outcome (Win, Lose, Draw).

### 2. Alpha-Beta Pruning
To improve efficiency, the AI uses Alpha-Beta Pruning to eliminate unnecessary branches in the search tree. By tracking the best maximum score found so far ($\alpha$) and the best minimum score found so far ($\beta$), the algorithm stops exploring a branch if $\alpha \ge \beta$, as it cannot influence the final decision.

### 3. Symmetry Reduction Engine
A $3\times3$ Tic-Tac-Toe board has 8-way symmetry based on the D4 Dihedral Group. The AI generates all 8 symmetrical transformations (rotations and reflections) for every board state. By tracking previously seen states, the system avoids redundant calculations, reducing the search space by approximately 85-90% in the early game.

### 4. Heuristic Evaluation
When the search depth limit is reached, the AI uses heuristic functions to estimate the quality of the board instead of continuing the full search. 
* **Basic Heuristic:** Scores +10 if the AI is close to winning (2 marks and 1 empty space) and -10 if the human is close to winning.
* **Advanced Heuristic:** Evaluates medium positions (scoring +3 or -3) and considers strategic advantages like center and corner control.
