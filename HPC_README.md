# How to use Harvard HPC
I'm summarizing some notes from [here] (https://github.com/alexandergagliano/summer-school-2024/tree/main/computing)

## Login
### SSH
```
ssh -Y cmiyamot@bridges2.psc.edu
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
```
conda env -n <ENV_NAME> python=3.11
conda activate <ENV_NAME>
```
Now you can pip install
```
python -m pip install <PACKAGE_NAME> --user
```








