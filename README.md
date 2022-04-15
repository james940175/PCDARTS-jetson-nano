# PCDARTS on jetson nano

## Usage
#### Search on CIFAR10

- First search the best cell on CIFAR10
- When finishing the search phase, you have to paste the mode to the genotypes.py
```
python3 train_search.py
```

#### Evaluation on CIFAR10:

```
python train.py \\
       --auxiliary \\
       --cutout \\
```
#### Evaluation on CIFAR100:

```
python train.py \\
       --auxiliary \\
       --cutout \\
```
