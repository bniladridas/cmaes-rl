# CartPole CMA-ES Agent

A CMA-ES–based reinforcement learning agent for solving the classic `CartPole-v1` control problem using linear policy evolution—no neural networks involved.

  ### Video Preview

  https://github.com/user-attachments/assets/5761feb4-1c36-41a1-9b4f-4824a7742cac

## Model Overview

- **Algorithm:** CMA-ES (Covariance Matrix Adaptation Evolution Strategy)  
- **Environment:** CartPole-v1 (Gymnasium)  
- **Input:** 4D continuous state vector  
- **Output:** Discrete action (0 or 1)  
- **Policy:** Linear (state → action)  
- **Training:** 100 generations × population size 16  

## Performance

- **Mean Reward:** 500.00 ± 0.00  
- **Evaluation Episodes:** 10  
- **Max Score Achieved:** 500 (environment cap)

## Usage

```python
from model import CMAESAgent

# Load the pretrained agent
agent = CMAESAgent.from_pretrained("bniladridas/cartpole-cmaes")

# Evaluate on 5 episodes
mean, std = agent.evaluate(num_episodes=5)
print(f"Mean reward: {mean:.2f} ± {std:.2f}")
````

## Training Details

The model was trained with the CMA-ES optimizer, using a linear policy without gradient updates:

* **Generations:** 100
* **Population:** 16
* **Policy Type:** Deterministic, linear
* **Optimizer:** Evolutionary (CMA-ES)

No backpropagation, neural nets, or deep RL frameworks are used.

## Limitations

* Optimized for CartPole-v1 only
* Linear policy lacks complexity for general tasks
* Evaluation may vary slightly due to environment randomness

## Citation

```bibtex
@misc{cartpole-cmaes,
  author = {Niladri Das},
  title = {CartPole CMA-ES Agent},
  year = {2025},
  publisher = {Hugging Face},
  howpublished = {\url{https://huggingface.co/bniladridas/cartpole-cmaes}}
}
```

### Hugging Face Metadata (for reference)

*Not parsed by GitHub, but used on Hugging Face Hub.*

* **Language:** English
* **Tags:** reinforcement-learning, gymnasium, cartpole, cma-es
* **License:** MIT
* **Library:** custom
* **Dataset:** gymnasium/CartPole-v1
* **Metric:** Mean Reward = 500.00
