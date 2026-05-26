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

- 1st principal of oops.
- Bundle the data and methods that operate on the data in a single unit or object.

public class Employee {
public int baseSalary;
public int hourlyRate;

public int calculateWage(int extraHours){
return baseSalary + (hourlyRate * extraHours);
｝

｝

// call the class and initialize it in Main method and access it.

- in this example both data and methods are bundled in a class. using object we can access.

---xxxxxx------xxxxx------xxx

Getter and Setter :

- consider from the above example, if user try to enter the 0 or -ve values in the base salary, the result will be wrong. we can avoid this issue from 2 types.
- 1. use validation from ui like entyer value >0
  2. or we can encapsulate this validation inside the class.
 
- public int baseSalary;
consider this line, the baseSalary field is accessible outside of the class.
- private int baseSalary;
This field cant be accessible outside of the class.

public void setBaseSalary(int baseSalary) {
if (baseSalary <= 0)
throw new IllegalArgumentException ("Salart cant be 0 or less");

this.baseSalary = baseSalary;

}

public int getSalary(){
return baseSalary;
}
-------


instead of directly assign the values from the object fields. Assign via set function/method and get the value via get function. Here we can handle validation and avoid issue while calling the calculate functions.

----xxxx-----xxx-----xxx------

Abstraction :
- 2nd principal of oops
- Abstraction means reduce complexity by hiding unnecessary details in our classes.
- Eg : Think of a remote control of our tv. it has bunch of buttons, inside the remote have electronic board and trsnsistors. We wont directly work with these transistors. these are the implementation details. there is so mych complexity is thre. we dont want to iunderstand that. We just use the remote to change the channle and volume. We dont care what happens under the hood. we dont care what state is this transistors doing. This is abstraction in action. 
- So with abstraction, we are going to hide the implementation details of our classes. Treat it like a black box.
- We dont care what is inside, we just work with simple interface.

- Eg : using getter and setter and privare variables, we hide the basesalary field.
----xxxxxx-----xxxx------xxxx

Coupling : 
- How much a class is dependent upon or coupling to another class.
- In a class if we have more methods the coupling is high. use private or abstraction to reduce the visible methods of a class object.
- In remote if we have large number of buttons, it was difficult to use it. if we have required buttons at limited, then it will be easy to use.

----xxxx-----xxx-----xxx

Reducing Coupling : 
- Consider we are in a browser. also consider browser is a class. In browser user going to type the website url, the url identify the dns ip address and render the html.
- Here type the website url is requied to visible to use. but get the ip address for the website url and get the html is not required to user user. Here navigate methos should visible to user but findIpAddress and sendHttpRequest is not required to display to users. so  navigate() in public and , findIpAddress and sendHttpRequest() should be private
- Abstraction - Reducing the complexity by hiding the unnecessary details.
- Its easy to use and less coupling in the future.

oops is not about creating classes and methods. 

----xxxxx------xxxxxx-----

Constructor: 
- who ever implementing the employee class has to remember to call those methods in order. if something missed, it result will be wrong.
- Eg : in a remote control, press A and B before to change a channel. this will be complex and not acceptable.
- We want to make the interface of the class as simple as possible.
- A constructor is a special methos that is called when we create a new object. the job of the constructor is to initialize the fields.
- constructor dont have return type.
- public Employee()
  {
  }
 - It have same class name Employee with caps 1st letter.
 - constructor can have parameters.
 - 1 class can have multiple construcotr,
 - One constructor can call another using this():
 - id we dont create constructor manually, thr java compiler will automatically create one for us. called  as default constructor.
 - 
------xxxxx------xxx-----xxxx-------xx

Method over loading:
- same method name with different type and number of parameters.
- in java we cant set default values for the parameter. but in python and c# we have option.
  class Test {

    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }

}

------xxxx------xxxxx-------xxxxx-----

Constructor overloading : 

- techinically constructors also methods.

  public Employee (int baseSalary) {
    this(baseSalary, hourlyRate: 0)
}
public Employee(int baseSalary, int hourlyRate) {

setBaseSalary (baseSalary) ; setHourlyRate (hourlyRate) ;

｝

----xxxxxx--------xxxx------

Static members: 
- in oops a class can have 2 types of members, 1. instance members and 2. static members
- 



