# PCDARTS on jetson nano

## Usage
#### Search on CIFAR10

- First search the best cell on CIFAR10
- When finishing the search phase, you have to paste the mode in `genotypes.py`
```
python3 train_search.py
```

#### Evaluation on CIFAR10:

```
python3 train.py
       --arch the_architecture_that_you_search
       --model_path model_path.pt
```
#### Evaluation on CIFAR100:

```
python3 train.py
       --set cifar100
       --arch the_architecture_that_you_search
       --model_path model_path.pt
```


## Test on jetson nano
### Results on CIFAR10
Model | Accuracy(%) | Params(M) | FLOPS(M) | Latency(s) | Throughput
--- | --- | --- | --- | --- | ---
PCDARTS|2.8|2.55|3150
PCDARTS-1/4 | 3.3 | 3.00 | 0.4
PCDARTS-1/4-cut | 3.3 | 2.76 | 1.0

### Results on CIFAR100
Model | Accuracy(%) | Params(M) | FLOPS(M) | Latency(s) | Throughput
--- | --- | --- | --- | --- | ---
PCDARTS|2.8|2.55|3150
PCDARTS-1/4 | 3.3 | 3.00 | 0.4
PCDARTS-1/4-cut | 3.3 | 2.76 | 1.0


## FLOPS Caculation
Package [THOP](https://github.com/Lyken17/pytorch-OpCounter) is required to caculate the FLOPS of the model
```
pip3 install thop
```
```
python3 flops.py
       --arch the_architecture_that_you_search
       --model_path model_path.pt
```


## Visualization
Package [graphviz](https://graphviz.readthedocs.io/en/stable/index.html) is required to visualize the cells that you search
```
python3 visualize.py EXP
```
where `EXP` can be replaced by any architectures in `genotypes.py`.


## Reference
[PC-DARTS](https://github.com/yuhuixu1993/PC-DARTS)

[DARTS](https://github.com/quark0/darts)

[THOP: PyTorch-OpCounter](https://github.com/Lyken17/pytorch-OpCounter)
