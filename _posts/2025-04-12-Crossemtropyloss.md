# Cross-Entropy Loss
In some other examples discussed, the default vision learner provided by fastai was used:
```
learn = vision_learner(dls, resnet34, metrics=error_rate)
learn.fine_tune(2)
```
In this code we haven't define the loss-function for fastai to use so fastai chooses its own appropriate loss function
based on the kind of data and model you are using. For the scenario of categorising images, fastai uses cross-entropy loss as default.

This is desired as 
a) cross-entropy loss works for binary or multi-class categorising
b) provides fast and reliable training results


