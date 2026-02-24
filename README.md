# Inertial-Mass-Optimizer-IMO-
Inertial Mass Optimizer (IMO): A physics-guided optimization algorithm that dynamically adjusts parameter updates based on gradient direction for stable and efficient training.

## Aim
The aim of this project is to design a physics-inspired optimization algorithm that improves convergence speed and stability in machine learning models.


## Motivation
Traditional optimizers such as SGD, Momentum, Adam, and RMSProp face several issues:

- Oscillation in narrow valleys  
- Overshooting due to momentum  
- Slow convergence even when gradients are consistent  

These limitations motivated the development of a more adaptive and stable optimizer.


## Key Idea
The **Inertial Mass Optimizer (IMO)** is inspired by **Newton’s Second Law (F = m × a)**.

- Treats gradient as **force**  
- Assigns **adaptive mass** to each parameter  

### Behavior:
- Decrease mass → Faster updates when direction is consistent  
- Increase mass → Stable updates when gradients oscillate  


## Methodology
1. Compute gradients using backpropagation  
2. Check gradient direction consistency  
3. Update parameter-wise mass  
4. Scale gradients using mass (force calculation)  
5. Apply momentum  
6. Use soft Nesterov update strategy  
7. Update parameters  


## Benchmark Experiments

The optimizer was evaluated on both **mathematical optimization problems** and **deep learning tasks**.

### Optimization Benchmarks
- Well-conditioned quadratic function  
- Ill-conditioned quadratic function  
- Rosenbrock function (non-convex)  

### Deep Learning Benchmarks
- MNIST dataset (Neural Network training)  
- CIFAR-10 dataset  


## Model Used
- Feedforward Neural Network (Fully Connected)  
- Training via backpropagation  
- Batch size: 64  
- Learning rate: 0.001  


## Results

### Optimization Problems

| Problem | Best Optimizer | Key Result |
|--------|---------------|-----------|
| Well-conditioned | IMO | Fastest convergence |
| Ill-conditioned | IMO | Stable & fast |
| Rosenbrock | IMO | Escaped local difficulties |

- IMO required significantly fewer iterations than Adam and SGD  
- Demonstrated faster convergence on difficult landscapes  


### Neural Network Performance

#### MNIST Dataset
- Adam Accuracy: **95.45%**  
- IMO Accuracy: **88.69%**  

#### CIFAR-10 Dataset
- Adam Accuracy: **73.42%**  
- IMO Accuracy: **59.7%**  


### Key Observations
- 30–55% fewer iterations compared to Adam  
- Reduced oscillation in narrow valleys  
- Stable updates in ill-conditioned problems  
- Slightly lower accuracy on complex datasets  


## Strengths
- Faster convergence  
- Reduced oscillation  
- Stable optimization behavior  
- Effective for ill-conditioned and non-convex problems  


## Limitations
- Higher computational cost (mass tracking)  
- Sensitive to noisy gradients (small batch sizes)  
- Lower accuracy on large datasets like CIFAR-10  


## Tools Used
- Python  
- NumPy  
- PyTorch  
- Matplotlib  


## Output Visualizations

<img width="833" height="489" alt="image" src="https://github.com/user-attachments/assets/3bf8bc4c-83ab-4331-8300-0ae8c122ea48" />
<img width="838" height="501" alt="image" src="https://github.com/user-attachments/assets/660f2027-b52f-406d-a706-0da20fa1b47c" />
<img width="828" height="490" alt="image" src="https://github.com/user-attachments/assets/be06c0b7-bf8c-4978-885d-0ab9365293e7" />
<img width="1154" height="609" alt="image" src="https://github.com/user-attachments/assets/c7193bc2-87df-4c91-94d4-6c9a0b5c31ba" />
<img width="1094" height="675" alt="image" src="https://github.com/user-attachments/assets/1ed27825-0eb6-428e-bb69-b4e5e9b5a157" />

## Conclusion
The **Inertial Mass Optimizer (IMO)** introduces a novel physics-based approach to optimization.  
It improves convergence speed and stability, especially in difficult optimization landscapes.

## Future Work
- Reduce computational overhead  
- Improve robustness to stochastic gradients  
- Hybridize with adaptive optimizers  
- Test on larger-scale models  


