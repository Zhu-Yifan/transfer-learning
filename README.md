# Transfer Learning for re-constructing LineP
The repo contains codes and resources related to **Transfer Learning** method used to reconstruct monthly data products
from historical [LineP](https://www.waterproperties.ca/linep/) observations during the *Reconstructing Line P: A Virtual Hackathon*. 
---
## Overview
The project applies a **Transfer Learning** approach in which a larger model is first pre-trained on similar oceanographic datasets
(e.g., other transects or NEP Argo profiles) to capture general spatial–temporal patterns, and is then fine-tuned using Line P
observations to adapt the model to local conditions.

---

## Workflow

### (1) install conda
You need to have anaconda or miniconda in your machine. Anaconda is a great way to get python, follow the directions here: 
https://www.anaconda.com/docs/getting-started/anaconda/install

On the linux machines don't put it in your home (~) folder because there is not much disk space there. 
The initialization adds some lines to your ~/.bashrc, or ~/.bash_profile

### (2) install Git
You will also need git, which you may or may not have. To find out if you have it, type which git in the terminal and see if it finds anything. 
If you need to get it you can install it easily by doing:
```bash
conda install -c conda-forge git
```
### (3) get the code from Git
On your machine, first go to wherever you want the ***LineP*** repo to end up. In my case, on one of our linux machines adroa,
I put it in /b1/yifan which is my working directory. On the linux machines don't put it in your home (~) 
folder because there is not much disk space there. When you are at whatever place you have decided on do:
```bash
git clone https://github.com/Zhu-Yifan/transfer-learning.git
```
and lineP and all its sub-folders will appear. To get any changes I may make, go to any folder in lineP and do:

git pull

### (4) create lineP environment

Create an environment that has all the modules required for this code by going to folder LineP and executing:
```bash
conda env create -f lineP.yml > env.log &
```
the lineP.yml includes necessary python packages like tensorflow, git, numpy, xarray, etc.

Then do:  
```bash
conda activate lineP
```
if you want to use this environment all the time, add the above line to your .bashrc or .bash_profile, 
and "source" it. Now (lineP) will appear at the start of your bash prompt.

### (5) Transfer learning Architecture

#### `***.ipynb`

This is the notebook to read process ctd, bottle, and argo float data. and normalize, split dataset into training and testing, 
and pre-train model.



