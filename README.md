# Model_-Caliberation

When dealing with a classification problem, collecting only the predictions on a test set is hardly enough; more often than not we would like to compliment them with some level of confidence. To that end, we make use of the associated probability, meaning the likelihood calculated by the classifier, which specifies the class for each sample. But does this always reflect reality? And if not, how can we tell?


Imagine we have two binary classifiers; model A and model B. Model A is 85% accurate and 0.86 confident for each prediction it makes. On the other hand, model B is also 85% accurate but 0.99 confident for each of its predictions. Which model do you think is better?

In this story, I will try to convince you that model A is better. Model A considers itself precise 86% of the time and indeed, that's almost the case. To the contrary, model B is overconfident about its predictions. This toy example demonstrates the intuition behind probability and model calibration.

Model calibration refers to the process where we take a model that is already trained and apply a post-processing operation, which improves its probability estimation. Thus, if we were to inspect the samples that were estimated to be positive with a probability of 0.85, we would expect that 85% of them are in fact positive.

Formally, a model is perfectly calibrated if, for any probability value p, a prediction of a class with confidence p is correct 100*p per cent of the time.


Model calibration is important only if you care about the probabilities your model computes. For instance, let us say that you are building a recommender engine, that ranks products according to user preferences. If your model estimates that user u will buy product a with probability 0.9, and item b with probability 0.7, you can go ahead and serve product a first. No need to calibrate that model.
