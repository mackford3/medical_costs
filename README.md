#Data Notes
<h1> Goal: Predict the cost of medical insurance </h1>

<h2>Things to do</h2>

- [ ] add examples of future inputs 
- [ ] add p balue tests
- [ ] see if other data points can be added to improve. 
- [ ] add a tree visualization
- [ ] create risk model with a risk score 

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
