Header Data-Block
=================

Let's inspect the **Header Data-Block** which is redefined in the following snippet.
.. code-block:: yaml
    bodies: [BodyA, BodyB]
    joints: [JointA]
    high resolution path: ./high_res/
    low resolution path: ./low_res/
    namespace: /ambf/env/

The **Header Data-Block** is the entry point of all Multibody config files and is parsed first and foremost. It contains global variables that can be used to save editing parameters locally and thus improving the readability of the remaining config file. We shall examine the context one by one.

**bodies**
~~~~~~~~~~

This **bodies** field is an associative array that contains the names of bodies in the config file that need to be loaded. The config file can have many bodies and not all bodies might require loading so they can be conveniently removed from the **bodies** array. This is useful for debugging and making sure individual sub-components can be tested in isolation.

**soft bodies**
~~~~~~~~~~~~~~~

**joints**
~~~~~~~~~~

Similar to the **bodies** field, **joint** is an associative array as well that contains the names of joints in the config file. Only the joints defined in this array are loaded whereas the config file itself can have many additional joints defined.


**high resolution path**
~~~~~~~~~~~~~~~~~~~~~~~~

The high resolution path is the folder path to the location of high-resolution visual meshes. This path can be either absolute or relative (based on the location of the config file).


**low resolution path**
~~~~~~~~~~~~~~~~~~~~~~~

The low resolution path is the folder path to the location of low-resolution collision meshes. This path can be either absolute or relative (based on the location of the config file).


**namespace**
~~~~~~~~~~~~~

The namespace is appended to the start of all bodies and joints in the config file. This helps in defining namespaces for different robots/mechanisms as well as avoiding naming conflicts between the identical body names in different config files.


**joint erp**
~~~~~~~~~~~~~


**joint cfm**
~~~~~~~~~~~~~


**ignore inter-collision**
~~~~~~~~~~~~~~~~~~~~~~~~~~
