# Multiclass loss function

The default learner for image processing provided by fastai used is vision_learner. [See documentation here.](https://docs.fast.ai/vision.learner.html)
```
vision_learner (dls, arch, normalize=True, n_out=None, pretrained=True,
                 weights=None, loss_func=None, opt_func=<function Adam>,
                 lr=0.001, splitter=None, cbs=None, metrics=None,
                 path=None, model_dir='models', wd=None, wd_bn_bias=False,
                 train_bn=True, moms=(0.95, 0.85, 0.95), cut=None,
                 init=<function kaiming_normal_>, custom_head=None,
                 concat_pool=True, pool=True, lin_ftrs=None, ps=0.5,
                 first_bn=True, bn_final=False, lin_first=False,
                 y_range=None, n_in=3)
```
Vision_learning uses a pre-trained model to define a new Learner.

An example of applying vision_learning for image processing is as below:

```
learn = vision_learner(dls, resnet34, metrics=accuracy_multi)
learn.fine_tune(3)
```
Where:
- dls is the Data block dataloarder with the resized images and specified batch size.
- rsenet is the residual network that influences the neural network and is set to 34 (see [More on resnet](More-on-resnet) for more info) 
- metrics is defined as error_rate for a single classifier and accuracy_multi for a multi classifier. [See more on metric options here.](https://docs.fast.ai/metrics.html#multi-label-classification)
- parameter in fine tune determines the number of epochs (how many times the data is iterated through) (see [Epoch vs Batch Size](Epoch-vs-Batch Size) for more info) 

In this code we haven't define the loss-function for fastai to use so fastai chooses its own appropriate loss function
based on the kind of data and model you are using. For the scenario of categorising images, fastai uses cross-entropy loss as default.

This is desired as 
a) cross-entropy loss works for binary or multi-class categorising
b) provides fast and reliable training results

## Epoch vs Batch Size
Iteration (or Batch): Training data is divided into smaller chunks called batches. One iteration involves processing a single batch of data through the model and updating the model's weights based on the calculated loss and gradients.

Epoch: An epoch is completed when the model has processed every single batch in the training dataset exactly once. So, if your training dataset has 1000 samples and you use a batch size of 100, one epoch will consist of 1000 / 100 = 10 iterations.

## More on resnet
Commonly used resnets are: ResNet18, ResNet34, ResNet50, ResNet101, ResNet152.
Changing the resnet to say 152 increases the number of layers and parameters within the neural network but this comes at the cost of higher computation time and memory but aims for a more accurate outcome. For a small dataset such a large residual network number is not needed to get the accuracy required.

The purpose of resnet is to help mitigate the vanishing gradient problem and enables the training of networks with hundreds or even thousands of layers without significant degradation in performance. 

The vanishing gradient problem is when the gradients calculated with respect to the weight becomes infinitely small due to the large number of layers which causes issues like slow/no convergence, poor performance or inaccurate models.

Without ResNet, each layer learns a direct mapping from input to output. With ResNet, it encourages layers to learn a residual mapping. This means the layers learn the difference between the input and the desired output while allowing the network to easily skip layers that are not contributing to the learning process. This allows networks to use more layers (become deeper) to improve the accuracy of the models while maintaining the stability of convergence and a reasonable runtime cost.

# Cross-Entropy Loss



