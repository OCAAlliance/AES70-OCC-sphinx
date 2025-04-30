This repository contains version of the AES70 control classes for the
[sphinx documentation generator](https://www.sphinx-doc.org/).

# Installation

In order to build this documentation using sphinx it is recommended to set
up a virtual environment using pip.

    python3 -m venv .venv

Once the environment has been set up it can be activated using

    source .venv/bin/activate

To install sphinx and the theme used for this documentation run

    pip install -r requirements.txt

# Building the documentation

To build the documentation run

    make html

inside the pip virtual environment.
