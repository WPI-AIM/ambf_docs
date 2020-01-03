Object State Payload
====================

afObject State Message
----------------------

The following table describes the payload of the State message for any _afObject_.

========================   ===========
ObjectState Payload        Description
========================   ===========
**header**                 The ROS message header includes **seq_number**, **time_stamp** and **frame_id**. **frame_id** not used for now
**name**                   The name of this **afOjbect**, set the AMBF Config file that loads this Object
**wall_time**              System time or Wall Clock in seconds
**sim_time**               Simulation clock which is incremented at each time-step. For RT **sim_time** == **wall_time**
**mass**                   The mass of the afObject, for kinematic bodies this is 0
**pInertia**               The principal inertial of the afObject. Ignore for kinematic bodies
**pose**                   The position and orientation as quaternion in the Parent frame
**wrench**                 The accumulated external forces on this body in the Parent Frame. Not yet implemented
**userdata**               Array of floats for defining user data
**userdata_description**   String to define any user data
**children_names**         An array for children names that are connected to this afObject
**joint_names**            An array of joint names that this object is a parent of
**joint_positions**        Positions of joints that this object is a parent of
========================   ===========
