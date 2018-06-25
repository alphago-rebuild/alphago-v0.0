# alphago-v0.0
play with it first

Timeline:
follow the tutorial of building alphago in 28 days
6/25: Finished Day1, get to know the rule of go and basic concept of monte carlo tree and game tree

复现AlphaGo
- Tech stack
  - Deep Learning (e.g. Pytorch/TensorFlow/MXNet)
  - Python
- Link
  - AlphaGo paper https://pdfs.semanticscholar.org/1740/eb993cc8ca81f1e46ddaadce1f917e8000b5.pdf
  - 28 天自制你的 AlphaGo (1) : 围棋 AI 基础 https://zhuanlan.zhihu.com/p/24801451
  - Facebook Research: https://github.com/pytorch/ELF
  - alpha go原理 Monte Carlo tree: https://en.wikipedia.org/wiki/Monte_Carlo_tree_search
- Ideas
  - 在有限计算资源（CPU、少量GPU）下复现AlphaGo AI模型
  - 在野狐等围棋平台上测试棋力

Elements:
1. MCTS（蒙特卡洛树搜索）
2. CNN （卷积神经网络，包括：策略网络 policy network、快速走子网络 playout network、价值网络 value network）
3. RL （强化学习）

Follow the rule: Tromp-Taylor Rules
https://senseis.xmp.net/?TrompTaylorRules
1. Go is played on a 19x19 square grid of points, by two players called Black and White.
2. Each point on the grid may be colored black, white or empty.
3. A point P, not colored C, is said to reach C, if there is a path of (vertically or horizontally) adjacent points of P's color from P to a point of color C.
4. Clearing a color is the process of emptying all points of that color that don't reach empty.
5. Starting with an empty grid, the players alternate turns, starting with Black.
6. A turn is either a pass; or a move that doesn't repeat an earlier grid coloring.
7. A move consists of coloring an empty point one's own color; then clearing the opponent color, and then clearing one's own color.
8. The game ends after two consecutive passes.
9. A player's score is the number of points of her color, plus the number of empty points that reach only her color.
10. The player with the higher score at the end of the game is the winner. Equal scores result in a tie.