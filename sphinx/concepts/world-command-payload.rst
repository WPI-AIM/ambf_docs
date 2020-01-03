World Command Payload
=====================

afWorld Command Message
-----------------------

The **afWorldCmd** message payload is as follows:

============================    ===========
WorldCmd Payload                Description
============================    ===========
**enable_step_throttling**      Boolean to enable/disable phyics simulation throttling
**step_clock**                  If the **enable_step_throttling** is set **true**, the toggle of field steps the simulation
**n_skip_steps**                The number of physics sub-steps to take in between each **step_clock** toggle
**publish_children_names**      Enable the publishing of all the children names
**publish_joint_names**         Enable the publishing of all children joint names
**publish_joint_positions**     Enable the publishing of all children joint positions
============================    ===========
