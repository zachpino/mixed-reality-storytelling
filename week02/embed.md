### Embedding Animated Models in Marker-Based AR

-----

A-Frame offers lots of awesome animation tools, but it still is not nearly as expressive as dedicated 3d animation tools like Maya. With the correct export settings, we can embed any model with its accompanying animations into an A-Frame AR or VR experience.

-----

##### Export Settings

After [installing the plugin](https://github.com/matiascodesal/maya-glTF) into Maya and modeling and animating...

```
File -> Export All

Filename = ___.gltf
Files of Type = glTF Export
```

Be absolutely certain you name your file with the extension `.gltf`!

-----

##### Loading Animated Models into A-Frame

You can now load your model with animations into A-Frame. Read more about [loading and handling gltf files](https://aframe.io/docs/0.8.0/components/gltf-model.html), as well as [animating them](https://github.com/donmccurdy/aframe-extras/tree/master/src/loaders#animation).

```html
<html>
<head>
	<!-- include A-Frame -->
	<script src="https://aframe.io/releases/0.8.0/aframe.min.js"></script>
	<!-- include ar.js for A-Frame -->
	<script src="https://jeromeetienne.github.io/AR.js/aframe/build/aframe-ar.js"></script>
	<!-- for accessing animations in gltf files -->
	<script src="https://cdn.rawgit.com/donmccurdy/aframe-extras/v4.1.2/dist/aframe-extras.min.js"></script>
</head>
<body>
	<!-- create an a-frame fullscreen, ar capable scene -->
	<a-scene embedded arjs>

		<!-- find custom marker -->
		<a-marker type='pattern' url='marker.patt'>
			<!-- build the content that will 'stick' to the marker--> 
			<!-- load a gltf model with animation. note the configurable animation properties -->
			<a-entity position="" scale=".25 .25 .25" gltf-model="url(whatever.gltf)" animation-mixer="loop:pingpong"></a-entity>
		</a-marker>
		<!-- create the camera to 'see' the 3d object. Here we give it defauly 0 0 0 position-->
		<a-entity camera></a-entity>

	</a-scene>
</body>
</html>
```