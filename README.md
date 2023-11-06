# Python Packaging Demo

This repo demos an example structure for packaging Python projects using `pyproject.toml`. This approach is recommended for new Python packages, replacing the `setup.py` approach since [PEP 518](https://peps.python.org/pep-0518/). Whenever a custom Python package is to be distributed to others, `pyproject.toml` is the best practice. This file contains the build system requirements and other metadata, which are then used by `pip` to build the package.

The goal of this repo is to provide a baseline project structure and outline the process for building and using the package within other _private_ projects. When it comes to package distribution, the common advice is to upload the project to PyPI, from where users can then easily install the package using `pip`. However, the process described here is aimed towards internal projects within a company that are not intended to be shared online.

### How to use the package within another project

Let's call the other project the "main project" to distiguish it from the package of interest.

1. Clone the package repo into its own directory.
2. Within the main project repo, create a virtualenv and source it.
3. `cd` into the package repo from step 1 and install the package in the virtualenv with `pip install -e .`. After installation, an `.egg-info` directory should be present within the `src` folder.
4. `cd` back into the main project.
5. Package can now be imported using normal import statements, i.e. `from example_package import example`

Alternatively, the package can be hosted on private server like Azure Artifacts which behave like PyPI and can use `pip` to install packages.

### Resources:

- https://packaging.python.org/en/latest/tutorials/packaging-projects/
- https://www.youtube.com/watch?v=QMY-OkckDwo
