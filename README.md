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
       --arch the_architecture_that_you_search_in_the_search_phase
```
#### Evaluation on CIFAR100:

```
python3 train.py
       --set cifar100
       --arch the_architecture_that_you_search_in_the_search_phase
```
