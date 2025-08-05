# How to use Harvard HPC
I'm summarizing some notes from [here](https://github.com/alexandergagliano/summer-school-2024/tree/main/computing)

There is an official HPC guide [here](https://www.psc.edu/resources/bridges-2/user-guide/)

## Login
### SSH
```
ssh -Y <USER_NAME>@bridges2.psc.edu
```

### OnDemand (GUI)
Go to https://ondemand.bridges2.psc.edu/.

It defaults to 8 GPUs typically. But if you want to change it, in `Extra Slurm Args` add
```
--gres=gpu:<NUM_GPUs>
```

## Package Mangement
### Quick
There are "AI-ready" environments. To see them:
```
module avail AI
```
You then perform (for example)
```
module load AI/pytorch_23.02-1.13.1-py3
```
You can also `pip install` into your base environment

### Proper (Conda)
PSC has a couple ways to do package management. Singularity (eww) and conda. 

Here I'll go over Conda. The TLDR is that is acts like normal conda 🎉.

First load conda.
```
interact # Start interactive session
module load anaconda3 # Load anaconda
```
Now you can create an environment.
```
conda create --name <ENV_NAME> python=3.11
conda activate <ENV_NAME>
```
Now you can pip install
```
python -m pip install ipykernel
python -m pip install <PACKAGE_NAME> --user
```








