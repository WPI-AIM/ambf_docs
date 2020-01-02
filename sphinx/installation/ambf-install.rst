.. _install-ambf-simulator:

Installing AMBF Simulator
=========================

Tested Platforms
----------------

AMBF has been tested on **Ubuntu 16.04** and **Ubuntu 18.04**. We need a few extra steps on **Ubuntu 14.04**, please create an issue if you would like to get instructions for that.

Even though it is recommended to use Linux for the full feature set of AMBF Simulator using ROS, AMBF has been tested on **MacOS Maverick** and **MacOS Mojave** without ROS support.

Building
--------
On Linux machines, you might need to install the :code:`libasound2-dev` package.

.. code-block:: shell
    sudo apt install libasound2-dev


Boost libraires ship with Ubuntu systems, but on Mac OS, you might need to install them explicitly.

For this purpose, on **Mac OS**, if you don't have Boost

1. Install **Xcode** from App Store
2. Install **command line tools** by running in terminal :code:`xcode-select --install`
3. Install **Homebrew** view running this in terminal :code:`/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
4. Install **boost** by running the following in the terminal :code:`brew install boost`


To build the framework (Linux and Mac-OS):

.. code-block:: shell

    cd ~
    git clone https://github.com/WPI-AIM/ambf.git
    cd ambf && mkdir build
    cd build
    cmake ..
    make

On Linux systems, please source the correct folder to achieve system wide availability of AMBF ROS modules.
While in the build folder, you can run:

.. code-block:: shell

    source ./devel/setup.bash

You can also permanently add the install location in your .bashrc with the following command:

.. code-block:: shell

    echo "source ~/ambf/build/devel/setup.bash" >> ~/.bashrc
