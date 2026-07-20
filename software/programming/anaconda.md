# Anaconda

## Installation

* https://docs.anaconda.com/anaconda/install/
* https://www.anaconda.com/docs/getting-started/anaconda/install/linux-install
* Repo archive: https://repo.anaconda.com/archive/
* Installation video: https://www.youtube.com/watch?v=sU2mXjOB-fA

### Download the installation file
```bash
wget https://repo.anaconda.com/archive/Anaconda3-2025.12-2-Linux-x86_64.sh
```

### Check integrity of the file
```bash
shasum -a 256 ~/<INSTALLER-FILENAME>
shasum -a 256 Anaconda3-2024.10-1-Linux-x86_64.sh
shasum Anaconda3-2024.10-1-Linux-x86_64.sh

```
	* Compare it with https://repo.anaconda.com/archive/

### Normal Installation
```bash
bash ~/Anaconda3-2025.12-2-Linux-x86_64.sh
bash Anaconda3-2025.12-2-Linux-x86_64.sh
```

```bash
bash /Downloads/Anaconda-latest-Linux-x86_64.sh
```
	
### Install in another directory
```bash
sudo bash Anaconda3-2024.10-1-Linux-x86_64.sh -f -b -p /Programs/anaconda3
```

### Refresh terminal
```bash
source ~/.bashrc
```

### List of packages installed with anaconda
```bash
conda list
```


## Anaconda commands

```bash
# Create--
conda create -name ENV_NAME python=python_version
conda create -n ENV_NAME python=python_version

# ActivateEnvironments--
conda activate

# See-list-libraries
conda list

# Activate-Specific-Environment--
conda activate <env_name>

# List-all-the-environments--
conda env list

# Deactivate-environment--
conda deactivate

# Update---
conda update -n base -c defaults conda

# Delete-environment--
conda remove --name ENV_NAME --all

# Delete-environment with libraries--
conda remove --n ENV_NAME --all

# Install packages
conda install <package>
```

**References**
* https://docs.conda.io/projects/conda/en/latest/user-guide/concepts/installing-with-conda.html

## Environments
### Create environments

```bash
conda create --name <my-env>
```

With an specific Python version
```bash
conda create -n myenv python=3.8
```
#### Delete environment
```bash
conda remove --name ENV_NAME --all
```

`ENV_NAME` denotes the name of the environment to be removed/deleted. Make sure you deactivate an environment before removing it by running the `conda deactivate` command.

The `--all` flag removes all the packages installed in that environment.

Here's a summary of the steps involved in deleting an environment in Conda:

- Deactivate the environment using the `conda deactivate` command.
- Delete the environment using the `conda remove --name ENV_NAME --all` command.

**References**
* https://www.freecodecamp.org/news/how-to-delete-an-environment-in-conda/

### Examples
```bash
Examples:  
  
Remove the package 'scipy' from the currently-active environment::  
  
   conda remove scipy  
  
Remove a list of packages from an environment 'myenv'::  
  
   conda remove -n myenv scipy curl wheel  
  
Remove all packages from environment `myenv` and the environment itself::  
  
   conda remove -n myenv --all  
  
Remove all packages from the environment `myenv` but retain the environment::  
  
   conda remove -n myenv --all --keep-env
```
