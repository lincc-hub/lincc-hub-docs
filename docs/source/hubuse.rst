Customizing your Hub
---------------------

Adding software: Conda Environments
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
You can create any number of personal conda environments where you have complete control over the software available. To create and activate a new conda environment, run the following in a terminal:

.. code-block:: console

    $ conda create -n my_environment python=3
    $ conda activate my_environment

Feel free to change "my_environment" to any environment name you desire. After activating the environment, you can use :code:`conda` and :code:`pip` commands to install any software you desire.

It may be helpful to install the :code:`mamba` software, a faster version of :code:`conda`:

.. code-block:: console

    $ conda install mamba


If the ``ipykernel`` package is installed in the environment, it will automatically show up in your list of kernels and be available for use in a Jupyter notebook.

.. image:: images/Picture5edit.png
    :width: 300

To install ``ipykernel`` use this command,

.. code-block:: console

    $ conda install ipykernel

or

.. code-block:: console

    $ mamba install ipykernel


.. IMPORTANT:: These environments are only accessible to you (they’re personal).
