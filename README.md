# Intelligent-Tic-Tac-Toe-Player
[cite_start]A desktop-based Tic-Tac-Toe game developed in Python that features an intelligent AI opponent[cite: 11, 22]. [cite_start]Instead of relying on random move generation, this AI agent analyzes the current state of the board, predicts future moves, and makes strategic decisions to maximize its chances of winning or force a draw[cite: 12, 13]. 

[cite_start]The project demonstrates practical applications of Artificial Intelligence in game development, specifically state-space search and decision-making optimization[cite: 14, 123].

---

##  Features

* [cite_start]**Human vs. AI Gameplay:** Users can interact with the game through mouse clicks to compete against the computer[cite: 23, 26, 37].
* [cite_start]**Multiple Difficulty Levels:** Supports multiple AI difficulty modes[cite: 51, 52].
    * [cite_start]**Easy:** Makes random moves[cite: 53].
    * [cite_start]**Medium:** Uses basic heuristic evaluation[cite: 54, 55].
    * [cite_start]**Hard:** Plays optimally using the Minimax algorithm combined with Alpha-Beta pruning[cite: 56].
* [cite_start]**Interactive GUI:** Built with a user-friendly interface that includes real-time feedback, move viewing, and a toggle to switch between heuristic modes[cite: 65, 67, 71, 263].
* [cite_start]**Aesthetic Design:** Features a consistent pink color palette, including the background (#ffc0cb), tiles (#ffb6c1), and distinct player colors[cite: 264, 265, 266, 267].
* [cite_start]**Game Management:** Supports real-time turn management, win/lose/draw detection, and replay functionality without closing the application[cite: 42, 47, 70].

---

##  Technology Stack

* [cite_start]**Language:** Python[cite: 11, 22].
* [cite_start]**GUI Framework:** Tkinter[cite: 248].
* [cite_start]**Libraries:** NumPy (matrix operations), Random (generating random moves in easy mode), Time (measuring execution time and delays), and Math (mathematical calculations)[cite: 248].
* [cite_start]**Development Environment:** Visual Studio Code (VS Code)[cite: 246].

---

##  How the AI Works

[cite_start]The intelligence of the hard-mode AI relies on a combination of search algorithms and optimizations to guarantee the best possible move without wasting computational resources[cite: 288, 290].

### 1. Minimax Algorithm
[cite_start]The system builds a game tree containing all possible moves, future game states, and final outcomes[cite: 137, 138, 139, 140]. [cite_start]The AI acts as the "MAX" player trying to maximize the score, while treating the human as the "MIN" player trying to minimize the score[cite: 133, 134, 142, 143]. [cite_start]It evaluates every state until it reaches a terminal outcome (Win, Lose, Draw) with a time complexity of $O(b^d)$[cite: 144, 145, 155].

### 2. Alpha-Beta Pruning
[cite_start]To improve efficiency, the AI uses Alpha-Beta Pruning to eliminate unnecessary branches in the search tree[cite: 159, 288]. [cite_start]By tracking the best maximum score found so far ($\alpha$) and the best minimum score found so far ($\beta$), the algorithm stops exploring a branch if $\alpha \ge \beta$, as it cannot influence the final decision[cite: 160, 163, 166, 168].

### 3. Symmetry Reduction Engine
[cite_start]A $3\times3$ Tic-Tac-Toe board has 8-way symmetry based on the D4 Dihedral Group[cite: 346]. [cite_start]The AI generates all 8 symmetrical transformations (rotations and reflections) for every board state[cite: 347, 348, 349]. [cite_start]By tracking previously seen states, the system avoids redundant calculations, reducing the search space by approximately 85-90% in the early game[cite: 353, 356, 365].

### 4. Heuristic Evaluation
[cite_start]When the search depth limit is reached, the AI uses heuristic functions to estimate the quality of the board instead of continuing the full search[cite: 180, 287]. 
* [cite_start]**Basic Heuristic:** Scores +10 if the AI is close to winning (2 marks and 1 empty space) and -10 if the human is close to winning[cite: 321, 324, 325].
* [cite_start]**Advanced Heuristic:** Evaluates medium positions (scoring +3 or -3) and considers strategic advantages like center and corner control[cite: 198, 337, 338, 339].
