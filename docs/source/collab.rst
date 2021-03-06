Collaborating Using Our Platform
=================================




Collaboration Facilities
------------------------
Every user has a ‘lincc’ folder in their home directory, with three subdirectories:

* **data:** shared, centrally managed, data.

* **groups:** group-owned, group-managed, files.

* **shared:** a folder anyone can write to, and readable by everyone on LINCC JupyterHub.

.. image:: images/Picture9.png
    :align: center

Group file spaces
-----------------



* When you log in, any organization that you’re a member of on github (and to which you’ve granted LINCC JupyterHub access; see slide #7), is given:

  - a UNIX group on LINCC JupyterHub    
  - a directory in ``lincc/groups``, readable and writable only by members of that group.

.. image:: images/Picture10.png
    :align: right
    :width: 400

* You can place shared notebooks, datafiles, software here…
* Works for any github organization, and is fully automatic.
* Enables seamless collaboration!


Group-controlled environments and software
-------------------------------------------

* A frequent use for shared directories is to install and maintain common software environments.
* It’s good to protect such environments from accidental corruption or deletion.

  - E.g., it’s too easy to accidentally run ‘pip install some_package’ and ruin a carefully curated conda environment.
  - Especially true for large groups (e.g. science collaborations).

* To defend against this, each group has an admin account, designed to own its software and important files.


Here is an example of how to use an admin account in the terminal:

.. code-block:: console

    # login as admin for dirac-institute
    $sudo -u dirac-institute –s
    $cd

    # install a new environment
    $conda create -n solarsystem openorb
    exit

    # check that we have access to the env
    $conda env list 
    $conda activate solarsystem
    $oorb

    # make it accessible in Jupyter
    $sudo -u dirac-institute –s
    $cd
    $conda activate solarsystem
    $mamba install ipykernel

.. note:: Only GitHub organization owners have access to the admin account.

.. tip::

    - Your **home directory** is visible only by you. Keep any private files there.

    - A **group directory** is visible only to eponymous GitHub organization’s members. Keep common files there.

    - The **shared directory** is visible (readable and writable) to anyone. Place files there that you want to share with the entire hub (that are public).




