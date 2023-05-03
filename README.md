## pytorch-ddp-test
Just clone &amp; run this code to check, DDP env!

## Run Code
``` script
python -m torch.distributed.launch --nproc_per_node=4 main.py
```

### If you have a problem of infinite loading?

The issue of infinite loading with torch.distributed.barrier() can occur when the function is not able to complete the synchronization process.

This problem could potentially be caused by a backend issue. In this case, you can try changing the backend from `nccl` to `gloo` and see if that resolves the issue.

Please check line 270 in `main.py` and change `opts.dist_backend = 'nccl'` to `opts.dist_backend = 'gloo'`

### Reference
https://csm-kr.tistory.com/47
