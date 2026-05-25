Programming Paradigms / styles of programming : 

1. Procedural
2. Functional
3. Object oriented
4. Event driven
5. Logic
6. Aspect oriented

Out of this.... Object oriented and Functional are Top most paradigms we use these days. 

these are all ways or styles of writing the programs., 

Languages like Small talk -> is single paradigm
Python, Ruby, Java, js -> are Multiple paradigms.

OOPS are working on the concept of object. These objects are units that contains Data (State) and Methods (Behaviour).

In oops -> object-> we get togther the data and methods. in a single object
In Functional programming. we take the opposite approach. We assume the data and methods are fundementally different. So we keep them separate. 

-----xxxxxx------

Benifits of oops : 

Reduce complexity - Reducing complexity by breaking down larger comple application.
Easier maintenance - More managable and easier to maintain object
Code Reuse - 
Faster development

----xxxxx-----xxxxxxx---

Both oops and functional programming are great. based on the requirement we have to chhose the correct one. 

--------xxxxxxxx-----xxxxx--------

OOPS 
Classes : 

- Classes are essential for oops. We are going to learn about Encapsulation and Abstraction.
- Constructors
- Getters and setters
- Method overloading

Class - A blue print for creating objects.
Object - An Instance of a class. 

UML - unified Modeling Language

- A class have both state and behavioural. state means - what is the values stored presently. Behaviour means - action itms, moved stopped, turnon, turnoff

----xxxx-----xxx

creating classes: 

Class can have fields and methods. inside method also we can access the fields.

Objects : 

An instance of a class. initialize with new operator.

var textBox1 = new TextBox();

if we dont assisgn any values to the class fields and try to accessit means. it shows nullpointer exception in java.

To avoild this, we can initialize with default valyes.
public String text = "";

------------
Memory allocation : 


Deallocate memory : 

var obj1 = new Object();
When a method ends / exit -> java run time will immediately remove all the variables (obj1) that stored in the stack. Now we endup with object in the heap (new Object()). since stack is removed there is no reference in the new Object(). so GC will remove it from the heap. This is called garbage collection (GC).

----x----xxxxxx----xxxxxx------

Proceduaral programming : 

- With a sigle class using Main method and multiple functions (Procudures) are called PRocedural programming. Instead of write entire code in main method, split the code into multiple fuctions also called as procedural programming. For this issue will be resolved by OOps.
- If something goes wrong, we have to go all opver the places in the code and work on it.
- Lack of re-usablity
- If a function have multiple parameters means, it should not a proper code. we have to implment oops here

---xxxxxx------xxxx------xx-x-------

Encapsulation : 




