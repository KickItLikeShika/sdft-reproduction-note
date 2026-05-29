# Reproducing Self-Distillation Fine-Tuning on Tool Use: A Running Report with a Released Model

## Abstract 
Self-Distillation Fine-Tuning (SDFT) was recently proposed as an on-policy distillation method in which a student model is trained on its own generations while matching a demonstration-conditioned teacher derived from the same model. Despite released code, several users reported difficulty reproducing the reported Tool Use results. In this note, we document a successful reproduction of SDFT on the released Tool Use split using Qwen2.5-7B-Instruct. We find that reproducing the result requires matching several implementation details that are easy to miss, including the use of per-token forward KL rather than the reverse KL suggested by the paper equation, the exact teacher-prompt construction, EMA teacher updates, skipped completion tokens, and the evaluation length. With these settings, our checkpoint reaches 70.1\% accuracy on the held-out Tool Use split, compared with 70.6\% reported by Shenfeld et al. and 42.2\% for the base model. We release the fine-tuned model, evaluation outputs, training logs, and the full configuration to provide a working reference point for future studies of SDFT.


## Artifacts
- HF Checkpoint: https://huggingface.co/KickItLikeShika/qwen-2.5-7b-instruct-sdft-tooluse
- W&B Report: https://api.wandb.ai/links/egyttsteam/d97ty5d9
