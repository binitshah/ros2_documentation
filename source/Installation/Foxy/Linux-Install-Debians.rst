Installing ROS 2 via Debian Packages
====================================

.. contents:: Table of Contents
   :depth: 2
   :local:

System Requirements
-------------------

We support Ubuntu Linux Focal Fossa (20.04) 64-bit x86 and 64-bit ARM.

Set locale
----------

.. include:: ../_Linux-Set-Locale.rst

Setup Sources
-------------

.. include:: ../_Apt-Repositories.rst

.. _Foxy_linux-install-debians-install-ros-2-packages:

Install ROS 2 packages
----------------------

Update your apt repository caches after setting up the repositories.

.. code-block:: bash

   sudo apt update

Desktop Install: ROS, RViz, demos, tutorials.

.. code-block:: bash

   sudo apt install ros-foxy-desktop

Environment setup
-----------------

Sourcing the setup script
^^^^^^^^^^^^^^^^^^^^^^^^^

Set up your environment by sourcing the following file.

.. code-block:: bash

   source /opt/ros/foxy/setup.bash

Install argcomplete
^^^^^^^^^^^^^^^^^^^

ROS 2 command line tools use argcomplete to autocompletion.
So if you want autocompletion, installing argcomplete is necessary.

.. code-block:: bash

   sudo apt install -y python3-pip
   pip3 install -U argcomplete

Install colcon
^^^^^^^^^^^^^^

Colcon is used to build ROS2 workspaces. See :ref:`this tutorial <install-colcon>` to learn how to use it.

.. code-block:: bash

   sudo apt install python3-colcon-common-extensions

Try some examples
-----------------

In one terminal, source the setup file and then run a C++ ``talker``\ :

.. code-block:: bash

   source /opt/ros/foxy/setup.bash
   ros2 run demo_nodes_cpp talker

In another terminal source the setup file and then run a Python ``listener``\ :

.. code-block:: bash

   source /opt/ros/foxy/setup.bash
   ros2 run demo_nodes_py listener

You should see the ``talker`` saying that it's ``Publishing`` messages and the ``listener`` saying ``I heard`` those messages.
This verifies both the C++ and Python APIs are working properly.
Hooray!

Next steps after installing
---------------------------
Continue with the `tutorials and demos </Tutorials>` to configure your environment, create your own workspace and packages, and learn ROS 2 core concepts.

Troubleshooting
---------------

Troubleshooting techniques can be found `here </Troubleshooting>`.

Uninstall
---------

If you need to uninstall ROS 2 or switch to a source-based install once you
have already installed from binaries, run the following command:

.. code-block:: bash

  sudo apt remove ros-foxy-* && sudo apt autoremove
