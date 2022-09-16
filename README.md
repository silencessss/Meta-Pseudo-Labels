![PyTorch](https://img.shields.io/badge/PyTorch-%3D1.9.1-informational)
![Python](https://img.shields.io/badge/Python-%3E%3D3.8-blue)
# Meta-Pseudo-Labels
A semi-supervised learning method. Paper online link is here: https://arxiv.org/abs/2003.10580

## USAGE
```basch
python main.py --seed 2 --name AcneECK --expand-labels --dataset AcneECK --num-classes 4 --num-labeled 460 --total-steps 300000 --eval-step 1000 --randaug 2 16 --batch-size 128 --teacher_lr 0.05 --student_lr 0.05 --weight-decay 5e-4 --ema 0.995 --nesterov --mu 7 --label-smoothing 0.15 --temperature 0.7 --threshold 0.6 --lambda-u 8 --warmup-steps 5000 --uda-steps 5000 --student-wait-steps 3000 --teacher-dropout 0.2 --student-dropout 0.2 --finetune-epochs 625 --finetune-batch-size 512 --finetune-lr 3e-5 --finetune-weight-decay 0 --finetune-momentum 0.9 --amp
```





## Debug..
> `RuntimeError: "nll_loss_forward_reduce_cuda_kernel_2d_index" not implemented for 'Int'`
- in `main.py` line 179: add `targets = targets.to(torch.int64)` before `t_loss_l = criterion(t_logits_l, targets)`
- in `main.py` line 405: add `targets = targets.to(torch.int64)` before `loss = criterion(outputs, targets)`


---

## Ref.
- https://github.com/kekmodel/MPL-pytorch
- https://github.com/google-research/google-research/tree/master/meta_pseudo_labels
