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
```
#### Evaluation on CIFAR100:

```
python3 train.py
       --set cifar100
       --arch the_architecture_that_you_search
```


## Results
### Results on CIFAR10
Method | Params(M) | Error(%)| Search-Cost
--- | --- | --- | ---
AmoebaNet-B|2.8|2.55|3150
DARTSV1 | 3.3 | 3.00 | 0.4
DARTSV2 | 3.3 | 2.76 | 1.0
SNAS    | 2.8 | 2.85 |1.5
PC-DARTS | 3.6 | **2.57** | **0.1**

### Results on CIFAR100
Method | Params(M) | Error(%)| Search-Cost
--- | --- | --- | ---
AmoebaNet-B|2.8|2.55|3150
DARTSV1 | 3.3 | 3.00 | 0.4
DARTSV2 | 3.3 | 2.76 | 1.0
SNAS    | 2.8 | 2.85 |1.5
PC-DARTS | 3.6 | **2.57** | **0.1**


## Visualization
Package [graphviz](https://graphviz.readthedocs.io/en/stable/index.html) is required to visualize the cells that you search
```
python visualize.py EXP
```
where `EXP` can be replaced by any architectures in `genotypes.py`.
