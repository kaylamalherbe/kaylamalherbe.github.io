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

## GPU vs GPUfrozen
Make sure you use GPUfrozen instead of GPU... this won't work in the dev containers

## Key Note:
patience is key, it takes a while to run some code/reopen containers/make sure everything is imported

## If All Else Fails
If your system is not working properly, try rebooting the WSL subsystem with:
```
wsl --shutdown
```
A popup window will then ask you to restart wsl. This often fixes it. After restarting wsl, you can restart docker desktop.
