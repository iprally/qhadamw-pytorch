# QHAdamW: Optimizer combining QHAdam and AdamW

This repository contains a PyTorch implementation of the QHAdamW optimizer. The optimizer combines the weight decay decoupling from AdamW ([Decoupled Weight Decay Regularization. Loshchilov and Hutter, 2019](https://arxiv.org/abs/1711.05101)) with QHAdam ([Quasi-hyperbolic momentum and Adam for deep learning. Ma and Yarats, 2019](https://arxiv.org/abs/1810.06801)).

The code is based on the PyTorch implementation of QHAdam found in the repository https://github.com/facebookresearch/qhoptim/.

Other implementations of AdamW in PyTorch:
* https://github.com/pytorch/pytorch/pull/4429
* https://github.com/egg-west/AdamW-pytorch

## Requirements

* Python >= 3.6
* PyTorch >= 1.0
