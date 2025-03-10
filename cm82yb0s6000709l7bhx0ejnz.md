---
title: "How to Manage Virtual Environments in JupyterLab: Introduction to JUNO"
seoTitle: "How to Manage Virtual Environments in JupyterLab: Introduction to JUNO"
seoDescription: "Learn how JUNO simplifies virtual environment management in JupyterLab, enhancing reproducibility and collaboration in data science workflows"
datePublished: Mon Mar 10 2025 11:00:22 GMT+0000 (Coordinated Universal Time)
cuid: cm82yb0s6000709l7bhx0ejnz
slug: how-to-manage-virtual-environments-in-jupyterlab-introduction-to-juno
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1740957965831/b192407a-fab9-441f-b445-850722054c53.png
tags: ai, python, data-science, efficiency, notebook, jupyter-notebook, jupyterlab, environment-setup

---

As someone who has spent countless hours wrestling with Python dependency conflicts in [Jupyter](https://jupyter.org/) notebooks, I've felt the unique pain that comes with hearing "but it works on my machine" when sharing notebooks with colleagues. The problem isn't just annoying—it's a fundamental barrier to reproducible data science.

That's why I was excited to discover [JUNO](https://github.com/velocitatem/juno), a tool that elegantly solves one of the most persistent challenges in the Jupyter ecosystem: managing virtual environments and packages directly within JupyterLab.

## The Virtual Environment Problem

If you've used Jupyter notebooks for any serious data science work, you've likely encountered these frustrating scenarios:

* Installing a package breaks your existing notebooks because of version conflicts
    
* Sharing notebooks that work perfectly for you but fail for colleagues
    
* Maintaining multiple projects with different dependencies
    
* Switching between different Python versions for specific projects
    

Traditional solutions involve creating separate virtual environments outside of Jupyter, then manually registering kernels—a process that's error-prone and requires command-line gymnastics.

## Enter JUNO: Virtual Environments Made Simple

JUNO reimagines how we manage environments in JupyterLab by integrating virtual environment creation and package management directly into the interface.

### Key Features

JUNO provides an intuitive UI for:

1. Creating and managing new isolated environments
    
2. Installing and managing packages with a visual interface
    
3. Switching between environments seamlessly
    
4. Sharing environment specifications for reproducibility
    

## Hands-On: Getting Started with JUNO

Let's walk through a typical workflow to see how JUNO simplifies environment management.

### Installation

```bash
pip install juno-manager
```

### Creating a New Environment

Instead of the traditional approach:

```bash
# The old way
python -m venv my_new_env
source my_new_env/bin/activate
pip install ipykernel
python -m ipykernel install --user --name my_new_env
jupyter lab
```

With JUNO, you simply:

1. Open `juno-manager`
    
2. Name your environment and specify which packages to install (you can also do this later)
    
3. Verify your environment was created and add any other packages directly if you want
    

Behind the scenes, JUNO handles the virtual environment creation and kernel registration automatically.

## Real-World Use Case: Managing ML Project Dependencies

Recently, I was working on a machine learning project that required TensorFlow for one notebook and PyTorch for another. Before JUNO, I would have:

1. Created separate virtual environments with different packages in various directories
    
2. Registered each as a kernel into my lab
    
3. Carefully selected the right kernel for each notebook
    
4. Documented the environment setup for teammates
    

With JUNO, I created two environments through the UI, installed the required packages with a few clicks, and could switch between them without any hassle.

```python
# In my TensorFlow notebook (using the tensorflow-env kernel)
import tensorflow as tf
model = tf.keras.Sequential([...])

# In my PyTorch notebook (using the pytorch-env kernel)
import torch
model = torch.nn.Sequential(...)
```

The best part? I could export the environment specifications directly from JUNO, making it trivial for teammates to recreate the exact environment.

## Under the Hood

JUNO isn't just a pretty interface—it leverages proven technologies like `venv` or [`conda`](https://anaconda.org/anaconda/conda) while abstracting away their complexities. The software communicates with a backend service that manages:

* Environment creation and deletion
    
* Package installation and removal
    
* Kernel registration with JupyterLab
    
* Environment activation and deactivation
    

This architecture ensures that JUNO integrates seamlessly with existing [Python](https://anaconda.org/anaconda/conda) packaging tools while providing a superior user experience.

## Why This Matters for Data Science Teams

For teams building data products, reproducibility isn't just a nice-to-have—it's essential. JUNO addresses this need by:

* Reducing environment setup time from minutes to seconds
    
* Eliminating "works on my machine" problems
    
* Simplifying onboarding for new team members
    
* Making dependency management accessible to less technical users
    

The productivity gains are substantial. In my experience, teams using [JUNO](https://github.com/velocitatem/juno) spend significantly less time debugging environment issues and more time solving actual problems.

## Conclusion

Managing virtual environments in JupyterLab has long been a pain point for data scientists and analysts. JUNO transforms this experience by bringing environment management into the JupyterLab interface, making it accessible and intuitive.

Whether you're a solo data scientist juggling multiple projects or part of a team that needs reproducible environments, JUNO offers a compelling solution that streamlines your workflow and eliminates one of the most persistent headaches in the Jupyter ecosystem.

Give it a try on your next project—your future self (and your teammates) will thank you.