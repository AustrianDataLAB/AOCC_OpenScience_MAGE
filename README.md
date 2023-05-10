
To have more information on what is available specifically through this kernel, type magic command `%help` in the interpreter.

For a basic example of the kernel using Jupyter Notebook, see `Examples/simpleDemo.ipynb`.

## Test environment with docker

Included you find a `Dockerfile` with a simple test environment based on JupyterLab. 
The installation is based on *Python 3.9* and uses *miniconda* to install Paraview 5.11.1 (on `conda-forge`).

To build the container run:
```bash
$ docker build -t iparaview_kernel_test .
```
and to run it:
```bash
$ docker run -it -p 8888:8888 iparaview_kernel_test
```
You will see the URL showing up to connect to the JupyterLab.
The container starts in the `./Examples` folder.
