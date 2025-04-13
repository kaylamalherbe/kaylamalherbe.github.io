# GPU Tracking
The gpu activity can be tracked with the following code segments:
```
nvidia-smi
```
Running nvidia will give useful information about your gpu such as driver version, how many processes are happening, GPU memory usage

![nvidia-smi output](/images/nvidi-smi.png)

To see real time GPU tracking, call nvtop:
```
nvtop
```
nvtop will bring up a live graph to track the the gpu which gives good intel including memory and gpu usage.

For example running pet_breeds from the fastbook. Downloading the data uses 25%
![GPU usage](/images/GPU_usage.png)

## ISSUES:
A issue that can occur in this process is if the gpu reachs 100% memory the remote laptop will kick you off the server. If this happens just exit the server what a few minutes and sign in again. 

![GPU Full memory Error](/images/GPU_error.png)

The the server doesn't kick you out and the GPU memory is full. An error like this might occur:
```
---------------------------------------------------------------------------
OutOfMemoryError                          Traceback (most recent call last)
Cell In[17], line 2
      1 learn = vision_learner(dls, resnet34, metrics=accuracy_multi)
----> 2 learn.fine_tune(3)
```

The solution to this is to simply restart the kernal which will get rid of any previously stored models.
