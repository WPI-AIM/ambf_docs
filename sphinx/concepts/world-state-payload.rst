World State Payload
===================

afWorld State Message
---------------------

There exists a single instance of simulation World called **afWorld**. Similar to **afObjects**, _afWorld_ is controllable using **ambf_msgs/afWorldCmd** message and relays its state using the **ambf_msgs/afWorldState** message.

=======================     ===========
WorldState Payload          Description
=======================     ===========
**header**                  The ROS message header includes **seq_number**, **time_stamp** and **frame_id**. **frame_id** not used for now
**dynamic_loop_freq**       The frequency of underlying pyhsics solver loop
**n_devices**               The number of haptics/input devices currently connected AMBF Simulator
**sim_step**                The number of simulation steps of the physics solver. This keeps incrementing
**wall_time**               The System Clock (Wall Clock) in seconds
**sim_time**                The time of the physics simulation. For RT **sim_time** == **wall_time**
=======================     ===========
