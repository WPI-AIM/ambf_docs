The General Concept
===================

To take full advantage of AMBF, it should be installed on Linux (Ubuntu 16, 17, 18) with a working installation of ROS. All the simulated/visual objects in the AMBF simulator (kinematic bodies, dynamic bodies, connected bodies, lights and cameras) are controllable using ROS messages. Each simulated/visual object (conveniently called _afObject_) communicates bidirectionally using **ambf_msgs/ObjectState** and **ambf_msgs/ObjectCmd** message types. The **ObjectState** is an outgoing message from the simulator that describes the state of the object. The **ObjectCmd** is the incoming message to the simulator and can be used to change the state of the corresponding _afObject_. A similar concept exists for the World where the only difference is that World exists as a single entity and thus has a single State/Command message pair. The message payloads are defined and discussed in the subsections.

Controlling dynamic bodies vs kinematic bodies:
-----------------------------------------------
Kinematic and dynamic bodies are controlled using the same afCommand message type. If an object is kinematic (which could be a camera or a light or a plain kinematic body), the boolean flag **enable_position_controller** has to be set to **1** in the afObjectCmd message. This is necessary as by default the **enable_position_controller** is set to **0** and the AMBF simulator takes the wrench command. For kinematic bodies, wrench commands are meaningless.

If the corresponding body is Dynamic (has non-zero mass and inertia), the **enable_position_controller** can be set to **1** or **0** to inform the AMBF Simulator to consider Pose or Wrench commands respectively. For Position Commands, the AMBF Simulator runs an internal PID Loop. The gains for this controller are directly set in the AMBF Description of the body.

Parenting of bodies and joints:
-------------------------------
It is important to point out the way parenting works in the AMBF Simulator. This table sheds some light on this where the nodes (circles) can be considered as bodies and the arrows as joints. The resulting parenting is shown in the same table.

.. figure:: https://raw.githubusercontent.com/wiki/WPI-AIM/ambf/Images/AMBF%20Densely%20Connected%20Bodies2.png
   :scale: 50 %
   :alt: Densely connected bodies
   :align: center

Based on this image, children bodies are in fact all the bodies lower in the hierarchy to a specific body. This is reflected in the **afObjectState** and **afObjectCommand** messages.

Note:
-----

A robot can have a large number of children bodies and joints and thus transmitting their names and positions using the **children_name**, **joint_names** and **joint_positions** payload fields can eat up the socket communication. Towards this end, the AMBF Description of the Robot / Multi-Body comes in handy. By default, the bodies are set to **NOT** publish **children_names** and **joint_positions** and **ONLY** publish **joint_names**. This can, of course, be overridden using the AMBF Description of Robot by specifying the following three optional fields for any **afObject**.

* **publish children names**: True or False
* **publish joint names**: True or False
* **publish joint positions**: True or False

Lastly, visual objects such as Cameras and Lights do not have joints.

Example
-------

// TODO
