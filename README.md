# CS 4331-002 - Virtual Reality Project 1
## Due: February 20, 2018
## Video demonstration link
https://www.youtube.com/upload?redirect_to_classic=true
## Project link
https://sksdow.github.io/VR_project1/project1/index.html

## Report

### What I learned
- The basics of Aframe and Threejs
- The basics of Javascript and HTML
- Designing techniques that takes into account user experience

### General issues
- Aframe is buggy, I had alot of issues with the physics library
- Making sure there are not too many high polygon or high vertices models
- Google cardboard does not register clickables very well

### Contributors
Tien Dang

## Key Features

### Area Specific Lighting
Each light in the scene is a point light. "point" is a "type" attribute of the html element "a-light", a point light radiates in all (6) directions within a specify "radius" attribute. Each light only covers a specific area in the scene, which gives the user a more realistic feeling.

Take the dining area light for example;
```html
<a-entity position="4.797 2.164 3.298" id="table_light_entity" >
  <a-light
    type= "point" intensity= "3" distance= "3" id="table_light_source">
  </a-light>
</a-entity>
```
![Image of table light](https://sksdow.github.io/VR_project1/project1/report_screenshots/dining_table_light.jpg)

### Interactable Objects

All interactable objects in this projects are clickable, which mean the object changes its state if is clicked on. This is implemented using a mix of the aframe library and a little bit of javascript. Firstly, the camera entity must wrap arround a raycaster entity html element, which is then defined as a ".intersectable". 
```html
  <a-entity position="14.81 1 -0.59" rotation="0 90 0" id="mycamera" camera="fov: 50" universal-controls>
    <a-entity raycaster="far: 150; objects: .intersectable" cursor geometry="primitive: ring; radiusOuter: 0.015;
      radiusInner: 0.01; segmentsTheta: 32" material="color: #283644; shader: flat" position="0 0 -0.75">
    </a-entity>
	</a-entity>
```
Secondly, the clickable object html element "class" attribute must be defined as "intersectable", and its "onclick" attribute must be set to a javascript function.
```html
<a-box id="ceiling_light_switch" scale="1.3 0.2 0.8" color="#00ff40" position="0 0 2.042" class="intersectable"
onclick="setCeilingLight()">
</a-box>
```
Thirdly, the javascript function will dynamically changes an appearance, physical attribute, or start animation of the html elements that is specified in the function. In the following example, the html elements of the ids; "ceiling_light_switch", "ceiling_light_source" are being modified.
```javascript
var ceiling_light_on = true;
function setCeilingLight(){
	var light_switch = document.querySelector('#ceiling_light_switch');
	var light        = document.querySelector('#ceiling_light_source');
	if(ceiling_light_on){
		light.setAttribute('intensity', "1");
		light_switch.setAttribute('color', "#FF0000");
		ceiling_light_on = false;
	}
	else{
		light.setAttribute('intensity', "5");
		light_switch.setAttribute('color', "#00ff40");
		ceiling_light_on = true;
	}
}
```
This is the effect of
```javascript
light.setAttribute('intensity', "1");
light_switch.setAttribute('color', "#FF0000");
```

This is the effect of
```javascript
light.setAttribute('intensity', "5");
light_switch.setAttribute('color', "#00ff40");
```

#### Other interactable objects
ceiling fan, rotates:

kitchen light, turns on and off:

lamp light, turns on and off:

bedroom light, turns on and off:


## Models and Links





