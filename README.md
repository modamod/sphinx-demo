## Configuration Steps

These are the configuration steps I took to prepare the environment to be used.

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
    "m2r2",
    "sphinxcontrib.confluencebuilder"
]

```

To be able to publish to Confluence add the following configuration to `docs/source/conf.py`
The configuration below is for Confluence server, if you are using Confluence Cloud refer to [Sphinx Confluence Extension Documentation](https://sphinxcontrib-confluencebuilder.readthedocs.io/en/stable/configuration.html)

```python

confluence_server_user = "<confluence user>"
confluence_server_pass = "<confluence user password>"
confluence_space_name = "SPHIN"
confluence_server_url = "<confluence server url>"
confluence_publish = True
confluence_parent_page = "Test Sphinx" # This is an exiting page on confluence
confluence_page_hierarchy = True

```

On `docs/source` run the following command to publish the documentation to Confluence.

Windows

```powershell
$ .\make.bat confluence

Running Sphinx v3.5.4
Password:
loading pickled environment... done
building [mo]: targets for 0 po files that are out of date
building [confluence]: targets for 0 source files that are out of date
updating environment: [config changed ('confluence_jira_servers')] 4 added, 0 changed, 0 removed
reading sources... [100%] usage/index
looking for now-outdated files... none found
pickling environment... done
checking consistency... done
preparing documents... done
writing output... [100%] usage/index
publishing documents... [100%] next/index
Publish point: http://192.168.56.1:8090/pages/viewpage.action?pageId=360479
building intersphinx... done

build succeeded.
```

Linux

```bash
$ make confluence

Running Sphinx v3.5.4
Password:
loading pickled environment... done
building [mo]: targets for 0 po files that are out of date
building [confluence]: targets for 0 source files that are out of date
updating environment: [config changed ('confluence_jira_servers')] 4 added, 0 changed, 0 removed
reading sources... [100%] usage/index
looking for now-outdated files... none found
pickling environment... done
checking consistency... done
preparing documents... done
writing output... [100%] usage/index
publishing documents... [100%] next/index
Publish point: http://192.168.56.1:8090/pages/viewpage.action?pageId=360479
building intersphinx... done

build succeeded.
```
