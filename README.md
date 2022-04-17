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





## Test on jetson nano
### Results on CIFAR10
Model | Accuracy(%) | Params(M) | FLOPS(M)
--- | :---: | :---: | :---: 
PCDARTS | 96.34 | 3.635 | 567.8
PCDARTS-1/4 | 95.40 | 0.989 | 162.1
PCDARTS-1/4-cut | 95.22 | 0.746 | 130.1

#### Batch size = 1
Model | Latency(s) | Throughput
--- | :---: | :---: 
PCDARTS |  | 
PCDARTS-1/4 | 19.6 | 14.7
PCDARTS-1/4-cut | 17.8 | 18.9

#### Batch size = 20
Model | Latency(s) | Throughput
--- | :---: | :---: 
PCDARTS-1/4 | 30.16 | 176.3
PCDARTS-1/4-cut | 27.66 | 241.6

<br />
<br />

### Results on CIFAR100
Model | Accuracy(%) | Params(M) | FLOPS(M)
--- | :---: | :---: | :---: 
PCDARTS | 81.06 | 3.687 | 567.9
PCDARTS-1/4 | 77.73 | 1.041 | 162.1
PCDARTS-1/4-cut | 76.06 | 0.798 | 130.2

#### Batch size = 1
Model | Latency(s) | Throughput
--- | :---: | :---: 
PCDARTS |  | 
PCDARTS-1/4 | 19.6 | 14.7
PCDARTS-1/4-cut | 17.8 | 18.9

#### Batch size = 20
Model | Latency(s) | Throughput
--- | :---: | :---: 
PCDARTS-1/4 | 30.16 | 176.3
PCDARTS-1/4-cut | 27.66 | 241.6

<br />






## Pretrained models
**CIFAR-10** 
- PCDARTS-1/4 ([cifar10_model.pt](https://drive.google.com/file/d/1IAJ43zyFcyUZcef3sAX6vyUhUX7_Xs0v/view?usp=sharing))
```
python3 test.py
       --arch PCDARTS_quarter
       --model_path cifar10_model.pt
```
- PCDARTS-1/4-cut ([cifar10_model_cut.pt](https://drive.google.com/file/d/1sX3-EOAONXEe3CeA5dE9qv-Ml41_-GMu/view?usp=sharing))
```
python3 test.py
       --arch PCDARTS_quarter_cut
       --model_path cifar10_model_cut.pt
```

<br />

**CIFAR-100** 
- PCDARTS-1/4 ([cifar100_model.pt](https://drive.google.com/file/d/1MFCK-VY_Knn3PqQ-0J8JbsISEaOQSIDU/view?usp=sharing))
```
python3 test_cifar100.py
       --arch PCDARTS_quarter
       --model_path cifar100_model.pt
```
- PCDARTS-1/4-cut ([cifar100_model_cut.pt](https://drive.google.com/file/d/1pxKi_mWnfY5nbQczWBhqdmzUbXiUBOd0/view?usp=sharing))
```
python3 test_cifar100.py
       --arch PCDARTS_quarter_cut
       --model_path cifar100_model_cut.pt
```
   
   
   
   

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
pip3 install graphviz
```
```
python3 visualize.py EXP
```
where `EXP` can be replaced by any architectures in `genotypes.py`.





## Reference
H. Liu, K. Simonyan, and Y. Yang. DARTS: Differentiable architecture  search. ICLR, 2019

Xu, Y., Xie, L., Zhang, X., Chen, X., Qi, G.-J., Tian, Q., and Xiong, H. PC-DARTS: Partial channel connections for memory-efficient architecture search. In International Conference on Learning Representations, 2020 

Y. Mao, G. Zhong, Y. Wang and Z. Deng, "Differentiable Light-Weight Architecture Search," 2021 IEEE International Conference on Multimedia and Expo (ICME), 2021, pp. 1-6, doi: 10.1109/ICME51207.2021.9428132.

[PC-DARTS](https://github.com/yuhuixu1993/PC-DARTS)

[DARTS](https://github.com/quark0/darts)

[THOP: PyTorch-OpCounter](https://github.com/Lyken17/pytorch-OpCounter)
