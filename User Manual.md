# Tic Tac Toe Game with AI - User Manual

# Overview

Welcome to the Tic Tac Toe Game with AI! This project allows you to play the classic Tic Tac Toe game against an artificial intelligence (AI) player. The AI player has been trained using Q-learning, making it a challenging opponent.

# Table of Contents

1.Installation
2.Game Rules
3.Starting the Game
4.Playing the Game
5.Training the AI Players
6.Viewing Training Progress

# Installation

To play the Tic Tac Toe game on your local machine, follow these steps:

1. Clone the repository:
git clone https://github.com/your-username/tic-tac-toe-ai.git
cd tic-tac-toe-ai

2. Run the main script:
python tic_tac_toe.py


# Game Rules

The Tic Tac Toe game is played on a 3x3 grid. Two players take turns marking a cell with their respective markers, "X" or "O." The player who successfully places three of their markers in a horizontal, vertical, or diagonal row wins the game. If all cells are filled, and no player has three in a row, the game is a tie.

# Starting the Game

When you run the script, the game will start automatically. You can choose to play against the AI player or watch two AI players compete against each other.

Playing the Game
If you choose to play against the AI player, follow these steps:

1.The board will be displayed, and it's your turn as "O."
2.Enter your move by providing the cell index (1-9) where you want to place your marker.
3.The AI player (X) will then make its move.
4.The game continues until a winner is determined or the game ends in a tie.

# Training the AI Players

The AI players can be trained to improve their performance. During training, two AI players compete against each other, and their strategies are updated based on the outcomes.

To train the AI players, run the following code in your Python environment:



```python
# Train AI players
ai_player_1 = AIPlayer()
ai_player_2 = AIPlayer()

# Set training parameters
TRAINING_EXAMPLES = 10000
TRAINING_EPSILON_1 = 0.2
TRAINING_EPSILON_2 = 0.3

# Training loop
for _ in range(TRAINING_EXAMPLES):
    game = TicTacToe(ai_player_1, ai_player_2)
    game.play()

print('Training is Done')
```

# Viewing Training Progress

To visualize the training progress, the cumulative rewards for both AI players can be plotted. After training, the AI player with exploration set to 0 (EPSILON = 0) can play optimally.


```python
# plot accumulated rewards for the two competing AI players
plt.subplots()
plt.plot(np.cumsum(ai_player_1.rewards))
plt.plot(np.cumsum(ai_player_2.rewards))
plt.xlabel('Training games')
plt.ylabel('Cumulative reward')
plt.title('Training progress')
plt.legend(['AI player 1','AI player 2'])

# plot accumulated rewards for the two competing AI players for the first 100 games
plt.subplots()
plt.plot(np.cumsum(ai_player_1.rewards[0:100]))
plt.plot(np.cumsum(ai_player_2.rewards[0:100]))
plt.xlabel('Training games')
plt.ylabel('Cumulative reward')
plt.title('Training progress for the first 100 games')
plt.legend(['AI player 1','AI player 2'])

plt.show()
```

Feel free to explore and enjoy playing Tic Tac Toe against the trained AI player!

For any issues or feedback, please refer to the GitHub repository and create an issue.

# Enjoy the game!
