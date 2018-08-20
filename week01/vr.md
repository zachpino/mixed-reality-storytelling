### Simple VR Immersive Environment and Object Creation

-----

A-Frame makes it easy to create virtual reality scenes in web browsers. All it takes is a bit of well-structured code.

This is the basics of an A-Frame VR scene, wrapped in a simple HTML page.

```html
<html>
	<head>
		<!-- import the A-Frame library -->
		<script src="https://aframe.io/releases/0.8.0/aframe.min.js"></script>
	</head>
	
	<body>
		<a-scene>
			<!-- Make a box! -->
  			<a-box position="1 .5 -2.5" width="1" height="1" depth="1" color="#a0a"></a-box>
  			
  			<!-- Make a ground plane! -->
  			<a-plane position="0 0 0" rotation="-90 0 0" width="10" height="10" color="#377"></a-plane>
  			
  			<!-- Make background color! -->
  			<a-sky color="#eee"></a-sky>
  			
  			<!-- Make a controllable camera! -->
  			<a-camera look-controls-enabled wasd-controls-enabled position="0 1 0"> </a-camera>
		</a-scene>
	</body>
</html>
```

The important bits are all contained within the `<a-scene>` element. Consult how you can style and add other 3D and 2D primitives in the [A-Frame documentation](https://aframe.io/docs/0.8.0/primitives/a-box.html) like spheres, cylinders, polyhedra, mapped images and videos, and global illumination sources. All of these a-frame *entities* are added to the scene and styled in the same way. Before checking the documentation, could you guess how to add a sphere? How might you change the opacity of the sphere?

-----

Let's add some motion to the scene with some [animation](animate.md).

