# linearSmile
Smile detectors based on linear regression

## ¯\\\_(ツ)_/¯

### What's inside?

- Analytical Smile Detector
- Gradient Descent Smile Detector

### Analytical Weight
`analytical_weight_detector.py` computes the optimal weights `w` and bias term `b` for the linear regression model by deriving the expression for the gradient of the cost function w.r.t. w and b, setting it to 0, and then solving.

The weight is computed as

<div align="center">
	<img width="180" src ="weight.png"/>
</div>

with the cost function of

<div align="center">
	<img width="340" src ="mse.png"/>
</div> 

### Gradient Descent

The algorithm picks a random starting value for `w` and `b` and a small learning rate (e.g., `ε` = .001). Then, using the expression for the gradient of the cost function, iteratively update w,b to reduce the cost. Stop when the difference between costs over successive training rounds is below some “tolerance” (e.g., `δ` = 0.000001). This method of optimizing model weights is much more general than analytically computing the optimal weights, at the expense of requiring some additional optimization hyperparameters (e.g., learning rate, tolerance).

The gradient of error w.r.t weight and w.r.t bias are computed as 

<div align="center">
	<img width="400" src ="gradient_weight.png"/>
</div>

and

<div align="center">
	<img width="380" src ="gradient_bias.png"/>
</div>

individually, where

<div align="center">
	<img width="190" src ="O.png"/>
</div>

### Gradient Descent with Regulation

In machine learning, **low** training error and **high** testing error imply **overfitting**. One of the simplest and oldest regularization techniques is to ***panelize*** large weights in the cost function. The L2 regularized error and the regularized gradient of error w.r.t weight are computed as

<div align="center">
	<img width="270" src ="mse_regularized.png"/>
</div>

and

<div align="center">
	<img width="240" src ="gradient_weight_regularized.png"/>
</div>

seperately.

## Getting Started

### Prerequisite

- Python v3.6.4
- NumPy v1.14.0

### Running

#### Analytical Weight Detector
To test out the analytical weight detector, run the following command in the terminal:

```bash
python3 analytical_weight_detector.py
```

Here is an example output:

```bash
Training MSE: 0.049402
Testing MSE: 0.092220

Training Accuracy: 0.895000
Testing Accuracy: 0.767505
```

#### Gradient Descent Detector
To test out the gradient descent detector, run the following command in the terminal:

```bash
python3 gradient_descent_detector.py
```

Here is an example output:

```bash
Start training the model
Training MSE: 0.052163
Testing MSE: 0.086731

Training Accuracy: 0.882500
Testing Accuracy: 0.774617
```

#### Gradient Descent with Regulation Detector
To test out the gradient descent with regulation detector, run the following command in the terminal:

```bash
python3 gradient_descent_regulation_detector.py
```

Here is an example output:

```bash
Start training the model
Unregulated Training MSE: 0.066756
Unregulated Testing MSE: 0.073758

Training Accuracy: 0.841000
Testing Accuracy: 0.811269
```

## Authors

- **Ben Hylak** - *Initial work* - [bhylak](https://github.com/bhylak)

- **Yang Liu** - *Initial work* - [byliuyang](https://github.com/byliuyang)

## License
This repo is maintained under MIT license.