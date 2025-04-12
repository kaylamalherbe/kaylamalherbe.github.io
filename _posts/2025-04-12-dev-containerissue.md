# Issues with Dev Containers
When you create a new dev container it doesn't have extra packages like jupyter or pip installed so sometimes the kernel won't work when you open a new package and it comes up with an error saying:
"Running cells with 'Python 3.10.12' requires the ipykernel and pip package"

My solutions to this was running these commands in bash and then restarting Vs code
```
sudo apt update
sudo apt install python3-pip
pip install ipykernel
```

after this make sure to open wsl again, rebuild and reopen in dev container to make sure its properly set up.

If all else fails, reclone the repo and reopen the dev container.

## NOTE:
Need to use gpufrozen not gpu... 

## Second note:
patience is key, it takes a while to run some code
