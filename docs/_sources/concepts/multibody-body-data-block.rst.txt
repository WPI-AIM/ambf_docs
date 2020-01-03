Body Data-Block
===============

The Body Data-Block, as the name indicates, is used to define a body. The parameters defined in the data-block are explained below.

* #### name
This name is the set to specify the topic name for this body. This name is prepended with the namespace parameter.

***

* #### namespace
The global namespace for this multibody file. The namespace can be overridden for a specific body in the body data-block
***

* #### mesh
This specifies the mesh file for this body. If the mesh is empty, this body shall be treated without collision. The mesh name is combined with the high-resolution path to get the visual mesh and with low-resolution path to get the collision mesh.

***

* #### collision mesh
If a collision mesh is defined, it is used for low res collision mesh. If not, the **mesh** is used for collision. The **collision mesh** is combined with the **low-resolution path** to get the full filename of the low-resolution mesh
***

* #### shape
Instead of specifying a mesh, a shape can be specified for the visual's and collision. Supported shapes are BOX, CYLINDER, CAPSULE, CONE, and SPHERE
***

* #### geometry
The geometry for the **shape** defined above. For a box, x, y, and z are required, for rest of the shapes; radius and height are required.
***

* #### collision shape
If specified, the collision shape shall be considered. A body can still have a **mesh** specified for visualization and then this **collision shape** item for using a primitive shape for collisions. Supported shapes are BOX, CYLINDER, CAPSULE, CONE, and SPHERE
***

* #### collision geometry
The geometry for the **collision shape** defined above. For a box, x, y, and z are required, for rest of the shapes; radius and height are required.
***

* #### mass: 0.3
This is the mass of the body. If the mass is set to 0, the body is kinematic.

***

* #### location:
This is the initial location of the body in the world frame. This location will of course change as the simulation goes on and the body interacts with other objects in the simulation

***

* #### inertia:
This is the principal inertia of the object. If not specified. It is computed internally by utilizing the collision mesh's geometry

***

* #### inertial offset:
This is the inertial offset from the mesh origin. This helps in giving the user the ability to define a mesh's origin at a convenient location without having to place it at the body's center of mass. The inertial offset can then be added. If the inertial offset if not specified, it is computed internally by the AMBF Framework based on the collision mesh's geometry.

***

* #### publish children names:
Boolean to enable/disable publishing of children names for this body in its **afState Message**
***

* #### publish joint names:
Boolean to enable/disable publishing of joint names for this body in its **afState Message**
***

* #### publish joint positions:
Boolean to enable/disable publishing of joint positions for this body in its **afState Message**
***

* #### friction:
Surface friction for the body.
***

* #### damping:
Damping for this body. A value in the range [0-1]
***

* #### restitution:
Restitution for the body. A value in the range[0-1]. 1 means full conservation of energy on collision and 0 means all energy dissipated
***

* #### collision groups:
A list of integers to classify what collision groups if this body part of.
***

* #### controller:
Linear and Angular controller's PD gains for the body. If not specified, they are estimated from the body's mass and inertia.
***

* #### color:
There are three different ways of specifying the color for a body. You can either use the **color** key and then specify a color from the [ambf/ambf_models/descriptions/color/colors.yaml](https://github.com/WPI-AIM/ambf/blob/master/ambf_models/descriptions/color/colors.yaml)

***

* #### color rgba:
Instead of picking a color name as in the field above. You can specify the raw color value using:
```yaml
color rgba: {r: 0.5, g: 0.5, b: 0.5, a: 1.0}.
```

***

* #### color components:
For even greater control of color. You can use the color components key:

```yaml
color components:
    ambient: {level: 1.0}
    diffuse: {r: 0.955, g: 0.4814, b: 0.3072}
    specular: {r: 1.0, g: 1.0, b: 1.0}
    transparency: 1.0
```
