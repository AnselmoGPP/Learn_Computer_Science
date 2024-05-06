# Machine learning 2

## Table of Contents
+ [Introduction](#Introduction)
+ [Linear regression (one variable)](#linear-regression-(one-variable))
+ [Linear regression (multiple variables)](#linear-regression-(multiple-variables))
+ [Logistic regression](#logistic-regression)
+ [Regularization](#regularization)
+ [Advices](#advices)
+ [Support vector machines](#support-vector-machines)
+ [Unsupervised learning](#unsupervised-learning)
+ [Anomaly detection](#anomaly-detection)
+ [Recommender systems](#recommender-systems)
+ [Large scale machine learning](#large-scale-machine-learning)
+ [Photo OCR](#photo-ocr)


## Introduction

**Machine learning:** Field of study that gives computers the ability to learn without being explicitly programmed. A computer program learns from experience E with respect to some task T and some performance measure P, if T, as measured by P improves with E. if the measured P improves with E.
 
Main machine learning algorithms:

- **Supervised learning:** Most common. We teach the computer by giving the algorithm a data set (training set) in which the "right answers" are given. A learning algorithm can deal with an infinite number of features/attributes with which make predictions. To deal with this infinite amount without running out of memory we use an algorithm called Support Vector Machine. Two types of problems: 
  - **Regression problem:** Predicts continuous valued output.
  - **Classification problem:** Predicts discrete valued output.
- **Unsupervised learning** (or clustering)
We don't give the right answer to the algorithm, it learns by itself. Used to organize large computer clusters. 
- **Reinforcement learning**
- **Recommender systems**

**Training set:** Portion of a **data set** used to fit (train) a model for prediction or classification of values that are known in the training set, but unknown in other (future) data. Example:
- Training set of housing prices (we want to predict prices):
  - Size in feet<sup>2</sup> (x): 2104, 1416, 1534, 852
  - Price in $ (y): 460.000, 232.000, 315.000, 178.000
- m: number of training examples
- x's: input variable (features)
- y's: output variable (target)
- (x, y): One training example
- (x<sup>(i)</sup>, y<sup>(i)</sup>): i<sup>th</sup> training example

**Learning algorithm:** Algorithm that takes a **training set** (x<sup>(i)</sup>, y<sup>(i)</sup>) as input, and outputs a function (h, hypothesis) that, given an input (x), offers an output (y).


## Linear regression (one variable)

### Cost function

**Cost function:** Learning algorithm for **supervised learning**. The hypothesis (h) will be a linear function (straight line). Represented as: 

h<sub>&Phi;</sub>(x) = &Phi;<sub>0</sub> + &Phi;<sub>1</sub>x

- &Phi;<sub>0</sub>: ordinate in the origin
- &Phi;<sub>1</sub>: slope

Given a training set, choose a value for each parameter (&Phi;<sub>0</sub> and &Phi;<sub>1</sub>x) so that h<sub>&Phi;</sub>(x) is close to **y** for out training examples (x, y).

We want to make small this expression (minimization problem): 

(h<sub>&Phi;</sub>(x) - y)<sup>2</sup>

**Square error cost function (J):** It's the most commonly used cost function in regression problems (though there are others). We want to find the values for the parameters (&Phi;<sub>0</sub>, &Phi;<sub>1</sub>...) that minimize J. 

J(&Phi;<sub>0</sub>, &Phi;<sub>1</sub>) = (1/2m) &sum;<sub>m,1</sub>(h<sub>&Phi;</sub>(x<sup>(i)</sup>) - y<sup>(i)</sup>)<sup>2</sup>

- (1/2m) is used for calculating the average multiplied by 1/2, which makes the math easier.

Example: We want to find the function (h<sub>&Phi;</sub>(x) = &Phi;<sub>0</sub> + &Phi;<sub>1</sub>x) that best models a scenario (like housing prices as a function of different parameters), which requires us to find the correct parameters. On a graph, it plots a straight line. There is also a cost function J(&Phi;<sub>0</sub>, &Phi;<sub>1</sub>) that plots a concave surface (if we only have one parameter, it's a parabola). The correct values of the parameters are those that make J = 0 (or close).

Note 2: Every h<sub>&Phi;</sub>(x<sup>(i)</sup>) - y<sup>(i)</sup>)<sup>2</sup> is the vertical distance between (x<sup>(i)</sup>, y<sup>(i)</sup>) (computed output given our parameters) and the real output (given by a data set).

Note 2: Instead of 3D charts we can use contour plot/figures. They draw sets of points (&Phi;<sub>0</sub>, &Phi;<sub>0</sub>) that have the same value for J. Each point represents a unique h<sub>&Phi;</sub>(x) function.

### Gradient descent

**Gradient descent (GD):** Algorithm for minimizing the cost funcion J. Used all over the place in machine learning (not only linear regression). We start with some parameters (&Phi;<sub>0</sub>, &Phi;<sub>1</sub>...) and keep changing their values to reduce J until we hopefully end up at a minimum. These changes are toward points that go downwards in J.

- **Batch GD:** Each step of GD uses all the training examples (other types may use a subset of training examples).
for(until convergence) {  &Phi<sub>j</sub> = &Phi<sub>j</sub> - &alpha;(&delta;J(&Phi;<sub>0</sub>,&Phi;<sub>1</sub>)/&delta;&Phi;<sub>j</sub>)  }

- &alpha;: Learning rate. It controls how big a step we take downhill. If &alpha; is too small, GD can be slow. If &alpha; is too large, GD can overshoot the minimum (fail to converge, or even diverge). GD can converge to a local minimum even if &alpha; is kept fixed (as we approach to a local minimum, GD automatically takes smaller steps) so there's no need to decrease &alpha; over time.
- &delta;J(&Phi;<sub>0</sub>,&Phi;<sub>1</sub>)/&delta;&Phi;<sub>j</sub>: Partial derivative (it represents the slope of J graph for component &Phi;<sub>j</sub>). We look for a derivative = 0 or close.
- d: Non-partial derivative symbol.

We compute the algorithm simultaneouly for every &Phi;<sub>j</sub> (i.e. for each &Phi; parameter) in order to update every &Phi. Then we compute y again with the new values for &Phi; (iteration). And so on.

Compute partial derivatives:
&delta;J(&Phi;<sub>0</sub>,&Phi;<sub>1</sub>) / &delta;&Phi;<sub>j</sub> = (&delta;/&delta;&Phi;<sub>j</sub>)(1/2m) &sum<sup>m</sup><sub>i=1</sub>(&Phi;<sub>1</sub>x<sup>(i)</sup><sub>1</sub> + &Phi;<sub>0</sub>x<sup>(i)</sup><sub>0</sub> - y<sup>(i)</sup>)<sup>2</sup>
- &delta;J(&Phi;<sub>0</sub>,&Phi;<sub>1</sub>) / &delta;&Phi;<sub>0</sub> = (1/m) &sum<sup>m</sup><sub>i=1</sub>(h<sub>&Phi;</sub>(x<sup>(i)</sup>) - y<sup>(i)</sup>)   (x<sub>0</sub>=1)
- &delta;J(&Phi;<sub>0</sub>,&Phi;<sub>1</sub>) / &delta;&Phi;<sub>1</sub> = (1/m) &sum<sup>m</sup><sub>i=1</sub>(h<sub>&Phi;</sub>(x<sup>(i)</sup>) - y<sup>(i)</sup>)   (x<sub>0</sub>=1) · x<sup>(i)</sup><sub>1</sub>

Now we can introduce both derivatives in our algorithm and use it to minimize J. Cost function of linear regression is a convex function, and doesn't have local optima except for the one global optimum.

**Normal equation method:** Solution for numerically solving for the minimum of the cost function J without using an iterative algorithm like GD. However, GD scales better to larger data sets.


## Linear regression (multiple variables)

We can take into account more than one variable/feature (x<sub>1</sub>=size, x<sub>2</sub>=bedrooms, x<sub>3</sub>=floors, x<sub>4</sub>=age) for every result (y=price).

- n: number of features (previously we used n to denote the number fo examples in the training set).
- x<sup>(i)</sup>: Vector containing all the features in the i<sup>th</sup> training example.
- x<sup>(i)</sup><sub>j</sub>: Value of feature j in x<sup>(i)</sup>.

**Hypothesis:**  h<sub>&Phi;</sub>(x) = &Phi;<sub>0</sub>x<sub>0</sub> + &Phi;<sub>1</sub>x<sub>1</sub> + &Phi;<sub>2</sub>x<sub>2</sub> + &Phi;<sub>3</sub>x<sub>3</sub> + &Phi;<sub>4</sub>x<sub>4</sub>
- x<sub>0</sub>=1

Now we have 2 vectors: 
                  |x<sub>0</sub>|                       |&Phi;<sub>0</sub>|
                  |x<sub>1</sub>|                       |&Phi;<sub>1</sub>|
x<sup>(i)</sup> = |x<sub>2</sub>|     x<sup>(i)</sup> = |&Phi;<sub>2</sub>|     
                  |     ...     |                       |       ...       |
                  |x<sub>n</sub>|                       |&Phi;<sub>n</sub>|

h<sub>&Phi;</sub>(x<sup>(i)</sup>) = &Phi;<sup>T</sup>·x<sup>(i)</sup>

**Cost function:** J(&Phi;<sub>0</sub>,&Phi;<sub>1</sub>...&Phi;<sub>n</sub>) = J(&Phi;) = (1/2m) &sum;<sup>m</sup><sub>i=1</sub>(h<sub>&Phi;</sub>(x<sup>(i)</sup>) - y<sup>(i)</sup>)<sup>2</sup>

**Gradient descent:** The following is used for updating all parameters simultaneously.

for(until convergence) {  &Phi;<sub>j</sub> = &Phi;<sub>j</sub> - &alpha &delta;J(&Phi;)/&delta;&Phi;<sub>j</sub>;  }
for(until convergence) {  &Phi;<sub>j</sub> = &Phi;<sub>j</sub> - &alpha (1/m) &sum<sup>m</sup><sub>i=1</sub>(h<sub>&Phi;</sub>(x<sup>(i)</sup>) - y<sup>(i)</sup>) · x<sup>(i)</sup><sub>j</sub>;  }

**Steps:**
1. Choose a type of **h(x)**
2. Obtain **J(&Phi;)** using training examples and initial values for &Phi;
3. Minimize J(&Phi;) using **GD** (obtain all &Phi; in every iteration simultaneously)
4. Now we have the optimal h(x)

**Normalization:**

- **Feature scaling:**
- **Mean normalization:**
- **Learning rate (&alpha):**
- **Feature edition:**


## Logistic regression

## Regularization

## Advices

## Support vector machines

## Unsupervised learning

## Anomaly detection

## Recommender systems

## Large scale machine learning

## Photo OCR