# Snake AI Q-learning

A Snake game AI that uses Q-learning reinforcement learning algorithm to teach itself how to play the classic Snake game.

## Overview

This project implements a Snake game environment and trains an AI agent using Q-learning, a model-free reinforcement learning technique. The agent learns to navigate the game environment, collect food, and avoid collisions through trial and error.

## Features

- Classic Snake game implementation
- Q-learning reinforcement learning algorithm
- Visualization of the game and learning progress
- Customizable learning parameters
- Ability to save and load trained models

## Requirements

- Python 3.6+
- Pygame
- NumPy
- Matplotlib (for visualization)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/Antwa-sensei253/Snake_AI_Q-learning.git
cd Snake_AI_Q-learning
```

2. Install the required dependencies:
```bash
pip install -r requirements.txt
```

## Usage

### Training the AI

To start training the Snake AI from scratch:

```bash
python train.py
```

You can modify the learning parameters in the script or use command line arguments:

```bash
python train.py --episodes 1000 --epsilon 0.1 --gamma 0.9 --learning_rate 0.1
```

### Testing a trained model

To watch the trained AI play the game:

```bash
python play.py --model saved_model.pkl
```

## How It Works

### Q-Learning

The Q-learning algorithm works by maintaining a Q-table that maps state-action pairs to expected rewards. In this implementation:

- **State**: Represented by the snake's relative position to food and obstacles
- **Actions**: Move up, down, left, or right
- **Reward**: Positive for eating food, negative for collisions

The AI learns through a process of exploration (trying random actions) and exploitation (using known good actions) to maximize its score.

### The Learning Process

1. Initialize Q-table with zeros
2. For each episode:
   - Reset the game environment
   - Until game over:
     - Choose an action (random or based on Q-table)
     - Perform the action and observe reward and new state
     - Update Q-value using the formula:
       Q(s,a) = Q(s,a) + α * [r + γ * max(Q(s',a')) - Q(s,a)]
     - Update state to new state

## Project Structure

```
Snake_AI_Q-learning/
├── game.py              # Snake game implementation
├── agent.py             # Q-learning agent
├── train.py             # Training script
├── play.py              # Script to watch trained agent
├── models/              # Saved model files
├── utils/               # Utility functions
└── visualizations/      # Performance graphs and visualizations
```

## Customization

You can adjust various parameters to experiment with the learning process:

- **Learning rate**: Controls how much new information overrides old information
- **Discount factor**: Determines the importance of future rewards
- **Exploration rate**: Controls the trade-off between exploration and exploitation
- **Reward structure**: Modify the rewards for different game events

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Inspired by various reinforcement learning tutorials and papers
- Snake game implementation based on pygame examples
