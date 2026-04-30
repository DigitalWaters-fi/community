# Use `repo2docker` to jump-start reproducibility

`repo2docker` is a utility maintained by Project Jupyter that creates stable Docker images based on [standard configuration files(https://repo2docker.readthedocs.io/en/latest/configuration/#config-files). It is suitable for Python, R, Python and R, and Julia environments, and can also install Linux packages if needed.

In this tutorial, you will use the [`repo2docker` GitHub Action](https://github.com/jupyterhub/repo2docker-action/blob/master/README.md) to build a reproducible image, deploy it to to DockerHub, and the start up a container with your environment on the DIWA VRE.

## 1. Set up your accounts

You will need a [GitHub account](https://github.com/signup?source=login) if you don't have one already to complete this tutorial. You can then use that GitHub Account to create  a [DockerHub account](https://app.docker.com/signup), and a [DIWA VRE account](https://diwa-data-lab-vre.rahtiapp.fi/hub/login). You can use the GitHub Account to create both the DIWA VRE account and the DockerHub account.

All prerequisites:

1. GitHub Account (with 2-Factor Authentication, added to the DigitalWaters-fi organization)
2. A DIWA Data Lab (VRE) account
3. A **DockerHub** account


