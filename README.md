#Data Notes
<h1> Goal: Predict the cost of medical insurance </h1>

<h2>Things to do</h2>

- [ ] add a tree visualization
- [ ] create risk model with a risk score 
- [x] add examples of future inputs 
- [x] add pearsons coef
- [x] add a sample with new data

<h2>Building a data pipeline</h2>
<ul>
    <li>setting up a pipeline creates a clean and modular flow. Where one object contains the full workflow.</li>
    <li>Yor fit and transform steps are done automatically in the right order.</li>
    <li>Easy to swap models or steps.</li>
</ul>

<h2>Notes from Working</h2>
<ul>
    <li>Cleaning categorical variables all the same way ColumnTransformer </li>
        <li>ColumnTransformer applies different transformations to different columns. In this case one hot encoding for the categorical variables and passthrough for the others </li>
    <li>Mean Squared Error tells us how close the model is. A MSE closer to zero is great</li>
    <li>Root Mean Squared Error on average how much we are off by</li>
</ul>

<h2>Helpful Libraries</h2>
<ul>
    <li>Pandas</li>
    <li>Shap</li>
    <li>Scikit-learn</li>
</ul>

<h2>Things I Learned</h2>
<ul>
    <li>Shap helped me visualize how much each item impacted the regression tree decision</li>
    <li>The decision tree performed better than the general linear regression model according to the rsquare .8 vs .7</li>
</ul>

<hr>

<h2> Deep Learning Section for Keras </h2>
<ul>
    <li>You could think of each layer in a neural network as performing some kind of relatively simple transformation.</li>
    <li>Without activation functions, neural networks can only learn linear relationships. In order to fit curves, we'll need to use activation functions.</li>
    <li>The layers before the output layer are sometimes called hidden since we never see their outputs directly.</li>
    <li>The Sequential model we've been using will connect together a list of layers in order from first to last: the first layer gets the input, the last layer produces the output.</li>
</ul>

<h3>Types of Activation layers</h3>
<ul>
    <li>relu</li>
    <li>softmax</li>
    <li>sigmoid</li>
    <li>selu</li>
</ul>

<p>up until now we have just set the foundation for a network. We still need to tell the network what problem to solve that is where we use the loss function</p>

<strong>The loss function measures the difference between the the target's true value and the models predicted value.</strong>

<h3>Types of loss function for Regression</h3>
<ul>
    <li>Mean Absolute Error</li>
    <li>Mean Squared Error</li>
    <li>Huber</li>
</ul>

<p>During Training the loss function will guide the model</p>

<h3>The Optimizer</h3>

<p>The Optimizer is an algorithm that adjusts the weights to minimize loss. Most algorithms used in deep learning are known as <strong>stochastic gradient descent</strong>. They are iterative.</p>

<p>Adding the Loss and Optimizer comes after defining a model, you can add a loss function and optimizer with the model's compile method</p>

<h2>Note: EPOCH</h2>
<p>An epoch is when all the training data is used at once and is defined as the total number of iterations of all the training data in one cycle for training the machine learning model. Another way to define an epoch is the number of passes a training dataset takes around an algorithm.</p>

<h2>Note: Plotting Loss</h2>
<p>After training your model you can view the loss through the 'history.history' Convert to df and plot</p>

<h3>Capacity & Stopping</h3>

<p>You can increase the capacity of a network either by making it wider (more units to existing layers) or by making it deeper (adding more layers). <br>
Wider networks have an easier time learning more linear relationships, while deeper networks prefer more nonlinear ones.</p>

<pre>
model = keras.Sequential([
    layers.Dense(16, activation='relu'),
    layers.Dense(1),
])

wider = keras.Sequential([
    layers.Dense(32, activation='relu'),
    layers.Dense(1),
])

deeper = keras.Sequential([
    layers.Dense(16, activation='relu'),
    layers.Dense(16, activation='relu'),
    layers.Dense(1),
])
</pre>