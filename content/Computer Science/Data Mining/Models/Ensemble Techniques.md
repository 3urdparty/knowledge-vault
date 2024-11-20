**Ensemble** - combining multiple base learners (individual/weak models) to create a stronger predictive model (like asking for several experts instead of one)
The three major methods:
1. Bagging:
	- Creates multiple models using different random samples of the training data
	- Each model is trained independently
	- Final prediction is based on voting (for classification) or averaging (for regression)
	- Example: [[Random Forrest]]
2. Boosting:
	- Models are trained sequentially
	- Each new model tries to correct the mistakes of previous models
	- Later models focus more on difficult cases that previous models got wrong
	- Examples: AdaBoost, XGBoost, Gradient Boosting
3. Stacking:
	- Multiple models make predictions independently
	- A meta-model (combiner) learns how to best combine their predictions
	- Can use different types of base models together


