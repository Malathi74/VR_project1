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
Each light in the scene is a point light. "point" is a "type" attribute of the element "a-light", a point light radiates in all (6) directions within a specify "radius" attribute. Each light only covers a specific area in the scene, which gives the user a more realistic feeling.

Take the dining area light for example
```html
<a-entity position="4.797 2.164 3.298" id="table_light_entity" >
<a-light
type= "point" intensity= "3" distance= "3" id="table_light_source">
</a-light>
</a-entity>
```

