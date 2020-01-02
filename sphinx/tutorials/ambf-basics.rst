Quickstart
==========

Launching the Simulator:
------------------------
Having successfully completed the steps above running is Simulator is easy. Depending
on what OS you're using, follow the steps below, we can look at the application flags using the -h command-line option:

.. code-block:: shell

    cd ~/ambf/bin/<os>
    ./ambf_simulator -h

This should show you the available command line options. Some of the command line options are for testing purposes and might be deprecated in future versions.

For our usage, one of the most important flags is the -l flag. The AMBF Simulator uses the **yaml** file located in [`ambf/ambf_models/descriptions/launch.yaml`](https://github.com/WPI-AIM/ambf/blob/master/ambf_models/descriptions/launch.yaml) to
load robot/multi-body models, haptic devices, simulated end-effectors, and the world. You can see the contents
of this file by launching it in your favorite text editor. For launching specific robots we can use the corresponding index of the multi-body in `multibody configs:` data-block. To launch a multi-body and index 3, we can simply run:

```
cd ~/ambf/bin/<os>
./ambf_simulator -l 3
```

If we want to run multiple robots, we can simply use a comma-separated list as follows:

```
cd ~/ambf/bin/<os>
./ambf_simulator -l 1,6,10
```
If we don't specify the `-l` flag, the first multi-body defined in the `multibody configs` data block is launched

There is a second option to the launch desired multi-bodies, if one has an AMBF description file in the home directory `/users/potato/tests/robot.yaml`, this file can be launched directly as follows

```
cd ~/ambf/bin/<os>
./ambf_simulator -a /users/potato/tests/robot.yaml
```

Similarly, as it the case with the `-l` flag, multiple filenames can be launch by comma separated values. E.g.

```
cd ~/ambf/bin/<os>
./ambf_simulator -a /users/potato/tests/robot.yaml,/users/potato/tests/car.yaml
```

Lastly, the `-l` and `-a` flags can be used together to launch some files based on the index and some based on the filenames.
