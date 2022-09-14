[[Deep Learning]]

# k-Nearest Neighbor Classifier

Instead of only using the label of the nearest image, like in [[Nearest Neighbor Classifier|NN Classifier]], we find the **k** nearest neighbors and based on them make our prediction.

$k=1$ is just the [[Nearest Neighbor Classifier|NN Classifier]].

The higher the **k** value is, the _smoother_ and more resistant the classifier is to outliers.
![[Pasted image 20220913195112.png]]

In the example $k=5$ was used, but what should the value be, to have the best accuracy?

## Validation sets for [[Hyperparameter]] tuning
The L1 and L2 distances from before, is what we call [[Hyperparameter|hyperparameters]]. We could also have used the dot product and a number of other options.

One of the ways to find **k** is to just try out different values, although ideally we _never_ want to touch the dataset, at least not until the end, and touch it that one time.

The danger here is that the hyperparameters may have been tuned to fit the test set, but would have poor performance in a real life scenario.

This is called [[Overfitting|overfitting]], or that the hyperparameters has been **overfit** to the test set.

If you tune the parameters to the test set, the test has basically become the training set, and that would produce great results, in testing, but would most likely not work well with actual random data.

## Validation sets
The way it's done correctly, is to split the training data into two, again, for example, split the [[CIFAR-10]] dataset into three: {49000:training, 1000:validation, 10000:test}.

The validation set is used as a fake test set, and in that way we can tune our hyperparameters to fit the training and validation sets, and when we think we have the perfect values, we can use the unknown data from the test set.

## Small datasets

If the available dataset is very small, the validation set will also be small. Therefore we can use, what's called, cross-validation.
Cross-validation is done by splitting the validation data into x equal parts, for example 5 parts. We then iterate over the classifier where fold 1 is the validation, then fold 2 is the validation, and so on, and average out the performance of the different fold.

This is computationally expensive, so generally avoided in the practice, but ultimately comes down to the validation set size. If the set size is very small (~100-200) cross-validation is used, but if it's larger, it's not used.

