# PCDARTS on jetson nano

## Usage
#### Search on CIFAR10

- First search the best cell on CIFAR10
- When finishing the search phase, you have to paste the mode to `genotypes.py`
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


## Visualization
Package [graphviz](https://graphviz.readthedocs.io/en/stable/index.html) is required to visualize the cells that you search
```
python visualize.py EXP
```
where `EXP` can be replaced by any architectures in `genotypes.py`.
