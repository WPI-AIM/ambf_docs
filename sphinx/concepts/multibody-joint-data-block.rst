Joint Data-Block
================

The items in the joint data block are explained below.

* #### name:
The name of the joint. For internal AMBF Usage
***

* #### parent:
The name of the parent body

***

* #### child:
The name of the child body
***

* #### parent axis:
The axis along the parent body's frame along which the joint is required.
***

* #### parent pivot:
The xyz offset in the parent's body frame where the origin of the joint is required.
***

* #### child axis:
The axis along the child body's frame along which the joint is required.
***

* #### child pivot:
The xyz offset in the child's body frame where the origin of the joint is required.
***

* #### joint limits:
Limits of this joint. Revolute, Prismatic and Spring joints have limits. Continuous (revolute without limits)
are free hinge joints.
***

* #### type:
What type of joint is this. Supported types are **REVOLUTE**, **PRISMATIC**, **FIXED**, **LINEAR SPRING** and **ANGULAR SPRING**.
***

* #### offset:
The offset in Radians applied to the child's body frame, carried out along the parent's axis (parent's joint axis). __Needs more explanation__
***

* #### joint erp:
Override the global ERP for this joint.
***

* #### joint cfm:
Overrride the global cfm for this joint
***

* #### stiffness:
Stiffness for SPRING joints. Only applicable for LINEAR and ANGULAR SPRING joints
***

* #### damping:
Damping for this joint. WIP on the AMBF Simulator
***

* #### controller:
Joint PD controller. Specify the values of the P and D for joint control
