# PathfinderRL: Reinforcement Learning Grid World

## Overview

PathfinderRL demonstrates the use of Reinforcement Learning (RL) to solve a navigational task within a "Lawnmower Grid World." This environment consists of a 4x4 grid with 16 states. The goal is to navigate from the top-left corner to the bottom-right corner while maximizing rewards and avoiding penalties. The agent collects batteries (positive rewards) and avoids pebbles (negative rewards) to reach the goal.

![Grid World](https://github.com/swamilalit/PathfinderRL/data/agent_env.png)

## Environment Setup

- **States:** Represented as tuples for the row and column indices on a 4x4 grid, from (0, 0) to (3, 3).
- **Actions:** The agent can move Up, Down, Right, or Left.
- **Rewards:** 
  - **Rocks:** Negative rewards (-5, -6)
  - **Batteries:** Positive rewards (+5, +6)
  - **Goal State:** Highest reward (+10)
- **Objective:** Navigate to the goal state (3, 3) while maximizing the total rewards.

## Visualization

The environment is visualized using Matplotlib:

- **Grid Cells:** Color-coded to show positive (warmer colors) and negative (cooler colors) rewards.
- **Goal State:** Highlighted in red.
- **Agent Position:** Marked to show the current position on the grid.

![Visualization](https://github.com/swamilalit/PathfinderRL/data/env_visualization.png)

## Algorithms Implemented

### SARSA (State-Action-Reward-State-Action)

- **Approach:** On-policy learning where the agent learns from actions based on the current policy.
- **Update Formula:** 
  \[
  Q(s, a) = Q(s, a) + \alpha \left(r + \gamma \cdot Q(s', a') - Q(s, a)\right)
  \]
  Parameters: learning rate (\(\alpha\)), reward (\(r\)), discount factor (\(\gamma\)), and Q-values of the current and next state-action pairs.
- **Features:** Balances exploration and exploitation through direct experiences.

### Q-Learning

- **Approach:** Off-policy algorithm that finds the optimal policy indirectly using the greedy method.
- **Update Formula:** 
  \[
  Q(s, a) = Q(s, a) + \alpha \left(r + \gamma \cdot \max(Q(s', a')) - Q(s, a)\right)
  \]
- **Features:** Robust in large state spaces, though it may overestimate Q-values due to its maximization step.

## Getting Started

To explore the project, run the Jupyter notebook provided in the `notebooks/` directory. The notebook includes detailed implementations of SARSA and Q-Learning algorithms along with visualizations of the grid world.

## Contributing

Feel free to fork the repository and submit pull requests. Contributions, bug reports, and feature requests are welcome!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

