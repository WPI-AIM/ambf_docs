Object Command Payload
====================

afObject Command Message
------------------------

==============================   ===========
ObjectCmd Payload                Description
==============================   ===========
**header**                       The ROS message header includes **seq_number**, **time_stamp** and **frame_id**. **frame_id** not used for now
**pose**                         The pose command (position and orientation) in Parent frame
**wrench**                       The wrench command (force and torque) for this body in World Frame
**enable_position_controller**   Boolean to inform which command to consider **1** for **pose Command** &  **0** for **wrench Command**
**joint_cmds**                   An array of joint commands for children joints
**position_controller_mask**     A mask to inform if the joint command is a Position Control Target or Effort Command
==============================   ===========

Types of Controllers
--------------------

The ObjectCmd has two distinct control fields. One being the afBody's Cartesian Pose Control using **pose**, **wrench** and **enable_position_control** payload fields and the other being the joint control of connected bodies using the **joint_cmds** and **position_control_mask** payload fileds.

Body's Pose Control
~~~~~~~~~~~~~~~~~~~

The payload fields (**pose**, **wrench** and **enable_position_control**) are designed to control the body in either **Cartesian Wrench Control** Mode or **Cartesian Position Control** Mode. The **pose** and **wrench** fields serve to control the equivalent pose or wrench of the object whose topic is being published to. The selection between **pose** and **wrench** command depends on the flag **enable_position_control**. When this flag is **0** (default), **wrench** command is considered while **pose** command is considered for when it's **1**. The controller gains for **pose** command are set directly in the bodies AMBF Description File. The **wrench** field does not require any controller gains.

Connected Bodies Joint Control
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The payload fields (**joint_cmds** and **position_control_mask**) are designed to control the children joints of the relevant afBody. The **joints_cmds** array is set in the order of the joint_names* from the corresponding ObjectState message of the Object a user is trying to control. One can echo the **joint_names*** in the ObjectState message to see what joints a body has (if any) and what order are they are stored. The size of the joint commands array depends on the number of joints, however, it's not required to fill in all the joints. For example, if the user intends to control the first 2 of the listed 10 joints, just setting the first two elements in the array should yield the desired result. Similarly, the **position_controller_mask** can be set to **1**'s for the joints that require position control, and **0** for open loop effort. Similar to afBody's Pose control, the controller gains for the joints positions are set directly in the AMBF description file.

If one wants to directly control the pose or wrench of any child Object, it can be accomplished by utilizing the corresponding objects' afObjectCmd (just like in the last section)


**joint_names:***
~~~~~~~~~~~~~~~~~

Only the root bodies of a connected tree of bodies are set to publish the **children_names**, **joint_names**, **joint_positions**. This can be easily changed by either setting the the last three fields in the afObjectCmd message or by modifying the corresponding AMBF Description file. Here is a simple example of an afBody data block where the fileds **publish_children_names**, **pubish_joint_names* and **publish_joint_positions** have been added and set to **true**:

.. code-block:: yaml

    BODY WristPlatform:
      name: WristPlatform
      mesh: WristPlatform.STL
      mass: 0.4
      collision margin: 0.001
      scale: 1.0
      publish children names: True
      publish joint names: True
      publish joint positions: True
      location:
        orientation: {p: -0.0, r: -0.0, y: -3.136}
        position: {x: -0.136, y: 0.002, z: -0.319}
      inertial offset:
        orientation: {p: 0, r: 0, y: 0}
        position: {x: 0.0, y: -0.055, z: -0.054}
      friction: {rolling: 0.01, static: 0.5}
      damping: {angular: 0.9, linear: 0.9}
      restitution: 0
      collision groups: [0]
      color components:
        ambient: {level: 1.0}
        diffuse: {b: 0.4576, g: 0.3377, r: 0.0488}
        specular: {b: 1.0, g: 1.0, r: 1.0}
        transparency: 1.0

You can do this for any afBody before launching the simulator.
