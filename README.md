# pres-mc

An attempt to create MC stack for the PRES experiment.

## Software installation guide

Suppose one have a fresh Ubuntu 20.04 LTS 64-bit installation and a root access. 
Run as a root-user:
```bash
apt update
apt upgrade
apt install git
useradd -m user
passwd user
adduser user sudo
su user
bash
cd
```
Last couple of commands switch you to a user account, init bash session and bring you into your home directory.
**Note:** If you use cloud-based installation it's better not to update cloud scripts.

As a user you have to download Miniconda scripts, setup and update conda. Here is a stack of commands:
```bash
wget http://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
sh Miniconda3-latest-Linux-x86_64.sh
source /home/user/miniconda3/etc/profile.d/conda.sh
conda config --add channels conda-forge
conda update -n base -c defaults conda
```

Next step is to download a list of requirements and setup pres-mc envoirement.
```bash
cd /home/user
git clone https://github.com/aleksha/pres-mc.git
cd pres-mc
conda create --name pres-mc
conda activate pres-mc
conda install --yes --file pres-mc-requirements.txt
```

Nest step is to download and compile ESEPP event generator:
```bash
cd /home/user
git clone https://github.com/gramolin/esepp.git
cd esepp
make
```

## Links on software
 - https://releases.ubuntu.com/20.04/
 - https://docs.conda.io/en/latest/miniconda.html
 - https://root.cern.ch/
 - https://geant4.web.cern.ch/
 - https://github.com/gramolin/esepp.git
