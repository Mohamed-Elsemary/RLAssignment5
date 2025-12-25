# World Models for Space Invaders

This is a World Models agent trained on the `SpaceInvadersNoFrameskip-v4` environment.
Hugging Face Submission:https://huggingface.co/loayahmed123/world-models-spaceinvadersW
## Model Description

World Models is a model-based reinforcement learning approach that learns a compressed representation 
of the environment and trains a controller to maximize reward in the learned model.

The architecture consists of three components:
- **V (Vision)**: Variational Autoencoder that compresses 64x64 RGB frames to 32-dimensional latent vectors
- **M (Memory)**: MDN-RNN that predicts the next latent state given current state and action
- **C (Controller)**: Linear policy trained with CMA-ES evolution strategy

## Training Details

### Hyperparameters
- VAE Latent Dimension: 32
- RNN Hidden Dimension: 256
- Number of Gaussian Mixtures: 5
- Population Size (CMA-ES): 64
- Training Episodes: 100
- VAE Epochs: 10
- RNN Epochs: 20
- Controller Generations: 10

## Evaluation Results

- **Mean Reward**: 575.00 ± 0.00
- **Max Reward**: 575.00
- **Mean Episode Length**: 3235.00

## Usage

```python
import torch
import gymnasium as gym

# Load models
vae = VAE(latent_dim=32)
vae.load_state_dict(torch.load('vae_model.pt'))

rnn = MDNRNN(latent_dim=32, action_dim=6)
rnn.load_state_dict(torch.load('mdnrnn_model.pt'))

controller = Controller(latent_dim=32, hidden_dim=256)
controller.load_state_dict(torch.load('controller_model.pt'))

# Run agent
env = gym.make('SpaceInvadersNoFrameskip-v4')
# ... (see repository for full inference code)
```

## References

- Paper: [World Models (Ha & Schmidhuber, 2018)](https://worldmodels.github.io/)
- Code: Based on the original World Models implementation

## Citation

```bibtex
@article{ha2018worldmodels,
  title={World Models},
  author={Ha, David and Schmidhuber, J{\"u}rgen},
  journal={arXiv preprint arXiv:1803.10122},
  year={2018}
}
```
