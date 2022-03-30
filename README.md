# Meta-Pseudo-Labels
practise

## Debug..
> `RuntimeError: "nll_loss_forward_reduce_cuda_kernel_2d_index" not implemented for 'Int'`
- in `main.py` line 179: add `targets = targets.to(torch.int64)` before `t_loss_l = criterion(t_logits_l, targets)`
