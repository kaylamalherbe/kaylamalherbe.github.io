# GPU Activity
The gpu activity can be tracked with the following code segments:
```
nvidia-smi
```
Running nvidia will give useful information about your gpu such as driver version, how many processes are happening, GPU memory usage

The real gpu tracking is nvtop:
```
nvtop
```
nvtop will bring up a live graph to track the the gpu which gives good intel including memory and gpu usage.

For example running pet_breeds from the fastbook. Downloading the data uses 25%
![GPU usage](/images/gpu_usage_pet.png)
