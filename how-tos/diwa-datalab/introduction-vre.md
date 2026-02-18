# Getting started on the DIWA DataLab
The [Digital Waters](https://digitalwaters.fi) flagship and pilot, in collaboration with [CSC – Finnish Center for Informatics in Science](https://csc.fi) has developed a JupyterHub based virual reasearch environment to accelerate research, promote FAIR and Open Science best practices within the flagship, facilitate collaboration, and co-develop digital twin services. We're calling this service the [DIWA DataLab](https://diwa-data-lab-vre.rahtiapp.fi/hub/login?next=%2Fhub%2Fhome), and it is available to use for research and development.

## Why use the DIWA DataLab?
A **Virtual Research Environment (VRE)** offers several clear advantages for the researcher community, especially in large consortium like the Digital Waters Flagship where collaboration )both on individual research projects and in co-development of digital twin services) is core to our mission.

1. **Easy Access Anywhere** – You can work from any computer with a web browser; no need to install complex software locally. Your workspace and files are in the cloud.

2. **Reproducibility** – A VRE ensures that the computing environment (software versions, tools, packages) is the same for all team members. This makes experiments and analyses easier to reproduce and verify.

3. **Collaboration** – Multiple researchers can share the same workspace, data, and tools, reducing the risk of mismatched versions or duplicated efforts.

4. **Data Safety** – Persistent storage (PVCs) keeps your files safe even if your session ends. This prevents work and data loss from failures of individual PCs.

5. **Resource Management** – Researchers can access more computing power (CPU, GPU, memory) than might be available on their personal machines, which is useful for processing large datasets or simulations, and can help you develop scalable tools.

6. **Pre-Configured Tools** – VREs use images with software and packages already installed, saving time on setup and reducing technical barriers. As we develop more data processing and modelling tools within the flagship, more software will be added to accelerate our research.

7. **Scalability & Flexibility** – You can quickly start new instances for experiments, adjust resources, or switch between different software environments as needed.

8. **Focus on Research** – By handling infrastructure, updates, and compatibility automatically, a VRE allows researchers to focus on **science instead of system administration**.

In short, a VRE is like having a **ready-to-use, secure, and sharable lab in the cloud**, designed to save time, improve collaboration, and make research more reproducible.

## Useful terms:
1. Server – The “workspace” that runs for a user, letting them access tools, write documents, and run experiments. Think of it as a personal computer in the cloud. 
2. Instance – A single active copy of that workspace. When you log in, an instance is created for you to work in. 
3. Image – A pre-packaged setup that includes the operating system and any tools you need. It’s like a pre-configured computer you can start instantly.
4. PVC (Persistent Volume Claim) – A way to save your files and data safely, even if the workspace is closed or restarted. It’s like a personal folder in the cloud. You have 500 GB of PVC with each server. Anything you save in your server will be available next time you log in, and these files can be accessed from any image.
5. Software – The applications or programs available in the image, like data analysis tools, simulation software, or text editors. You can use the images that we provide, suggest new images for us to build, or upload your own.
6. Packages – Extra add-ons or modules that expand what the software can do. For example, if the software is a drawing tool, packages might add new brushes or shapes. You can install your own packages into any image and they will be there for you next time you log in. Learn more about installing packages in the DIWA DataLab [here](https://github.com/DigitalWaters-fi/community/tree/main/how-tos/install-packages-guides)

# Signing up for the VRE
The DIWA DataLab is accessible via GitHub. To get access to the DIWA DataLab, create a user account on GitHub.com, and request to join the DigitalWaters-fi GitHub organization [here](https://forms.office.com/Pages/ResponsePage.aspx?id=muScnwFRo0qMdQ1ZNa1lJWEtMFscU0JOr8HqIPYV7uJUN0xYMlpTMVBKOTI2MUVJOFpNMkZaNUdOSi4u). Detailed instructions on how to create a professional GitHub profile, and integrate these credentials into the DIWA DataLab, can be found [here](https://github.com/DigitalWaters-fi/community/tree/main/how-tos/connect-vre-github).

# Features of the DIWA DataLab
## Launch page
Use the landing page to log in to the DIWA DataLab using your GitHub credentials. Please note that we require users to have 2FA (two-factor authentication) set up on their GitHub account. If you aren't a member of the DigitalWaters-fi GitHub organization, use the "Sign up" form to request access. <img width="1911" height="901" alt="image" src="https://github.com/user-attachments/assets/2e9b5cde-c4aa-414d-ba23-3aba9b43386c" />

Once you are in the DIWA DataLab, click "Launch My Server"

## Select an image
Each one of the tiles viewable in your server represent an image: a virtual workspace in the cloud that includes an operating system and some software that we've selected because we think will be useful to you.
<img width="1502" height="822" alt="image" src="https://github.com/user-attachments/assets/c6a926ea-1127-46d5-bc1c-368c58e7ea96" />

**We have three four types of images in the DIWA DataLab.**
1. Notebook based images: these will give you access to a terminal, some basic software, and notebook IDEs to write code in R, Python, or Julia.
2. Desktop based images: these will launch an Ubuntu desktop, where you can select software using a graphical user interface. Software that requires a GUI, like QGIS and CloudCompare, can be accessed here.
3. Process model images: the DIWA Engineering Team and researchers are working to develop a scalable, source-to-sea virtualization of the hydrosphere in the form of coupled process models with a data assimilation system. As we add more proess models to this framework, these will appear as images here.
4. Build your own images: you can upload your own Docker or Singularity containers and run them here.

**Wait, I don't see my software in any of these images...what do I do?**
Reach out! We need to hear from you to learn more about your workflows. Please suggest software, packages, or any additional features you'd like to see hosted on the DIWA DataLab using GitHub [Discussions](https://github.com/orgs/DigitalWaters-fi/discussions/1), by raising an [Issue](https://github.com/DigitalWaters-fi/.github/issues), or by email: diwa-vre@lists.oulu.fi.

## Instance image + size
After you've selected the image (software and packages) you want to run on your server, you will see a drop down menu allowing you to pick an image **size**: how much CPU and RAM will be available to you. This allows you to scale up or down your computer power as needed. To conserve resources, please always selected the smallest effective size for your project. If you need more compute power than our current options indicate, email diwa-vre@oulu.fi with your GitHub username and allocation request, and we'll work to get that updated ASAP.

## Notebook images
An interactive notebook (aka Jupyter Notebook or R Markdown) is a digital document that lets you combine text, code, and results in one place and immediately see the output of your work, richly formatted like a website. It’s called “interactive” because it is not just a pretty webpage, it is an integrated development environment (IDE) you can change the code or inputs and instantly run it to see updated results.

* **Markdown cells**: allow you to write and present formatted text and equations, embed URLs, videos, and images. This is a place to communicate your research and explain your code and results. Learn more about Markdown [here](https://www.markdownguide.org/)
* **Code cells**: are where you write and execute code in either R, Python, or Julia. This is how you read data into your workspace, process data, train and run models, and prepare text-based figures visualizing results. Are you new to scientific computing? Learn the ropes in Python using [The Python Data Science Handbook by Jake VanderPlas](https://github.com/jakevdp/PythonDataScienceHandbook?tab=readme-ov-file)

### Installing packages and libraries


### Managing environments and Kernels
An **environment** is an isolated workspace with its own: software (R, Python) version, installed packages (and versions), and dependencies (and versions). Environments are an important part of reproducible scientific workflows, because they allow someone to run your code without having to install specific packages or manage dependency chain conflicts. As the libraries behind your research evolve and change, working in software environments will ensure that your code still runs in the future.

We have provided you with a few environments that support many functions in geoscientific computing. If you install a package from within an environment, that package will be saved to your image, and you won't have to install it again.

To open an environment from within your Jupyter Notebook interface, select the kernel in the upper right hand corner:

Or using the main menu:

Learn more about managing environments, and making them discoverable as kernels in your notebook images, [here](https://github.com/DigitalWaters-fi/community/tree/main/how-tos/install-packages-guides)

## Desktop images
## Saving data and files
## Syncing git with GitHub
## Reporting bugs
## Ask for help with research computing
## Demo Video



