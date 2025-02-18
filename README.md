# Linear Regression using Gradient Descent

Overview

This project implements Linear Regression using Batch Gradient Descent, Stochastic Gradient Descent (SGD), and Mini-Batch Gradient Descent without using libraries like scikit-learn, TensorFlow, or PyTorch. The dataset is normalized before training, and different learning rates are tested to observe their effects on the cost function.

### Dataset Description
The dataset consists of two files:

1. linearX.csv (Independent/Predictor Variable)
2. linearY.csv (Dependent/Response Variable)

These datasets are concatenated into a single DataFrame with columns X and Y (merged_dataset).

## Questions

### 1. Use linear regression to fit a straight line to the given database. Set your learning rate to 0.5. What are the cost function value and learning parameters values after convergence? Also, mention the convergence criteria you used.
#### ans : 
After convergence the cost function value is 0.2781 and value of m is 0.6620 and b is 0.0000 (after 50 iteration)
<img width="278" alt="cost" src="https://github.com/user-attachments/assets/ded174f8-5459-48ed-bcc3-c15f3867c64f" />
The convergence criteria used in the code is the stabilization of the cost function.

### 2. The cost function that we are using in this assignment is different than the one we used in class. Can you think of the advantage of averaging the cost?
#### ans : Advantages of Averaging the Cost Function -
Averaging the cost function provides several benefits in linear regression:

1. Stabilizes Gradient Updates :-
     When using batch gradient descent, averaging the cost function ensures that each update step is more stable and not dominated by extreme values. This helps prevent 
     sudden fluctuations in parameter updates, leading to smoother convergence.

2. Better Convergence Behavior :-
     Without averaging, the cost function values could become excessively large, especially when the dataset is large. Averaging prevents large gradients, making the 
     optimization process more controlled and reducing the chances of divergence.

3. Ensures Scale Independence :-
     If we did not average, the cost function would scale with the dataset size. By averaging, we make the cost function independent of the number of data points, ensuring 
     that it remains comparable across datasets of different sizes.

4. Improves Numerical Stability :-
     When working with large datasets, summing the squared error terms directly can result in numerical instability. Averaging helps in keeping the computed values within a 
     reasonable range, reducing the risk of overflow or underflow.

5. Consistency Across Different Optimization Methods :-
     Whether using batch gradient descent, stochastic gradient descent, or mini-batch gradient descent, averaging the cost function ensures consistent learning behavior 
     across different optimization techniques.

### 3. Plot cost function v/s iteration graph for the model in question 1 for first 50 iterations.
#### ans : ![cost_vs_iterations](https://github.com/user-attachments/assets/fbb78a09-0248-4ca2-bd86-49bf75be5990)


### 4. Plot the given dataset on a graph and also print the straight line you obtained in question 1 to show how it fits the data.
#### ans : ![Linear Regression Fit](https://github.com/user-attachments/assets/aaf48fba-396c-48b7-900c-22f645cea2af)

### 5. Test your regression model with the learning rates lr = 0.005, lr = 0.5, lr = 5. For each learning rate, plot a graph showing how the cost function changes for the first 50 iterations and write your observation.
#### ans : 
![photo1](https://github.com/user-attachments/assets/9c7cbf71-da41-4837-8a5f-193ba4b8441e)![photo2](https://github.com/user-attachments/assets/cb083032-8878-4d91-908d-86b6468ad677)![photo3](https://github.com/user-attachments/assets/45b7ea01-44a9-4351-a86a-d36114e62193)

#### Observations : 
   1. A learning rate of 0.5 is optimal for this dataset as it balances convergence speed and stability.
   2. A learning rate of 0.005 is too small, leading to slow progress.
   3. A learning rate of 5 is too large, causing divergence.

### 6. Choose a suitable learning rate, then implement stochastic and min-batch gradient descent, plot the cost function against iteration, and observe how your cost function changes compared to batch gradient descent.
#### ans :
![SDG (1)](https://github.com/user-attachments/assets/7877df28-2d50-41bb-a33f-bce0a2ad4553)
![cost_vs_iterations](https://github.com/user-attachments/assets/d8597241-ae87-4811-af32-23eaf92f541b)
![Mini-Batch GD](https://github.com/user-attachments/assets/7b581b91-507c-4b2f-bd75-970b45dd2647)

Based on the three graphs the best optimization method for your model is **Stochastic Gradient Descent (SGD)**.
In the , **Batch Gradient Descent** ,the cost function decreases smoothly over iterations. is stable but may be slow for large datasets. other side **Mini-Batch Gradient Descent (MBGD)** ,the cost function initially remains stable but later explodes, this indicates divergence, likely due to an inappropriate learning rate or batch size. But in **Stochastic Gradient Descent (SGD)** ,it consistently decreases the cost while maintaining efficiency. Despite the noise, SGD converges faster and generalizes better, avoiding getting stuck in local minima.
