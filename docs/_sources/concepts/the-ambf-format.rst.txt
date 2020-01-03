The AMBF Format
===============

The AMBF Description Format uses YAML to specify Bodies, Joints, Lights, Cameras and Sensors. The format
has been developed to make it easier for users to develop complex interconnected robots and mechanisms with fully customizable dynamic parameters while keeping the syntax easy and human readable. On one hand, this format has been inspired by **URDF** (Unified Robot Description Format) and **SDF** (Simulation Description Format) while on the other it's has been developed to address the key limitations and complexities of both URDF and SDF. The first and foremost goal of the format is the choice or markup language (YAML). In our experience, YAML is much easier to read and modify.

The Anatomy of the AMBF Format
------------------------------

In general, the current version 0.1 of the AMBF Format can specify the following objects
* **Rigid Bodies (Kinematic and Dynamic)**

  + Cartesian Controllers for these Bodies

* **Soft Bodies**
* **Joints**

  + Types of Joints

    - Prismatic or Slider Joints
    - Revolute, Hinge or Continous Joints
    - Point To Point or P2P Constraints
    - Fixed Joints
    - Linear Springs
    - Torsion or Angular Springs

  + Joint Controllers

* **Multiple Cameras as Viewports**
* **Lights**
* **Sensors**

  + Types of Sensors

    - Proximity Sensors (using Ray Tracing)

## Delving Deeper into the AMBF Format
We can start by examining a very basic example of a multibody defined by the AMBF Format. This multibody Consists
of two Rigid Bodies and a Joint.

.. code-block:: yaml

    bodies: [BodyA, BodyB]
    joints: [JointA]
    high resolution path: ./high_res/
    low resolution path: ./low_res/
    namespace: /ambf/env/

    BodyA:
      name: base_plate
      mesh: base_plate.STL
      mass: 5.0
      location:
        orientation: {p: -0.0, r: 0.0, y: 0.0}
        position: {x: 1.0, y: 0.0, z: -1.0}
      color: orange_tomato

    BodyB:
      name: latch
      mesh: latch.STL
      mass: 0.3
      location:
        orientation: {p: 1.571, r: -0.0, y: 0.0}
        position: {x: 1.0, y: -0.85, z: -1.0}
      inertial offset:
        orientation: {p: 0, r: 0, y: 0}
        position: {x: 0.0, y: -0.162, z: -0.003}
      color: red_crimson

    JointA:
      name: hinge_AB
      parent: BodyA
      child: BodyB
      parent axis: {x: 1.0, y: 0.0, z: 0.0}
      parent pivot: {x: 0.0, y: -0.85, z: 0.0}
      child axis: {x: 0.0, y: 0.0, z: 1.0}
      child pivot: {x: 0.0, y: 0.0, z: 0.0}
      type: revolute

Let's start examining the different subsections of this config file. We can call each section a data-block. Towards this end, this config file can be broken down into four data-blocks which are explained below

1. Header or Global Data-Block
2. BodyA Data-Block
3. BodyB Data-Block
4. JointA Data-Block

The whole concept of AMBF revolves around the asynchronous concept of data-blocks. The data blocks can potentially be split into different config files and should work independently of each other even though they can be related to each other by constraints. More on this later.
