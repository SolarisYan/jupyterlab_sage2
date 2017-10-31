# jupyterlab_sage2

A JupyterLab extension to integrate SAGE2 into the JupyterLab scientific workflow.

## Extension

This extension to JupyterLab allows a user to simultaneously connect to multiple SAGE2 servers and share JupyterLab content with SAGE2, including:
* Notebooks
* Notebook Cells (Images)

Notebooks are sent to SAGE2 and rendered using [nbviewer](http://nbviewer.jupyter.org/). Notebook cells are rendered as images and automatically updated when a cell is re-run.

### How-to

From the JupyterLab launcher, open the SAGE2 widget under "Other." Click the Green-Plus-Button to create a new server connection, and enter a server name and address.

Once connected, use the SAGE2 menu in the upper menu-bar to send the current notebook or selected cell output to a connected SAGE2 server of your choice.

## Package Installation

### Prerequisites

* **JupyterLab**

### Installation

```bash
jupyter labextension install jupyterlab_sage2
```

### Development

For a development install (requires `npm` version 4 or later), do the following in the repository directory:

```bash
npm install
jupyter labextension link .
```

To rebuild the package and the JupyterLab app:

```bash
npm run build
jupyter lab build
```

## Docker Installation

To try JupyterLab with SAGE2, use the `sage2/jupyterlab-datascience-notebook` Docker image. This image is built `FROM` the `jupyter/datascience-notebook` and includes Python 3, R, and Julia as well as a variety of data science packages. 

### To install/update:
```
docker pull sage2/jupyterlab-datascience-notebook
```

### To run:
```
docker run -it --rm -p 8888:8888 sage2/jupyterlab-datascience-notebook start.sh jupyter lab
```

The `-p 8888:8888` maps the external port to the docker port: `-p external:internal`. If you would like to select a different port to access Jupyterlab use `-p yourport:8888`.

When starting the docker image, the console will give a JupyterLab url with an access token. To access JupyterLab, navigate your webpage to `http://yourhostname:yourport/?token=yourtoken`.

For more information on the jupyter/datascience-notebook image, visit: https://github.com/jupyter/docker-stacks/tree/master/datascience-notebook

## Future Plans

In the future, we plan to support more content types and methods of sending data from JupyterLab to SAGE2, as well as implement a file browser for JupyterLab which allows access to SAGE2 files in the JupyterLab workspace.

## Issues and Contributing
Please direct any issues or bug reports to the repository's [Issues](https://github.com/AndrewTBurks/jupyterlab_sage2/issues).

If you would like to contribute, submit a [Pull Request](https://github.com/AndrewTBurks/jupyterlab_sage2/pulls).