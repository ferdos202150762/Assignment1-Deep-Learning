# Assessment 1

## Datasets for this assessment

https://www.dropbox.com/sh/sztempv7hymr3ck/AADjIBGNJgKl9Ox7LcpKlgR7a?dl=0

## P1 - permutation-invariant functions

Consider the problem of learning a permutation-invariant function <img src="https://render.githubusercontent.com/render/math?math=f:\mathbb{R}^m\rightarrow\mathbb{R}"> by using a neural network according to the <img src="https://render.githubusercontent.com/render/math?math=(\phi,\rho)">-sum-decomposition neural network architecture defined in lectures.

For function <img src="https://render.githubusercontent.com/render/math?math=\phi">, use a feedforward neural network with one hidden layer with 100 neurons and ReLU activation function, and the output layer with `lat_dim` output units. `lat_dim` is a hyperparameter which you will need to set to values specified below.

For function <img src="https://render.githubusercontent.com/render/math?math=\rho">, use a feedforward neural network with one hidden layer with 100 neurons and ReLU activation function.

For training, use the stochastic gradient descent algorithm with learning rate 1e-4. Use MSE for the loss function. Use a validation dataset by taking 0.1 portion of the training dataset (validation split). Use batch size of value 128.

The training and testing datasets are provided in files `train-1.csv` and `test-1.csv`, respectively. Each row in these files consists of 11 comma-separated values, with the first 10 values corresponding to features of the feature vector, and the last value corresponds to the response variable.

You need to perform the following tasks:

### P1.1

Implement the neural network specified above. Explain your implementation.

### P1.2

Train the neural network with `lat_dim = 5` for 10 epochs. Show the test and validation loss versus the number of epochs. Show also the test MSE value. Repeat this but by taking `lat_dim = 100`. Discuss the obtained results. 

### P1.3

Train the neural network with `lat_dim = 100` for 10 epochs, for different values of learning rates equal to 0.01, 0.1, and 0.5. Discuss the obtained results.

### P1.4

Train the neural network with `lat_dim = 100` for 50 epochs, with ReLU activation functions. Show the training and validation loss versus the number of epochs. Repeat this for the same setting but with ReLU activation functions replaced with sigmoid activation functions. Discuss the results.

### P1.5

In this part you need to evaluate the neural network architecture defined above, for different values of `lat_dim` in [1, 2, ..., 10, 20, 30, ..., 100]. For each setting of `lat_dim`, run 5 independent training runs, each for 5 epochs. For each training run, select the best model found with respect to the MSE validation metric. Compute the test MSE value of the best model for each training run. For each `lat_dim`, compute the mean of the test MSE values of the best models identified in the corresponding training runs. Show the mean test MSE versus `lat_dim` in a plot. Comment the results.  

## P2 - permutation-equivariant functions

Consider the problem of learning a permutation-equivariant function <img src="https://render.githubusercontent.com/render/math?math=f:\mathbb{R}^{m\times{d}}\rightarrow\{0,1\}^m"> by using a feedforward neural network with equivariant layers - see lectures for definition. The function we are going to consider corresponds to a choice function that for each set of input items outputs the choice of one of these items (using one-hot encoding).

We consider a feedforward neural network with `L` equivariant layers. Each of the first `L-1` layers consists of an equivariant affine transformation followed by ReLU activation units with output dimension <img src="https://render.githubusercontent.com/render/math?math=m\times{w}">. The output layer is an equivariant affine transformation with output dimension <img src="https://render.githubusercontent.com/render/math?math=m">.   

For training, use Adam optimizer with learning rate of value 1e-4 and epsilon set to value 1e-3. For the loss function, use MSE. Use validation split of value 0.1. Use batch size of value 300. Use the number of epochs of value 100.

The training dataset is given in `xtrain-2.csv` and `ytrain-2.csv`. Each row of xtrain-2.csv contains values of a flatten <img src="https://render.githubusercontent.com/render/math?math=m\times{d}"> matrix (row concatenation). Each row of ytrain-2.csv contains elements of a <img src="https://render.githubusercontent.com/render/math?math=m"> dimensional output vector. The test dataset is given in `xtest-2.csv` and `ytest-2.csv` and is of the same format. In these datasets, <img src="https://render.githubusercontent.com/render/math?math=m=5"> and <img src="https://render.githubusercontent.com/render/math?math=d=3">.

You need to perform the following tasks:

### P2.1

Implement the feedforward neural network defined above. Explain your implementation.

### P2.2

Train the neural network with <img src="https://render.githubusercontent.com/render/math?math=(L,w)=(2,5)">. Show the training and validation loss versus the number of epochs. Compute the test MSE value. Repeat this for <img src="https://render.githubusercontent.com/render/math?math=(L,w)"> set to (2,10), (2,100), (2,200), (3,5), (3,10), (3,100), and (3,200). Discuss the obtained results. 

## Marking scheme

| Problem | Full points | Max points |
|:--------|-----------:|-----------:|
| P1-1  | neural network implementation | 20 |
| P1-2  | training and evaluation | 20 |
| P1-3  | choice of learning rate |            5 |
| P1-4  | choice of activation function  |            5 |
| P1-5  | neural network comparison |            20 |
| P2-1  | neural network implementation |  20 |
| P2-1  | training and evaluation |  10 |
| Total |         |          100 |

## Submission date and guidelines

1. Solution deadline: **23 February, 11:59 pm**.
2. Upload your Python code (including discussion/explanation for each question) and additional files (if any) into GitHub. 
3. There is no need for uploading training and testing data, **as these datasets cannot be changed**.
4. **IMPORTANT**: for completing your submission, go to [Moodle](https://moodle.lse.ac.uk/mod/assign/view.php?id=1069783) (Assessment 1 section) and **provide a file with a link to your GitHub repository** (this must be done by the deadline). 

