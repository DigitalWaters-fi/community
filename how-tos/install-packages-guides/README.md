# Install Packages

This guide explains how to create and activate Python environments and install packages in JupyterHub using Conda (Micromamba), Python venv, and pip.

---

## Prerequisites (Required Once for Conda)

Before using `conda activate`, users must initialize their shell.

Run the following commands once:

```bash
echo 'source /etc/profile.d/micromamba.sh' > ~/.bashrc
source ~/.bashrc
```

This enables the `conda activate` command in JupyterHub terminals.

If `conda activate` does not work, use the fallback:

```bash
source activate <env-name>
```

---

## Conda Environments (Recommended)

### Create a Simple Conda Environment (Default Python)

Create an environment without specifying a Python version:

```bash
conda create -n simple-env
```

Activate:

```bash
conda activate simple-env
```

Fallback:

```bash
source activate simple-env
```

---

### Create a Conda Environment with a Specific Python Version

```bash
conda create -n myenv python=3.10
```

Example with packages:

```bash
conda create -n data-env python=3.9 numpy pandas matplotlib
```

---

### Activate a Conda Environment

```bash
conda activate myenv
```

Fallback:

```bash
source activate myenv
```

Verify activation:

```bash
which python
python --version
```

---

### Install Packages with Conda

```bash
conda install numpy
conda install pandas scipy scikit-learn
conda install -c conda-forge xarray
```

---

## pip Installation (Conda or venv)

Always activate your environment before using pip.

```bash
pip install requests
pip install fastapi uvicorn
pip install -r requirements.txt
```

Upgrade pip (recommended):

```bash
pip install --upgrade pip
```

---

## Python Virtual Environments (venv)

Use venv if Conda is unavailable or not required.

### Create a Python Virtual Environment

```bash
python -m venv py-env
```

Or specify Python version:

```bash
python3.10 -m venv py-env
```

---

### Activate the Python Virtual Environment

Linux / macOS (JupyterHub):

```bash
source py-env/bin/activate
```

Deactivate:

```bash
deactivate
```

---

### Install Packages with pip (venv)

```bash
pip install numpy pandas matplotlib
pip install -r requirements.txt
```

---

## Example: Full Conda Workflow

```bash
echo 'source /etc/profile.d/micromamba.sh' > ~/.bashrc
source ~/.bashrc

conda create -n ml-env python=3.10
conda activate ml-env

conda install numpy pandas scikit-learn
pip install xgboost
```

---

## Example: Simple Conda Environment Workflow

```bash
conda create -n simple-env
conda activate simple-env
conda install numpy pandas
```

---

## Example: Python venv Workflow

```bash
python -m venv py-env
source py-env/bin/activate
pip install numpy pandas matplotlib
```

---

## Notes & Best Practices

- Always activate an environment before installing packages
- Prefer Conda for scientific and data-science libraries
- Use pip for packages not available in Conda
- Do not install packages into the system Python
- Do not mix packages across environments
