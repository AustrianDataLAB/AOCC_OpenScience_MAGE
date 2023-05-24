
To have more information on what is available specifically through this kernel, type magic command `%help` in the interpreter.

For a basic example of the kernel using Jupyter Notebook, see `ParaviewExample.ipynb`, for a sample Tutorial see `MagIonPlot.ipynb` , for opening a connection via Globus, see `globus_client_start.ipynb`.

## TL;DR
```
docker run -it -p 8888:8888 ghcr.io/austriandatalab/aocc_openscience_mage:main
```

and you have the Jupyter-Lab-with-Paraview-Kernel running locally, accessible in your browser.


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
The container starts in the `./Examples` folder.
