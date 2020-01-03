Quickstart
==========

Launching the Simulator
-----------------------
Having successfully completed the steps above running is Simulator is easy. Depending
on what OS you're using, follow the steps below, we can look at the application flags using the -h command-line option:

.. code-block:: shell

    cd ~/ambf/bin/<os>
    ./ambf_simulator -h

This should show you the available command line options. Some of the command line options are for testing purposes and might be deprecated in future versions.

For our usage, one of the most important flags is the -l flag. The AMBF Simulator uses the **yaml** file located in `ambf/ambf_models/descriptions/launch.yaml <https://github.com/WPI-AIM/ambf/blob/master/ambf_models/descriptions/launch.yaml>`_ to load :code:`robot/multi-body models`, haptic devices, simulated end-effectors, and the world. You can see the contents of this file by launching it in your favorite text editor. For launching specific robots we can use the corresponding index of the multi-body in `multibody configs:` data-block. To launch a multi-body and index 3, we can simply run:

.. code-block:: shell

    cd ~/ambf/bin/<os>
    ./ambf_simulator -l 3

If we want to run multiple robots, we can simply use a comma-separated list as follows:

.. code-block:: shell

    cd ~/ambf/bin/<os>
    ./ambf_simulator -l 1,6,10

If we don't specify the :code:`-l` flag, the first multi-body defined in the :code:`multibody configs` data block is launched

There is a second option to the launch desired multi-bodies, if one has an AMBF description file in the home directory :code:`/users/potato/tests/robot.yaml`, this file can be launched directly as follows

.. code-block:: shell

    cd ~/ambf/bin/<os>
    ./ambf_simulator -a /users/potato/tests/robot.yaml

Similarly, as it the case with the :code:`-l` flag, multiple filenames can be launch by comma separated values. E.g.

.. code-block:: shell

    cd ~/ambf/bin/<os>
    ./ambf_simulator -a /users/potato/tests/robot.yaml,/users/potato/tests/car.yaml

Lastly, the :code:`-l` and :code:`-a` flags can be used together to launch some files based on the index and some based on the filenames.

Selecting Robots
----------------

This a brief overview of the `ambf/ambf_models/descriptions/launch.yaml <https://github.com/WPI-AIM/ambf/blob/master/ambf_models/descriptions/launch.yaml>`_ file. If we take a look at the block :code:`multi-body configs`, we can see the existing multi-body config files that have been defined for AMBF. There are of course additional Robots and Multibodies that are defined in the `ambf/ambf_model/descriptions/multi-bodies <https://github.com/WPI-AIM/ambf/tree/master/ambf_models/descriptions/multi-bodies>`_ folder. These can be added to :code:`multibody config` block and even you can create your own :code:`Robot/Multi-Bodies` that can be appended to the :code:`multibody config` block. It's worth paying attention to the comments after each multibody file. These are indexes that can be used to load the specific multibody in the simulator and are there only to assist in counting.


.. code-block:: yaml

    # This is the base file for Coordination Application
    world config: ./world/world.yaml
    color config: ./color/colors.yaml
    input devices config: ./input_devices/input_devices.yaml
    multibody configs:
      1. "./multi-bodies/robots/blender-toy-car.yaml" #0
      2. "./multi-bodies/robots/blender-toy-car2.yaml" #1
      3. "./multi-bodies/robots/blender-neuro-robot.yaml" #2
      4. "./multi-bodies/robots/blender-raven2.yaml" #3
      5. "./multi-bodies/robots/blender-mtm.yaml" #4
      6. "./multi-bodies/robots/blender-psm.yaml" #5
      7. "./multi-bodies/robots/blender-ecm.yaml" #6
      8. "./multi-bodies/robots/blender-suj.yaml" #7
      9. "./multi-bodies/robots/blender-kuka.yaml" #8
      10. "./multi-bodies/robots/blender-pr2.yaml" #9
      11. "./multi-bodies/puzzles/parallel_structure.yaml" #10
      12. "./multi-bodies/puzzles/puzzle1.yaml" #11
      13. "./multi-bodies/puzzles/puzzle2.yaml" #12

Now let's run the simulator as described in `Launching the Simulator <https://github.com/WPI-AIM/ambf/wiki/Launching-the-Simulator>`_
