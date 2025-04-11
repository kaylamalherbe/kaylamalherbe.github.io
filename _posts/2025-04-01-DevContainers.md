# Dev Container
Up until this course I've used a lot of virtual environments both in Uni and work. Moslty I familiarised myself with conda (anaconda)
but have also started uses offsprings of this such as miniforge/miniconda due to licensing. I've found these package controls very helpful
when setting up different python versions with different packages but still find that the packages needs constant updates, they are always conflicting
and it is incredibly tediuous to update the python version. In addition, the packages cannot be reached without the environments which makes 
using certain functions different when running threads, parallel cmd promts and multi gpu processing. 

## First experience with Dev Containers
Following Brian Lovell's instructions, dev containers were way way more simple than I could've expected. No extra packages needed,
no random pip lines and no restarting 1000 times. I ran into some space issues when I tired to set it up on my home laptop but after
doing it on the lab computers everything ran super smoothly. Best thing is if you stuff up you can just open a new Dev container.
Initalially the loading takes quite long but after the first load, its super quick which is desirable.


## New Container for each branch
Interesting things I found out was that each new branch requires a new dev container. For example comparing the cpufrozen vs gpufrozen branches with the same code requires the dev container to be reopened, everything be reimported and extensions be reloaded then all previously code needs to be run again. This is basically instant on the GPU but on the CPU branch running things takes a while so its a bit frustrating.
