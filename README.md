# Snake AI Q-Learning 🐍

A sophisticated implementation of a Snake game AI that utilizes Deep Q-Learning to master gameplay autonomously. This project demonstrates the practical application of reinforcement learning in game environments, showcasing how an AI agent can learn complex strategies through experience.

![Snake AI Demo]((https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExd25qM2VmY3Q0M3NhNnJxdjMzaWRmMTMzamFyeGtiZzNkNWsxanI1MCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/AOAopvXMNeiBaAQfqy/giphy.gif))

## 🌟 Features

- 🎮 Classic Snake game built with Pygame
- 🧠 Deep Q-Learning implementation with PyTorch
- 📈 Real-time visualization of training progress
- 💾 Automatic saving of best models
- 🎯 High score tracking

## 🔧 Technical Requirements

### Core Dependencies
- Python 3.13.1
- PyTorch 2.9.0
  - torchvision 0.24.0
  - torchaudio 2.9.0
- Pygame 2.6.1 (SDL 2.28.4)
- Matplotlib 3.10.7
- NumPy 2.3.4
- IPython 9.6.0

### Additional Dependencies
- filelock 3.20.0
- fsspec 2025.10.0
- jinja2 3.1.6
- networkx 3.5
- pillow 12.0.0
- typing-extensions 4.15.0
- MarkupSafe 3.0.3
- sympy 1.14.0
- contourpy 1.3.3
- cycler 0.12.1
- fonttools 4.60.1
- kiwisolver 1.4.9
- packaging 25.0
- pyparsing 3.2.5
- python-dateutil 2.9.0
- six 1.17.0

## 🚀 Quick Start

1. Clone the repository:
```bash
git clone https://github.com/Antwa-sensei253/Snake_AI_Q-learning.git
cd Snake_AI_Q-learning
```

2. Create and activate a virtual environment:
```bash
python -m venv .venv
# On Windows:
.\.venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install torch torchvision torchaudio
pip install pygame numpy matplotlib
```

4. Run the training:
```bash
python agent.py
```

## 🎮 Game Environment

The game environment (`game.py`) is built with Pygame and includes:
- Classic snake movement mechanics
- Food spawning system
- Collision detection
- Score tracking
- FPS control

## 🤖 AI Agent

The AI agent (`agent.py`) uses Deep Q-Learning with:
- 11 input state features:
  - Danger detection in 3 directions
  - Current movement direction (4 values)
  - Food location relative to snake head (4 values)
- 3 possible actions:
  - [1,0,0] → Go straight
  - [0,1,0] → Turn right
  - [0,0,1] → Turn left

## 🧮 Neural Network

The model (`model.py`) architecture:
```
Input Layer (11) → Hidden Layer (256) → Output Layer (3)
```

## 💡 Training Process

- Experience replay with memory size of 100,000
- Epsilon-greedy exploration strategy
- Reward system:
  - Eating food: +10 points
  - Game over: -10 points
  - Survival: 0 points

## 📊 Performance Tracking

- Terminal output shows:
  - Current game number
  - Score
  - Record score
- Real-time plot displays:
  - Individual game scores
  - Moving average score

## 📁 Project Structure

```
Snake_AI_Q-learning/
├── agent.py     # AI agent and training loop
├── game.py      # Snake game environment
├── model.py     # Neural network architecture
├── plot.py      # Training visualization
└── model/       # Saved model weights
```

## ⚙️ Configuration

Key parameters in `agent.py`:
```python
MAX_MEMORY = 100_000
BATCH_SIZE = 1000
LR = 0.001
```

## 🤝 Contributing

Contributions are welcome! Feel free to:
1. Fork the repository
2. Create a feature branch
3. Submit a pull request

## 📝 License

This project is open source and available under the MIT License.

## 🙏 Acknowledgments

Special thanks to:
- PyTorch team for the deep learning framework
- Pygame community for the game development library
