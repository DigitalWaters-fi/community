# Persistent Conda Environment in Jupyter (Kubernetes / JupyterHub)

This guide shows how to create a **persistent Conda environment** that survives **pod or server restarts**.

---

## 1️⃣ Create a Persistent Directory for Conda Environments

```bash
mkdir -p /home/jovyan/conda-envs
```

All new environments will live here and **persist across pod restarts**.

---

## 2️⃣ Create the Environment

```bash
conda create -p /home/jovyan/conda-envs/myenv python=3.10 -y
```

- `-p` specifies the **exact installation path**.
- You can create multiple environments like:

```
/home/jovyan/conda-envs/myenv
/home/jovyan/conda-envs/myenv2
/home/jovyan/conda-envs/myenv3
```

---

## 3️⃣ Activate the Environment

```bash
source activate /home/jovyan/conda-envs/myenv
```

---

## 4️⃣ Install `ipykernel`

```bash
conda install ipykernel -y
```

This allows the environment to appear as a **Jupyter kernel**.

---

## 5️⃣ Register the Environment as a Jupyter Kernel (Persistent)


```bash
python -m ipykernel install \
  --prefix=/home/jovyan/.local \
  --name myenv \
  --display-name "Python (myenv)"
```

This creates the kernel specification at:

```
/home/jovyan/.local/share/jupyter/kernels/myenv
```

Since `/home/jovyan` is persistent, the kernel will **survive server restarts**.

---

## 6️⃣ Verify Installation

```bash
jupyter kernelspec list
```

Expected output:

```
Available kernels:
  python3      /opt/conda/share/jupyter/kernels/python3
  myenv        /home/jovyan/.local/share/jupyter/kernels/myenv
```

---

✅ Your environment is now **persistent and available as a Jupyter kernel**.
