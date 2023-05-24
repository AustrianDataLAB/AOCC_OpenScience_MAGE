
# JupyterLab OpenScience Containers 
This is the first sample container for which we demonstrate how to use some HPC tooling on Kubernetes or locally, using the https://cgs.jhuapl.edu codebase "MAGE" ( an ecosystem consisting of Fortran/Python MPI/OPENMP).
Here, we specifically use Paraview to plot Magneto-Hydro-Dynamics Data produced by MAGE, and thus we include the Python Packages required specifically for this HPC codebase (kaipy etc).
WIP: The Globus Endpoints for the data are public, but currently those datasets are rather large.

In real life: there is a CI pipeline with the source code, that builds this Analysis-Container

For a basic example of the kernel using Jupyter Notebook, see `ParaviewExample.ipynb`, for a sample Tutorial see `MagIonPlot.ipynb` , for opening a connection via Globus, see `globus_client_start.ipynb`. To have more information on what is available specifically through this Jupyter-kernel, type magic command `%help` in the interpreter.

## TL;DR
```
docker run -it -p 8888:8888 ghcr.io/austriandatalab/aocc_openscience_mage:main
```

and you have the Jupyter-Lab-with-Paraview-Kernel running locally, accessible in your browser.

## For JupyterHub locally
 You can also see our other repos for the full JupyterHub on Docker and Minikube (https://github.com/AustrianDataLAB/AOCC-JupyterHub-Trial)


## Test your own modified environment with docker locally

Included you find a `Dockerfile` with a simple test environment based on JupyterLab. 

The installation is based on *Python 3.9* and uses *miniconda* to install Paraview 5.11.1 (on `conda-forge`).

If you wish to add your own modifications, clone this repo, modify it, then:

To build the container run:
```bash
$ docker build -t my_openscience_paraview:0.0.1 .
```
and to run it:
```bash
$ docker run -it -p 8888:8888 my_openscience_paraview:0.0.1
```
You will see the URL showing up to connect to the JupyterLab.

## For JupyterHub on Kubernetes 
see our main project under:
(https://dev.azure.com/AOCC/OpenScienceLabs)
