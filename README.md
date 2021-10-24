# spwn-physics
a simple library to add physics to spwn

example of use:
```
p = import physics //imports the library

p.dynamicObjects(1g,1b,2) //sets the dynamic object's group to "1g", sets it's collision group to "1b" and it's weight to "2", this will be the falling object
p.dynamicObjects(2g,2b,3) //adds another falling object with it's group being "2g", it's collision group being "2b" and it's weight being "3"
//p.s. weight values higher than "8" may cause some inaccuracy in the "landing" point of the object (on the Y axis)
p.staticObject(3b) //sets the static object's collision group to "3b", this will be the object that the falling object will fall on

$.print(p.staticObject()) //prints the static object's properties (in this case it will print "3b")
$.print(p.dynamicObjects()) //prints the static object's properties (in this case it will print "[[1g,1b,2],[2g,2b,3]]")


```
