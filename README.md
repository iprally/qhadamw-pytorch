# QHAdamW: Optimizer combining QHAdam and AdamW

This repository contains a PyTorch implementation of the QHAdamW optimizer. The optimizer combines the weight decay decoupling from AdamW ([Decoupled Weight Decay Regularization. Loshchilov and Hutter, 2019](https://arxiv.org/abs/1711.05101)) with QHAdam ([Quasi-hyperbolic momentum and Adam for deep learning. Ma and Yarats, 2019](https://arxiv.org/abs/1810.06801)).

The code is based on the PyTorch implementation of QHAdam found in the repository https://github.com/facebookresearch/qhoptim/.

Other implementations of AdamW in PyTorch:
* https://github.com/pytorch/pytorch/pull/4429
* https://github.com/egg-west/AdamW-pytorch

## Usage

QHAdamW serves as a drop-in replacement for Adam/QHAdam/AdamW. Note that you might need to tune your weight decay value when switching from Adam/QHAdam to QHAdamW. In case the weight decay is zero QHAdamW equals QHAdam. QHAdam/QHAdamW has, in addition to the hyperparameters in Adam, additional hyperparameters (nus), which control the discount factors used to estimate the gradient and its square.

As mentioned in [Loschilov et al.](https://arxiv.org/abs/1711.05101) (page 6) when using AdamW/QHAdamW you may do parameter sweeps for the learning rate and the weight decay independently. Note that the optimal weight decay value will depend on the batch size and the amount of epochs you use ([Loschilov et al.](https://arxiv.org/abs/1711.05101), Appendix B.1). It might make sense to scale the weight decay by the square root (or linearly) with the batch size (in the same manner as you would scale the learning rate).

## Requirements

* Python >= 3.6
* PyTorch >= 1.0
