# ocd-api-documentation
Documentation of the Open Civic Data API. Available on [readthedocs.io](http://ocd-api-documentation.readthedocs.io/en/latest/).

## Set-up 

Read the Docs suggests using Sphinx, a tool to facilitate the generation of nice-looking documentation. Before you install Sphinx, you may want to set-up a virtualized development environment: learn [how to set up virtualenv](http://docs.python-guide.org/en/latest/dev/virtualenvs/).

Then, run the following in your terminal:

```bash
mkvirtualenv ocd-api-documentation
git clone git@github.com:datamade/ocd-api-documentation.git
cd ocd-api-documentation
pip install -r requirements.txt
```

Afterwards, whenever you want to use this virtual environment, run `workon ocd-api-documentation`.

## Contribute

You can learn about the process of Sphinx and document creation on the [Read the Docs site](http://docs.readthedocs.io/en/latest/getting_started.html).

Ready to dive in? Edit the `rst` files in the `docs` directory. Then, generate the html by running the Makefile:

```bash
cd docs
make html
```

Then, view your code in a browser:

```bash
open _build/html/index.html
```

## Team

* Forest Gregg, DataMade 
* Regina Compton, DataMade
* Jack Corrigan 
