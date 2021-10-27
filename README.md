# spwn-physics
a simple (and pretty bad) library to add physics to spwn

## commands and arguments:
```
dynamicObjects(fallingObjectsGroup,fallingObjectsCollisionGroup,objectsWeight) //add a falling object
dynamicObjects() //print all falling objects and their properties

staticObject(staticObjectsCollisionGroup) //set the static object
staticObject() //print the static object's properties
```

## how to set up:

in the geometry dash editor, you must first add 2 objects and 2 collision blocks like this:

![image](https://user-images.githubusercontent.com/92307212/138601195-ce6423c6-5184-447c-9239-53bc99b71adc.png)

then, you must set the first object's group id to the "fallingObjectsGroup"
then, you must set the first collision block's block id to the "fallingObjectsCollisionGroup" and make it a "dynamic block"
now you must set the second collision block's block id to the "staticObjectsCollisionGroup" collision group id, and merge them into the corresponding blocks like this:

![image](https://user-images.githubusercontent.com/92307212/138601213-cb1ae6e4-98c1-41b9-a728-6c8e25d9be5f.png)

now you only need to build the script and you're done!

## example of use:
```
p = import physics //imports the library

p.dynamicObjects(1g,1b,2) //sets the dynamic object's group to "1g", sets it's collision group to "1b" and it's weight to "2", this will be the falling object
p.dynamicObjects(2g,2b,3) //adds another falling object with it's group being "2g", it's collision group being "2b" and it's weight being "3"
//p.s. weight values higher than "50" won't change much
p.staticObject(3b) //sets the static object's collision group to "3b", this will be the object that the falling object will fall on

$.print(p.staticObject()) //prints the static object's properties (in this case it will print "3b")
$.print(p.dynamicObjects()) //prints the static object's properties (in this case it will print "[[1g,1b,2],[2g,2b,3]]")


```
