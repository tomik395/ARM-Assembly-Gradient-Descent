# Gradient Descent Implementation in ARM Assembly Language

## Overview
This project is an implementation of the gradient descent algorithm, commonly used in machine learning for optimization, written in ARM Assembly Language. The code is designed to iterate through a dataset, normalize the data, compute the loss function, and adjust parameters for linear regression.

## Code Structure
The primary code structure includes two main components: `main` and `train`. The `main` section sets up various parameters such as array size, learning rate, epochs, and array memory. The `train` function runs the gradient descent algorithm by calculating the gradients and updating the parameters.

### main
The `main` section starts by loading the parameters from memory including array size, learning rate, number of epochs, mean and standard deviation for X and Y, and more. It then initiates variables M (Slope) and C (Y-intercept) to zero, and sets i and j to zero, which will be used in the train function as loop counters. It then calls the train function.

### train
The `train` function initiates the gradient descent. It starts by setting up the stack frame for storing local variables and preserving the link register. It contains two nested loops, an outer loop over the epochs (i), and an inner loop over the data points (j).

In each iteration of the inner loop, it normalizes the current X and Y data points, calculates the derivatives of the loss function with respect to the parameters (M and C), and updates these parameters. The loop continues until the dataset size has been reached.

Then, it checks if the absolute difference between the new loss and the old loss is smaller than a threshold, or if the number of epochs is completed, in which case it exits the loop. If not, it continues with the next epoch.

The function `lossFunc` calculates the loss for the current parameters over the dataset, and `datasetSize` fetches the data point for the current iteration and calculates the derivative for the M and C parameters.

## Requirements
This code is written in ARM Assembly Language, hence requires an ARM processor or a simulator for execution.

## Running the Code
1. Compile the assembly file using an ARM assembly compiler.
2. Run the compiled binary on an ARM processor or a simulator.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change. Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)

> NOTE: This README assumes the user has a basic understanding of Assembly programming and the ARM architecture. If not, it is recommended to learn the basics of assembly programming and the ARM architecture before reading this code.
