### Simple Object Animation

-----

What good are static objects?

```html
<html>
  <head>
    <!-- import the A-Frame library -->
    <script src="https://aframe.io/releases/0.8.0/aframe.min.js"></script>
  </head>
  
  <body>
    <a-scene>
      <!-- Make a box! -->
        <a-box position="1 .5 -2.5" width="1" height="1" depth="1" color="#a0a">
            <a-animation attribute="position" from="1 .5 -2.5" to="-1 1.5 -2.5" dur="3000"></a-animation>
            <a-animation attribute="color" from="#a0a" to="#0ff" dur="5000"></a-animation>
        </a-box>
        
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

This is the same scene, with some motion! The cube now moves around a bit, and changes color. All the code to make that motion happen is nested *within* the html element that should experience the movement, and the `<a-animation>` html element contains all of the settings for the motion/transition including start and end state, as well as duration. Here, the box is animated separately from the ground plane. Any a-frame entity can accept animations in this way.

You can read through other animation opportunities in the [a-frame documentation](https://aframe.io/docs/0.8.0/core/animations.html).

-----

Note that, in the previous example, the box moved and changed color simulataneously. What if we wanted those transitions to be sequential instead? There are a few ways to sequence animations, including setting `delay` or `begin`.

With `delay`...

```html
<html>
  <head>
    <!-- import the A-Frame library -->
    <script src="https://aframe.io/releases/0.8.0/aframe.min.js"></script>
  </head>
  
  <body>
    <a-scene>
      <!-- Make a box! -->
        <a-box position="1 .5 -2.5" width="1" height="1" depth="1" color="#a0a">
            <a-animation attribute="position" from="1 .5 -2.5" to="-1 1.5 -2.5" dur="3000"></a-animation>
            <a-animation attribute="color" from="#a0a" to="#0ff" dur="1000" delay="3000"></a-animation>
        </a-box>
        
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

Same thing, with `begin` instead...

```html
<html>
  <head>
    <!-- import the A-Frame library -->
    <script src="https://aframe.io/releases/0.8.0/aframe.min.js"></script>
  </head>
  
  <body>
    <a-scene>
      <!-- Make a box! -->
        <a-box position="1 .5 -2.5" width="1" height="1" depth="1" color="#a0a">
            <a-animation attribute="position" from="1 .5 -2.5" to="-1 1.5 -2.5" dur="3000"></a-animation>
            <a-animation attribute="color" from="#a0a" to="#0ff" dur="1000" begin="3000"></a-animation>
        </a-box>
        
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

There is currently no meaningful difference, but once we play with scripting experiences, `begin` will become much more powerful and allow event-based reactivity.

-----

You can also control timing and repetition. Boomerang! 

```html
<html>
  <head>
    <!-- import the A-Frame library -->
    <script src="https://aframe.io/releases/0.8.0/aframe.min.js"></script>
  </head>
  
  <body>
    <a-scene>
      <!-- Make a box! -->
        <a-box position="0 .5 -2.5" width="1" height="1" depth="1" color="#a0a">
          <a-animation attribute="position" from="0 .5 -2.5" to="0 3 -2.5" direction="alternate" repeat="indefinite" dur="1000"></a-animation>
          <a-animation attribute="color" from="#a0a" to="#a00" direction="alternate" repeat="indefinite" dur="1000"></a-animation>
        </a-box>
        
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

Setting `repeat` to a numerical value will allow a finite number of bounces.

-----

Let's leave behind VR and investigate some [marker-based Augmented Reality](marker.md).