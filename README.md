﻿# Client Selection in Federated Learning
Client Selection methods of Federated Learning implementations in PyTorch

## Requirements
```shell
torch
torchvision
numpy
scipy
tqdm
h5py
```

## Client Selection methods
```shell
python main.py --method {client selection method you want}
```

 1. ```Random``` Random
 2. ```AFL``` [Active Federated Learning](https://arxiv.org/pdf/1909.12641.pdf)
 3. ```Pow-d``` [Power-of-d-Choice](https://arxiv.org/pdf/2010.01243.pdf)
 4. ```Cluster1``` [Clustered Sampling 1](http://proceedings.mlr.press/v139/fraboni21a/fraboni21a.pdf)
 5. ```Cluster2``` [Clustered Sampling 2](http://proceedings.mlr.press/v139/fraboni21a/fraboni21a.pdf)
 6. ```DivFL``` [Diverse Client Selection for FL](https://openreview.net/pdf?id=nwKXyFvaUm)

## Benchmarks

1. FederatedEMNIST (default)
    
    ```shell
    python main.py --dataset FederatedEMNIST --model CNN -A 10 -K 3400 --lr_local 0.1 -B 20 -R 2000 
   ```

2. CelebA
   
   ```shell
   python main.py --dataset CelebA --model CNN -A 10 -K 9343 --lr_local 0.005 -B 5 -R 100
   ```

3. FederatedCIFAR100
    
   ```shell
    python main.py --dataset FedCIFAR100 --model ResNet -A 10 -K 500 --lr_local 0.1 -B 20 -R 4000 
   ```

4. FederatedCIFAR10 (Partitioned by Dirichlet distribution, followed by Clustered Sampling) 
    
   ```shell
    python main.py --dataset PartitionedCIFAR10 --model CNN -A 10 -K 100 --lr_local 0.1 -B 50 -R 1000 
   ```

5. Reddit

   ```shell
    python main.py --dataset Reddit --model BLSTM -A 200 -K 7527 --maxlen 400 \
        --alpha1 0.75 --alpha2 0.01 --alpha3 0.1 \
        --lr_local 0.01 --lr_global 0.001 -E 2 -B 128 -R 100
   ```
   
   - [ ] TODO: reproducible performance

## References
 - https://github.com/FedML-AI/FedML 
 - https://github.com/Accenture/Labs-Federated-Learning/tree/clustered_sampling
