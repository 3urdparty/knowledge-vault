Adaboost :
- first really successful boosting algorithm developed for binary classification
- Modern boosting methods build on AdaBoost, most notably stochastic gradient boosting machines.
[Youtube Video](https://www.youtube.com/watch?time_continue=3&v=LsK-xG1cLYA&embeds_referring_euri=https%3A%2F%2Fbuiltin.com%2F&source_ve_path=Mjg2NjMsMjM4NTE)

Creates stumps (decision trees with one decisions) and uses the accuracy to assign the weightage to the decisions of this stump
Training data that is hard to predict is given more weight
Models are created sequentially



Because so much attention is put on correcting mistakes by the algorithm it is important that you have clean data with outliers removed.