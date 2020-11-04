# pres-mc

An attempt to create MC stack for the PRES experiment.

## Software installation guide

Suppose one have a fresh Ubuntu 20.04 LTS installation and a root access. 
Run as a root-user:
```bash
apt update
apt upgrade
apt install git
useradd -m user
passwd user
adduser user sudo
su user
```
Last command switch you to a user account.

As a user you have to download Miniconda scripts, requirements list and setup envoirement. Here is a stack of commands:
```bash
wget http://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
sh Miniconda3-latest-Linux-x86_64.sh
source path-to-miniconda/etc/profile.d/conda.sh
conda config --add channels conda-forge
mkdir pres-mc
cd pres-mc
wget http://adzyuba.web.cern.ch/adzyuba/d/pres-mc-requirements.txt
conda create --name pres-mc
conda activate pres-mc
conda install --yes --file pres-mc-requirements.txt
git clone https://github.com/gramolin/esepp.git
cd esepp
```

Nest step is to download and compile ESEPP event generator:
```bash
git clone https://github.com/gramolin/esepp.git
cd esepp
make
```
