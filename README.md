# Cybershoes Quest SDK For UE4  

## The Fast method  

In most cases this works. Cybershoes output a single joystick press for entering sprint mode. 

How to do it:  
UNreal Engine > Engine Input > Bindings  
* add Gamepad Left Thumbstick to your Y-Axis and X-Axis Mappings  
* add Gamepad Left Thumbstick Button (Press) to your toggle "Sprint" Action

![UE4-gamepad-cybershoes-implementation](https://user-images.githubusercontent.com/42228867/122557491-25c23880-d03d-11eb-8a55-0dcfb2195e55.jpg)


The Cybershoes receiver outputs a left stick x/y gamepad signal relative to the HMD orientation. This signal tells the game in which direction the shoes are moving.  

Walking in the direction of the shoes works well, if the same factor is applied for speed y (forward) as for speed x (sidewards). Either you or we test how the speed feels.  

On https://www.cybershoes.com/questsetup/ [Game HINTS] we explain what setting to choose in game. 

## Blueprint method   

Locate your Motion Controller Pawn (or First Person Character) Blueprint  

Right click>type Gamepad Events> choose Gamepad Left Thumbstick X-Axis  
Right click>type Gamepad Events> choose Gamepad Left Thumbstick Y-Axis 

![UE4 blueprint method find gamepad event](https://user-images.githubusercontent.com/42228867/112618965-05f8eb00-8e27-11eb-9ce6-79359749d867.jpg)

Out of your Camera, drag Get Forward Vector… and repeat with Get Right Vector  
Use float * float to bring up multiplicator to adjust speed (use same value for X & Y !!)  
Wire up like below with Add Movement Input  

![UE4 blueprint method](https://user-images.githubusercontent.com/42228867/112619020-1610ca80-8e27-11eb-8fcd-f25cc65cbc08.jpg)  

Cybershoes users are mostly nerved by “artificially” imposed stamina and “run/walk” barriers.



