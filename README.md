## Configuration Steps

These are the configuration steps I took to preare the environment to be used.

### Installation

Sphinx comes packaged in different format. The most common way to install Sphinx is using pip.

```bash

pip install sphinx

```

Since the target for our documentation is confluence one more dependency needs to be installed.

```bash

pip install sphinx-confluence

```

We will be using md files as a base of our documentation as a result we would need to install m2r dependency as well.

```bash

pip install m2r

```

### Usage

Sphinx comes built in with a quick start option that sets up the folder structure and prepare the necessary files to build the documentation.
Run the following commands and follow the wizard to setup sphinx.

```bash
mkidr docs
cd docs
sphinx-quickstart
```

Open `docs/source/conf.py` file and add both dependencies to the configuration as follows

```python

extensions = [
    "m2r2"
]


```
