Design and make web-based VR house with A-FRAME
---
[**LIVE DEMO** ](https://chaupmcs.github.io/aframe_vr_house/)

[**VIDEO DEMO**](https://www.youtube.com/watch?v=SZVZ-kMAp8k)

![Overview](/screenshots/beginning_scene.png)

This is a basic web-based VR application that allows us to navigate through a decorated house and interact with some objects inside.
In this project, we decorated a 2-floor house [6], furnished the room, and created some interactions and animations.
The application was implemented with [A-FRAME framework](https://aframe.io/) [1].

The following screenshots highlight some of the features/components of the house.

## Interactions/Animations
1. **Cat**  

Hover the cat to see the text. When clicking on the cat to snuggle it, you will hear the meows.
The mouse hover is done by `AFRAME.registerComponent("name-on-hover")`, with events `addEventListener("mouseenter")` and `addEventListener("mouseleave")`, and the audio is attached to the cat by `sound="src:#cat_meow; on: click"`
![pet_me](/screenshots/pet_me.gif)


<br />



2. **TV**
               
Click on the TV to toggle it. While on, the TV displays an image and plays a song. Click on the TV again to turn it off (black screen). The TV shows the embedding image by changing material color from black to white: `TVScreen.setAttribute('material', 'color', 'white')`
<br />

![TV](/screenshots/TV.gif)


<br />



3. **Teleport upstairs/downstairs** 
                                            
To go up/downstairs, use the teleport buttons near the stairs. 
It will change the position and rotation of the camera to move us to go up/downstairs. 
For example, to move up:
```
teleport_up.addEventListener('click', function () {
        cam.setAttribute('position', {x: 10, y: 14, z: 12});
        cam.setAttribute('rotation', {x: 0, y: 50, z: 0});
    });
```
<br />

![teleport_up](/screenshots/teleport_up.gif)

<br />

![teleport_down](/screenshots/teleport_down.gif)


<br />



4. **Time machine**  
       
Click on the rail switch to turn back time, when there's no COVID19. 
Back then, we can have friends come over for a small party in the house. 
However, many things changed when the virus came. 
Not only no more parties up there, but these changes are reflected in the living room and working room as well. 
For example, the toy car and the cat show up in the present only. Perhaps, we need these little things to overcome the quarantine while stuck indoors.
The bookshelf changes its position too. It was in the working room but later moved out to the living room, next to the TV.
Some medical stuff like the mask in the desk will be disappeared when the time machine running.

- To show/hide the objects or change their position, I made use of `position` and `visible` attributes.
For example, three human models in the party will be shown by changing `visible` from `false` to `true`.
- When turning back time, the color will be changed to purple. We can still use the teleport, but no longer interact with other objects (e.g., Disable the interaction with TV, light switch).
- Sound effects: 
    - Turn the time machine on: When clicking on the rail switch, it plays the sound of the time machine so that we know it's just clicked, then the background noise in the party effect. 
    - Turn the time machine off: Toggling the switch again, it plays the time machine effect. After that, the background noise effect will be ceased.
<br />

![time_machine](/screenshots/time_machine.gif)


<br />



5. **Toy car**  
       
The car is running by changing its `position` attribute via `<a-animation>`.
<br />

![toy_car](/screenshots/toy_car.gif)


<br />



6. **Ceiling fan**  
       
Similar to the above-mentioned toy, but this time with `rotation` attribute.
<br />

![fan](/screenshots/fan.gif)
<br />



## Models

### Custom Made Models
I used basic objects to create five models.
For example, the TV model consists of five cubes. Regarding the speaker, I used two cubes and two circles to create it.
![my_models](/screenshots/custom_made_models.png)


### External Models
Most of the models are downloaded from [Sketchfab](https://sketchfab.com/) [2] and [Sweet Home 3D](http://www.sweethome3d.com/freeModels.jsp) [3].
Main models are listed as following:
1. Sofa: [https://sketchfab.com/3d-models/sofa-web-0fe3264cdfa8482a83830450d05ae1f1](https://sketchfab.com/3d-models/sofa-web-0fe3264cdfa8482a83830450d05ae1f1)
2. Frame Squirrel: [http://www.sweethome3d.com/searchModels.jsp?model=squirrel&x=0&y=0](http://www.sweethome3d.com/searchModels.jsp?model=squirrel&x=0&y=0)
3. Desk light: [http://www.sweethome3d.com/searchModels.jsp?model=desk+light&x=0&y=0](http://www.sweethome3d.com/searchModels.jsp?model=desk+light&x=0&y=0)
4. Desk: [http://www.sweethome3d.com/searchModels.jsp?model=desk&x=0&y=0](http://www.sweethome3d.com/searchModels.jsp?model=desk&x=0&y=0)
5. Face mask: [https://sketchfab.com/3d-models/discarded-covid-19-mask-e778607a19f64f1ca7bd5f405252130f](https://sketchfab.com/3d-models/discarded-covid-19-mask-e778607a19f64f1ca7bd5f405252130f)
6. Toilet paper: [https://sketchfab.com/3d-models/isolation-creation-ii-toilet-paper-e831aa5fdaca45e2b63352714833dc55](https://sketchfab.com/3d-models/isolation-creation-ii-toilet-paper-e831aa5fdaca45e2b63352714833dc55)
7. Wood logs: [http://www.sweethome3d.com/searchModels.jsp?model=log&x=0&y=0](http://www.sweethome3d.com/searchModels.jsp?model=log&x=0&y=0)
8. Toy car: [https://sketchfab.com/3d-models/fallout-car-2-cf54e5b166644fc7ade7bbaac502a04f](https://sketchfab.com/3d-models/fallout-car-2-cf54e5b166644fc7ade7bbaac502a04f)
9. Rail Switch: [https://sketchfab.com/3d-models/rail-switch-36d498bb02a741db9eeb2510d32dc447](https://sketchfab.com/3d-models/rail-switch-36d498bb02a741db9eeb2510d32dc447)
10. Seamless texture - Stone wall: [https://sketchfab.com/3d-models/seamless-texture-stone-wall-0bd6f3f8ec2342618beb52ec920ae65b](https://sketchfab.com/3d-models/seamless-texture-stone-wall-0bd6f3f8ec2342618beb52ec920ae65b)
11. Flower pot: [https://sketchfab.com/3d-models/flower-pot-with-succulent-plants-acce0c2e1e5b4986b4ff18198eb90e3e](https://sketchfab.com/3d-models/flower-pot-with-succulent-plants-acce0c2e1e5b4986b4ff18198eb90e3e)
12. Coffee maker: [http://www.sweethome3d.com/searchModels.jsp?model=coffee&x=0&y=0](http://www.sweethome3d.com/searchModels.jsp?model=coffee&x=0&y=0)
13. Glass table: [http://www.sweethome3d.com/searchModels.jsp?model=glass+table&x=0&y=0](http://www.sweethome3d.com/searchModels.jsp?model=glass+table&x=0&y=0)
14. Bookshelf: [http://www.sweethome3d.com/searchModels.jsp?model=bookshelf&x=0&y=0](http://www.sweethome3d.com/searchModels.jsp?model=bookshelf&x=0&y=0)
15. Ceiling fan 1: [https://sketchfab.com/3d-models/ceiling-fan-lp-20026b96c5144e5b923f1c8c4f8d41e7](https://sketchfab.com/3d-models/ceiling-fan-lp-20026b96c5144e5b923f1c8c4f8d41e7)
16. Ceiling fan 2: [http://www.sweethome3d.com/searchModels.jsp?model=fan&x=0&y=0](http://www.sweethome3d.com/searchModels.jsp?model=fan&x=0&y=0)
17. Guitar: [https://sketchfab.com/3d-models/low-poly-guitar-757b3b5aaf6d4052933edc329c4f5aa5](https://sketchfab.com/3d-models/low-poly-guitar-757b3b5aaf6d4052933edc329c4f5aa5)
18. Pirate Girl: [https://sketchfab.com/3d-models/pirate-dc4d64fbe3f24335b12cae289270ef39](https://sketchfab.com/3d-models/pirate-dc4d64fbe3f24335b12cae289270ef39)
19. Girl 2: [https://sketchfab.com/3d-models/free-download-attractive-african-woman-236-f2c29b6947f34237a0bfdc777120ef28](https://sketchfab.com/3d-models/free-download-attractive-african-woman-236-f2c29b6947f34237a0bfdc777120ef28)
20. Boy: [https://sketchfab.com/3d-models/game-ready-character-e321e805190748c6a94dbe11b97e3023](https://sketchfab.com/3d-models/game-ready-character-e321e805190748c6a94dbe11b97e3023)

...

## Sound effects
1. Light switch
2. Meows
3. Teleport 
4. TV (UEFA Champions League Anthem)
5. Time machine
6. Background noise in the party

## Useful tools
- [A-FRAME inspector](https://github.com/aframevr/aframe-inspector) [4]: a simple but helpful tool that can help us easier to locate the object in the scene.  
Just put an extra line in the code, the application will turn into an Inspector.
```    
    <script src="https://cdn.jsdelivr.net/gh/aframevr/aframe-inspector@master/dist/aframe-inspector.min.js"></script>
```

![fan](/screenshots/aframe_inspector.png)
<br />

- [Sweet Home 3D](http://www.sweethome3d.com/) [5]: a free interior design tool for drawing and designing the house. It allows us to arrange the furniture inside visually as well.
  <br />

- [Blender](https://www.blender.org/) [7]: Good tool for making your own 3D models

## Credits
For the design of the 2-floor house in this project, I borrowed from [DreamHomeVR](https://github.com/joyellealina/DreamHomeVR) [6].
                                                                                      
## REFERENCES
[1] A-FRAME: https://aframe.io/  
[2] Sketchfab: https://sketchfab.com/  
[3] Sweet Home 3D models: http://www.sweethome3d.com/freeModels.jsp  
[4] A-FRAME inspector: https://github.com/aframevr/aframe-inspector  
[5] Sweet Home 3D (free interior design application): http://www.sweethome3d.com/  
[6] DreamHome: https://github.com/joyellealina/DreamHomeVR  
[7] Blender: https://www.blender.org/
