# Development Environment Setup

Instructions to setup the (local) Python development environment.

- [Virtual Environment using `venv`](#venv) for Standard Python Distribution
- [Conda Virtual Environment](#conda) for Anaconda Python Distribution

---

<a name="venv"></a>

#### Virtual Environment using `venv`

The `venv` module provides support for creating lightweight “virtual environments” 
with their own site directories, 
optionally isolated from system site directories. 
Each virtual environment has its own Python binary 
(which matches the version of the binary that was used to create this environment) 
and can have its own independent set of installed Python packages in 
its site directories.

**Note**: The `venv` module is part of the **Python Standard Library**, so no further 
installation is required.

The following **`3`** steps are required to setup a new virtual environment 
using `venv`:

1. Create the environment:

    ```shell script
    python -m venv </path/to/new/virtual/environment>
    ```

    

2. Activate the environment:

    ```shell script
    source </path/to/new/virtual/environment/bin/activate>
    ```

    

3. Install the Required Package (using the `requirements.txt` file):

    ```shell script
    pip install -r requirements.txt
    ```

    

4. (**Optional**) Create new Jupyter notebook Kernel

To avoid re-installing the entire Jupyter stack into the new environment, 
it is possible to add a new **Jupyter Kernel** to be used in notebooks with 
the "default" Jupyter.

To do so, please make sure that the `ipykernel` package is installed in the **new** 
Python environment:

```shell script
pip install ipykernel  ## this should be the default pip 
```

Then, execute the following command:

```shell script
python -m ipykernel install --user --prefix /path/to/new/virtual/environment --display-name "Python 3 (DL Biomed)"
```

Further information [here](https://ipython.readthedocs.io/en/stable/install/kernel_install.html)

<a name="conda"> </a>

#### Setting up `conda` environment

If you are using Anaconda Python distribution, it is possible to re-create the 
virtual (conda) environment using the export `.yml` (`YAML`) file:

```shell script
conda env create -f dl-biomed.yml
```

This will create a new Conda environment named `dl-torch` with all the 
required packages.

To **activate** the environment:

```shell script
conda activate dl-biomed
```

##### (**Optional**) Create new Jupyter notebook Kernel

To avoid re-installing the entire Jupyter stack into the new environment, 
it is possible to 
add a new **Jupyter Kernel** to be used in notebooks with the "default" Jupyter.

To do so, please make sure that the `ipykernel` package is installed in the **new** 
conda environment:

```shell script
conda install ipykernel 
```

Then, still remaining in the **new** conda environment, execute the following command:

```shell script
python -m ipykernel install --user --name dl-torch --display-name "Python 3.7 (DL Biomed)"
```

Further information [here](https://ipython.readthedocs.io/en/stable/install/kernel_install.html)
