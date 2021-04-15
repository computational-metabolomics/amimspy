Installation
============

Conda (recommended)
-------------------

Install Miniconda, follow the steps described `here <https://docs.conda.io/projects/conda/en/latest/user-guide/install>`_

Start the ``conda prompt``

* Windows: Open the ``Anaconda Prompt`` via the Start menu
* macOS or Linux: Open a ``Terminal``

Create a amimspy specific ``conda`` environment.
This will install a the dependencies required to run ``amimspy``::

    $ conda create --yes --name amimspy amimspy -c conda-forge -c bioconda -c computational-metabolomics

.. note::

    * The installation process will take a few minutes.
    * Feel free to use a different name for the Conda environment

    You can use the following command to remove a conda environment::

        $ conda env remove -y --name amimspy

    This is only required if something has gone wrong in the previous step.

Activate the ``amimspy`` environment::

    $ conda activate amimspy

To test your ``amimspy`` installation, in your Conda Prompt, run the command::

    $ amimspy --help

or::

    $ python
    import amimspy

Close and deactivate the ``amimspy`` environment when you’re done::

    $ conda deactivate


PyPi
----

Install the current release of ``amimspy`` with ``pip``::

    $ pip install .

.. note::

    * The installation process will take a few minutes.

To upgrade to a newer release use the ``--upgrade`` flag::

    $ pip install --upgrade amimspy

If you do not have permission to install software systemwide, you can
install into your user directory using the ``--user`` flag::

    $ pip install --user amimspy

Alternatively, you can manually download ``amimspy`` from
`GitHub <https://github.com/computational-metabolomics/amimspy/releases>`_  or
`PyPI <https://pypi.python.org/pypi/amimspy>`_.
To install one of these versions, unpack it and run the following from the
top-level source directory using the Terminal::

    $ pip install .


Testing
-------
amimspy uses the Python ``pytest`` testing package.  You can learn more
about pytest on their `homepage <https://pytest.org>`_.
