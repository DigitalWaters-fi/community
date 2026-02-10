Install Packages

This guide explains how to create and activate Python environments and install packages in JupyterHub using:

Conda (Micromamba) – recommended

Python virtual environments (venv)

pip

Prerequisites (Required Once for Conda)

Before using conda activate, users must initialize their shell.

Run the following commands once:

echo 'source /etc/profile.d/micromamba.sh' > ~/.bashrc
source ~/.bashrc


This enables the conda activate command in JupyterHub terminals.

⚠️ If conda activate does not work, use the fallback:

source activate <env-name>

Conda Environments (Recommended)
Create a Simple Conda Environment (Default Python)

Create an environment without specifying a Python version:

conda create -n simple-env


Activate:

conda activate simple-env


Fallback:

source activate simple-env

Create a Conda Environment with a Specific Python Version
conda create -n myenv python=3.10


Example with packages:

conda create -n data-env python=3.9 numpy pandas matplotlib

Activate a Conda Environment
conda activate myenv


Fallback:

source activate myenv


Verify activation:

which python
python --version

Install Packages with Conda
conda install numpy
conda install pandas scipy scikit-learn
conda install -c conda-forge xarray

pip Installation (Inside Conda or venv)

Always activate your environment first.

pip install requests
pip install fastapi uvicorn
pip install -r requirements.txt


Upgrade pip (recommended):

pip install --upgrade pip

Python Virtual Environments (venv)

Use venv if Conda is unavailable or not required.

Create a Python Virtual Environment
python -m venv py-env


Or specify Python version:

python3.10 -m venv py-env

Activate the Python Virtual Environment
Linux / macOS (JupyterHub)
source py-env/bin/activate


To deactivate:

deactivate

Install Packages with pip (venv)
pip install numpy pandas matplotlib
pip install -r requirements.txt

Example: Full Conda Workflow
# One-time shell setup
echo 'source /etc/profile.d/micromamba.sh' > ~/.bashrc
source ~/.bashrc

# Create environment
conda create -n ml-env python=3.10

# Activate environment
conda activate ml-env
# or: source activate ml-env

# Install packages
conda install numpy pandas scikit-learn
pip install xgboost

Example: Simple Conda Environment Workflow
conda create -n simple-env
conda activate simple-env
conda install numpy pandas

Example: Python venv Workflow
python -m venv py-env
source py-env/bin/activate
pip install numpy pandas matplotlib

Notes & Best Practices

Always activate an environment before installing packages

Prefer Conda for scientific and data-science libraries

Use pip for packages not available in Conda

Do not install packages into the system Python

Do not mix packages across environments
