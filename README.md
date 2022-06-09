![PyTorch](https://img.shields.io/badge/PyTorch-%3D1.9.1-informational)
![Python](https://img.shields.io/badge/Python-%3E%3D3.8-blue)
# Meta-Pseudo-Labels
practise

## Debug..
> `RuntimeError: "nll_loss_forward_reduce_cuda_kernel_2d_index" not implemented for 'Int'`
- in `main.py` line 179: add `targets = targets.to(torch.int64)` before `t_loss_l = criterion(t_logits_l, targets)`
- in `main.py` line 405: add `targets = targets.to(torch.int64)` before `loss = criterion(outputs, targets)`
