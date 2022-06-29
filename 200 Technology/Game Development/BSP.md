[[Unreal Engine]]

# BSP

This basically refers to a programs geometry tools, like geometry brushed.
Also called Constructive Solid Geometry (CSG).

Mainly used to prototype levels, as the shapes added with this tool is performance heavy.

## The 7 types of BSP
- **Box**: A simple box, with the ability to "hollow" it out, deleting "walls" to quickly prototype rooms and such. It is also possible to set the "wall" thickness, to make it look like an actual room.
- **Cone**: Not just a cone, as you can define the amount of sides it has. Just like the box, the "wall" thickness can be adjusted.
- **Cylinder**: Just like the cone, not just a cylinder, as you can define the amount of sides it has.
- **Curved stair**: A curved staircase that can wrap around other objects, but cannot wrap over itself.
- **Linear stair**: Just a staircase. No bend.
- **Spiral stair**: Just a spiral staircase, which *can* wrap over itself.
- **Sphere**: Just a sphere.

## The two types of brushes
- **Additive**: This brush adds material to a BSP, can be used for adding walls or terraforming.
- **Subtractive**: The opposite of **Additive**, takes away material from BSP. Can be used to create windows or holes in the ground for lakes for example.