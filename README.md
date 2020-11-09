# pres-mc

An attempt to create MC stack for the PRES experiment.

## Prerequisites:
64-bit Linux installation (tested on Ubuntu 20.04 LTS 64-bit)
Git

## Software installation guide


**Note:** If you use cloud-based installation it's better not to update the cloud scripts.

First you have to install and update conda. Here are the commands:
```bash
wget http://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
sh Miniconda3-latest-Linux-x86_64.sh
source ~/miniconda3/etc/profile.d/conda.sh # replace "~/miniconda3/" with your conda path if you've changed it
conda config --add channels conda-forge
conda update -n base -c defaults conda
```
**Note:** If you close your shell you will have to run conda.sh again; alternatively, you can run "conda init" to make the script run automatically each time you open your shell, for more information run "conda init --help"


Next step is to setup the environment and install the requirements.
```bash
cd # you may want to choose other directory
git clone https://github.com/aleksha/pres-mc.git
cd pres-mc
conda create --name pres-mc
conda activate pres-mc
conda install --yes --file requirements.txt
```

Next step is to download and build ESEPP event generator:
```bash
cd
git clone https://github.com/gramolin/esepp.git
cd esepp
make
```

## Links
 - https://releases.ubuntu.com/20.04/
 - https://docs.conda.io/en/latest/miniconda.html
 - https://root.cern.ch/
 - https://geant4.web.cern.ch/
 - https://github.com/gramolin/esepp.git
