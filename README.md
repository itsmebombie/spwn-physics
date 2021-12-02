# spwn-physics
a simple (and pretty bad) library to add physics to spwn

## commands and arguments:
(<> mandatory, [] optional)
```
dynamicObjects(<objectsGroup>,<bottomPartOfObjectCollisionGroup>,[objectsWeight]) //add a falling object
dynamicObjects() //print all dynamic objects and their properties

staticObject(<staticObjectsCollisionGroup>) //set the static object
staticObject() //print the static object's properties

velocity(<name>,<objectsGroup>,<fullObjectsCollisionGroup>,[velocityX],[velocityY],[objectsWeight],[duration],[spawnTriggerId]) //add velocity to an object
velocity() //print all dynamic objects affected by velocity and their properties
```

## how to set up:

in the geometry dash editor, you must first add 2 objects and 4 collision blocks like this:

![image](https://user-images.githubusercontent.com/92307212/139891396-1b4a343f-e4c4-41bd-be28-4087fda352ac.png)

then, you must scale 2 of those collision blocks like this

![image](https://user-images.githubusercontent.com/92307212/139892244-d1507e91-bddd-4b31-bea8-870eac799792.png)

then, you must set the first object's group id to the "fallingObjectsGroup"
then, you must set the first collision block's block id to the "fullObjectsCollisionGroup" and make it a "dynamic block", and set the next 2 collision blocks block ids to "bottomPartOfObjectCollisionGroup" and also make them "dynamic blocks"
now you must set the last collision block's block id to the "staticObjectsCollisionGroup" collision group id, and merge the collision blocks into the corresponding objects like this:

![image](https://user-images.githubusercontent.com/92307212/139893181-f222d6ff-c61b-4a12-b13d-8491d16c7ab2.png)
(you should also scale the bigger block to 0.97 and move it so it doesnt touch the bottom part of the block completely)

now you only need to write code, build the script and you're done!
here's an example to help with the writing code part:

## example of use:
```
p = import physics //imports the library

p.dynamicObjects(1g,1b,10) //sets the dynamic object's group to "1g", sets it's bottom collision group to "1b" and it's weight to "10", this will be the dynamic object
p.dynamicObjects(2g,4b,20) //adds another dynamic object with it's group being "2g", it's bottom collision group being "2b" and it's weight being "20"
p.staticObject(3b) //sets the static object's collision group to "3b", this will be the object that the falling object will fall on
p.velocity(1,1g,2b,6,15,20,1,3g) //sets the name to "1", the dynamic object's group to "1g", sets it's full block collision group to "3b", the amount it will move on the x axis to "6 * 50", the amount of movement on the y axis to "15 * 10", it's weight to "20", the duration to "1" and the group id (the id that should spawn this, keep blank for no group spawn)

$.print(p.staticObject()) //prints the static object's properties (in this case it will print "3b")
$.print(p.dynamicObjects()) //prints all of the dynamic and their properties (in this case it will print "{1g: [1g,1b,10],2g: [2g,2b,20]}")
$.print(p.velocity()) //prints all of the objects that will be affected by velocity and their properties properties (in this case it will print "{1g: [1g,1b,6,15,20,1]}")


```
