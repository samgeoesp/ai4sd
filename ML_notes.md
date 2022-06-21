# ML Lectures Notes

### Overview of Machine Learning - Mahesan Niranjan

Spoke about the development of data and examples of this. Examples of data with and without targets - in particular mentioning investigating spread 
of this data. Also mentioned the high dimensional space associated with experimental datasets. Supervised vs. Unsupervised.


Predictions are not rational when having a overtly complicated function approximator. To make this more reasonable, add regularization.

'Curse of Dimensionality'

To maintain the same accuracy at higher and higher densities you need expenentionally more data. 

>
> Add to this.
>


### Machine Learning: Estimation - Mahesan Niranjan

Frequentist thought vs. Bayesian thought.

Different correlations of data:

- Data not correlated = clump.
- Data linearally correlated = line to the effect of y = x.
- y equals a relatively consistent x.

Principle Component Analysis

>
> Add to this.
>

Constrained Optimisation Problems

>
> Add to this.
>

Autoencoders

>
> Add to this.
>

tSNE

>
> Add to this.
>


### Classification: Mahesan Niranjan

X vs. y with two plots of high/low pairs that overlap. Can store as a vector of both class 1 and class 2.

ROC Curves

>
> Add to this.
>

Mahalanodis Distance

>
> Add to this.
>


### Linear Regressioon to Perceptron Classification: Mahesan Niranjan

Notation - append certain values to make algebra more managable:

>
> f = y^t a
>

Error is sum of model actual values and predicted values obtained from the function chosen. 
With Linear Regression, you can't get stuck in a local minima because the error is raised to the power 2 at greatest. This means that plotting this line 
would generate one minima. Any local == Global. This is *NOT* the case for NN's.

>
> Insert Plot.
>

Learning rate needs to always be tuned as too small you may struggle to reach minima but too large you may jump over. This also depends on the gradient:

- Large gradient (use small learning rate)
- Small gradient (use large learning rate)

Second Order (Newton's) method inverts a Hessian which has a cubic relationship thus provides addditional complexity and challenge.

Stochastic Gradient Descent (SGD) utilises computation of the nth value in the data to then update. Updates and updates until gradient no longer changes. 
Modern literature typically always uses SGD. SGD provides a chance to get out of local minimas.

Regularisation applies a small constant (diagonal matrix) to eleviate the problem of pseudo inverse solution being ill conditioned. Tune this to remove 
the problems. Restricts the a value from reaching large values.
L1 norm (sum of absolute values of a) is another method to provide regularisation by pushing smaller values to 0. This provides a sparse solution. 

Perceptron - A suitable performance measure

Number of misclassified examples as measure of error = Piecewise constant. You cannot differentiate this because it is stepwise.

Instead, for a suitable error measure you use the dot product sum of all the misclassified examples. Once you have the function you compute the gradient 
to then use with new predictions. Defining a loss function for your problem is very important - the wrong loss function will impact model performance. 

>
> Add to this.
> 

### Machine Learning: Radial Basis Functions and Multi-Layer Perceptrons - Mahesan Niranjan


Radial Basis Functions:

Fix non linear part in data-dependent way and estimate only a linear part utilising Linear Regression.

> 
> Add to this.
>

Multi-Layer Perceptron

Completely non-linear models. A lot of the previous logistics combined together. *Read up on backpropogation.*

Deeper layers can affect gradients - vanishing gradient problem. Multiplying small weights by small weights makes smaller and smaller gradients thus, poor 
predictive ability.

To speed up training you can update weights and curvature information as you go. This is 'Newton's Method' and has the issue mentioned earlier with 
inverting the Hessian. To sit inbetween there is algorithms to aide sufficient gradient descent. One is *momentum* which weights the change based upon 
previous weight and proposed weight change for this step. This is the idea to smooth the error function by carrying information forward. An example is 
*QuickProp* which measures gradient in two different places then updates the weight. 

Performance on Out-of-Sample Data - unseen data.

Don't want to overfit to the train. Combat this with early stopping implemented nicely in TensorFlow.

>
> Insert epoch vs. accuracy plot.
>

Deep Learning - Mahesan Niranjan

Approximating Data + Regularisation leads to Generalisation. 
