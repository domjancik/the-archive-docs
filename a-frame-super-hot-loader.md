# A-Frame Components

## Remove function

`remove` can be implemented to run any code on component disconnection.

Possible uses:
- To return parent entity to original state after removing component
- Clean up resources

## Tick function

Implement `tick` with logic to run every frame

## Underlying element

Access the parent element via `this.el`

## 3D Object, transformations

Access the 3D object via `this.el.object3D`

Change transform by adjusting one of the following properties:

```
this.el.object3D.rotation.x
this.el.object3D.rotation.y
this.el.object3D.rotation.z
this.el.object3D.position.x
this.el.object3D.rotation.y
this.el.object3D.rotation.z
```