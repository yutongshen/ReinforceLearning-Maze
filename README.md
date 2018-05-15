# Reinforce Learning Practice
Maze

## Prerequisite
- Python 3.6.4

## Install Dependency
```sh
$ pip install -r requirements.txt
```

## Usage
```sh
$ python usage: main.py [-h] [-l LENGTH] [-i ITERATION]
```

| optional Options           | Description                                    |
| ---                        | ---                                            |
| -h, --help                 | show this help message and exit                |
| -l LENGTH                  | input the length of the grid                   |
| -i ITERATION               | input the iteration of training                |


## Game Rules

\_ \_ \_ \* <- Destination, will get +1 reward <br>
\_ \_ \_ \_<br>
\_ \_ \_ \_<br>
o \_ \_ \_<br>
^<br>
Start Point<br>

We can choose 'up', 'down', 'left' and 'right' to approach destination

## Algorithm
- Q-Learning
  - Initialize Q-Table:

| state  | 'up'    | 'down'  | 'left'  | 'right' |
| ---    | ---:    | ---:    | ---:    | ---:    |
| (0, 0) |     0.0 |     0.0 |     0.0 |     0.0 |
| (0, 1) |     0.0 |     0.0 |     0.0 |     0.0 |
| (0, 2) |     0.0 |     0.0 |     0.0 |     0.0 |
| (0, 3) |     0.0 |     0.0 |     0.0 |     0.0 |
| (1, 0) |     0.0 |     0.0 |     0.0 |     0.0 |
| (1, 1) |     0.0 |     0.0 |     0.0 |     0.0 |
| (1, 2) |     0.0 |     0.0 |     0.0 |     0.0 |
| (1, 3) |     0.0 |     0.0 |     0.0 |     0.0 |
| (2, 0) |     0.0 |     0.0 |     0.0 |     0.0 |
| (2, 1) |     0.0 |     0.0 |     0.0 |     0.0 |
| (2, 2) |     0.0 |     0.0 |     0.0 |     0.0 |
| (2, 3) |     0.0 |     0.0 |     0.0 |     0.0 |
| (3, 0) |     0.0 |     0.0 |     0.0 |     0.0 |
| (3, 1) |     0.0 |     0.0 |     0.0 |     0.0 |
| (3, 2) |     0.0 |     0.0 |     0.0 |     0.0 |
| (3, 3) |     0.0 |     0.0 |     0.0 |     0.0 |

  - Initialize Enviroment and get current state, s
  - According to s, Actor will give an action: (ε-Greedy, e.g. ε = 0.9)
    - 10%: random choose one of 'up', 'down', 'left' or 'right'
    - 90%: choose the action with the highest Q-value
  - Take the action, and observe the reward, r, as well as the new state, s'.
  - Update the Q-table for the state using the observed reward and the maximum reward possible for the next state.
    - ${Q(s, a) = Q(s, a) + \alpha (r + \gammma max(Q(s', x)) - Q(s, a))}
  - Set the state to the new state, and repeat the process until a terminal state is reached.

## Related Link
- [nbviewer](https://nbviewer.jupyter.org/github/yutongshen/DSAI-HW3-Subtractor/blob/master/Subtractor.ipynb)

## Authors
[Yu-Tong Shen](https://github.com/yutongshen/)