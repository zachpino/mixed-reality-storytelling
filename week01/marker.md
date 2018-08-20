### Marker-Based Augmented Reality

-----

Though not nearly as interesting as object-recognition or spatially-aware Augmented Reality, cleverly deployed marker-based AR still offers bountiful design opportunities.

These examples will only work in Google Chrome or Mozilla Firefox. Safari and related browsers block the necessary webcam refresh rate required of AR.js.

-----

##### Marker File Generation

First, we need a marker to pin 3d objects to in our AR scene. [This awesome website](https://jeromeetienne.github.io/AR.js/three.js/examples/marker-training/examples/generator.html) generates the necessary images and pattern files. Ensure you upload a black and white, asymmetric image *with no transparency* for best results.

After you upload the image and size it with the interactive tool to your liking, download the resulting image for printing, and marker file for coding. Place the marker file next to your `index.html` file.

-----

##### Temporarily Reduce Security


In order to get past Google Chrome's annoying security defaults (this is a temporary measure), we should launch the browser without its highest security settings.

In Terminal (on macOS)...

```
open /Applications/Google\ Chrome.app --args --disable-web-security --user-data-dir
```

-----

##### Using an AR Marker


```html
<html>
	<head>
	    <!-- import the A-Frame library -->
	    <script src="https://aframe.io/releases/0.8.0/aframe.min.js"></script>
		<!-- include ar.js for A-Frame -->
		<script src="https://jeromeetienne.github.io/AR.js/aframe/build/aframe-ar.js"></script>
	</head>

	<body>
		<!--make an a-frame scene with ar.js support-->
		<a-scene embedded arjs >

			<!-- import custom marker -->
			<a-marker preset='custom' type='pattern' url='marker.patt'>
				<!-- 3d text, the coordinates here are *marker-relative* -->
        		<a-box position="1 .5 -2.5" width="1" height="1" depth="1" color="#a0a">
			</a-marker>
			
		</a-scene>
	</body>
</html>
```

Multiple markers can be prepared and linked to different a-frame entities. How could we animate an entity pinned to a marker?

-----

##### Restore Security

Quit Google Chrome, and the reduced security will be restored.

-----

Now, do your [homework](README.md)! 

