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
- w/o creatimg objects we can directly use it with classname
- if the value is independent of object means then we can inroduce static fields.Also we can share it accross all all obejcts.
- Main method in the application is static. This is enable the java run time to directly call it w/o creating objects. so thats why the main methods is always be declared with static.
- Inside a class we have have static and normal fields and functions. IF we want to call the normal function inside a static function, we need to create object for class to call normal function inside a static function
- static methods can only see static fields of the class.
- If static methods want to access non static fields, 

Example : 
  class Car {
    String model = "BMW"; // instance field

    static void showModel() {
        System.out.println(model); // ❌ Compilation Error
    }

}

Reason :
The compiler complains because model belongs to an object, but showModel() is running without any object.

------

Solution 1: Create an Object

class Car {
    String model = "BMW";

    static void showModel() {
        Car car = new Car();
        System.out.println(car.model);
    }
}

Here, the static method creates an instance and accesses the field through that instance.

-----

Solution 2: Pass an Object as a Parameter

This is usually the better approach.

class Car {
    String model = "BMW";

    static void showModel(Car car) {
        System.out.println(car.model);
    }
}

public class Main {
    public static void main(String[] args) {
        Car car = new Car();
        Car.showModel(car);
    }
}

---------

Default access modifier :

In Java, if you don't specify an access modifier, the default is package-private (sometimes called default access).

/* package-private */ class Car {
    /* package-private */ String model;

    /* package-private */ static void showModel() {
        System.out.println(model);
    }
}

-------
xxxxx-----xxxxx-------xxxxx--------

Moving away from static fields : 

- we use constructor to initialize instance fields 
- use a class instance inside another class.
  - in class 2 we initialize class1. uisng class2 constructor with parameter we can initialize class1.
    public class Class2{

    private Class1 class1;

    public Class2(Class1 class1){
    this.class1 = class1;
    }
    }

------xxxx-----xxxxx---------xxxx-----------

Moving static fields : 

Instead of using the the static fields in main class and pass it as parameter to another class object. move it to the actual class and use it.

----xxxxxx----xxxx----xxxx

Extracting duplicate logic : 

- Instead of writing the same logic repeatedly inside different fuctions... move that logic into a private method and call the method to other methods. This avoids duplidate logics.

- for(double balance : calculator.getRemainingBalances())
    System.out.println(NumberFormat.getCurrencyInstances().format(balance));

  This line means for(double balance : double[]) - from the array get one by one data and execute it.

-----xxxxxx-----xxxx-----xxxxx-----

Inheritance : 
ClassB extends ClassA

ClassB have the fwatures of ClassA. 

- By default all the classes are extends from thr Object class in Java. But this is not explicitly done. it done by internally.

---xxxxx-----xxxx------

Object Class :
- By default all the classes are extends from thr Object class in Java compiler. But this is not explicitly done. it done by internally.

- var obj = new Object();  // its available in java.lang package. so its available in everywhere
- Java compiler automatically extends this Object class to all Classes.
- It have getClass , equals, hashcode members
- getclass returns Class object.  With this we can read metadata of an object. We can define all the fields and methods combined in that object.
- equals - we can use it t comparing objects.
- hashcode - returns an integer based on the address of the object in memory.
- toString() - retuns the string representation on that object.
- few others methods -> notify, notifyAll and wait that are used in concurrenchy.

- obj.hashcode() -> 1258902577 --> lot of poeple thins this is the address of the object in memory. But its not. The address of the object goes to a special fucntion claled Hash function. and the job of this fuction is to get a value and map it to a numeric value. The one of the usageis comparing objects in a quality.
- toString() - returns the string representation of an object. it have 2 parts. one is fully qualified name of the class.(it cona=tains the package is orifinally from) and another is hashcode (represented as hexadecimal-> hexadecimal with both numbers and a-z)
- com.codewithmosh.TextBox@5b2133b1

-----xxxxxx------xxxxx------

constructors in inheritence : 
- consider we have parent and child class. If the parent class ahev constructor with parameter then in our child class constructor we have to pass the values with super fucntion inside the coinstructor.

- Class Child

- public Child(){
    super (true); // this should be very 1st stamenet in the child class constructor
- }

----xxxxx------xxxxxx-----

Access modifiers : 
- protected is like public and package. means inside the package we can access the class. but outside the package , we cant access.
- public - we can access it everywhere.
- private - access it only inside the class. not even access by inherited classes.
- default (package-private) - same class and same package we can access.

- best practice use public and private.

-----xxxxx-----xxxxxxp-------

Overriding Methods :
- sometimes we inherit some methos to child class. but we are not happy about the implementation. we want to change it. to implement this, we can use method override.
- We use Annotations. An annotations is basically a label that we attach to a class member. wuith this we get extra information to the java compiler. we are telling the java compiler that we are overridng the toString method in this class.
- @Override annotation in the class member
- For override the methodname and return type should be same. 

------xxxxxx-----xxxxxx-------xxxxxx

  Upcasting and Downcasting : 

  public static void main (Stringll args) {
var contral = new UIControl (isEnabled: true);
var textBox = new TextBox ();
show (textBox);
｝
public static void show(UIControl control) {
var textBox = (TextBox) control;
textBox. setText("Hello World' );
System.out println (control);
}

- UIControl is the parent class and TextBox is the child or sub class.
- in a method the paramter is parent class but we are passing child class object. this is called Upcasting.in compile time we can only access the parent class members. But in run time it act as child class object.
- var textBox = (TextBox) control; --> this is downcasting here we can access the child class members.
- If the created instance is parent class and we want to downcast to child class, we get classcast exception and program crashed. To avoild this  we can use control instanceof TextBox condition, it=f true we can access it orlse handle with condition
- 
------xxxxxxx------xxxxxx----

  Comparing Objects :

  public static void main (Stringll args) {
    var point1 = new Point (x: 1, y: 2) ;
    var point2 = new Point (x: 1, y: 2) ;
      System.out-println(point1 == point2);

｝

- the output is false. both objects are reference types. Values that are stored in that variables are address of the objects in memory.
- -----xxxx------xxxx------xxx----

  Polymorphism :

  - Excapsulation , Abstraction and Inheritence.
  - Polymorphism -- Many forms
  - in the base classe we have 1 method and we override this to child class and change the logic. 

-----xxx-------xxxx

Abstract classes and methods : 

- Abstract means - more common one not a specific one. UIControl is common one, textBox and RadioButton are specific one.
- We cant instatiate the Abstract class.
- We only can extends and create new class with them.
- For method also we can use abstract, but we only define the method.
- public abstract void render();
- xxxx----xxxx---xx

Final Classes and Methods : 

- When we define a class with Final, we cant extends it. i mean cant inherit it.
- If we define a method with Final. we cant override it.
-----xxxx-----xxxx-----

  Deep Inheritence :
  - Avoid deep inheritance. inheritance is good upto 2 levels. more than 3 leel is not good and risk is high to manage the code.
 
----xxxx----xxxx
Multiple Inheritance :
- Java doesnt support Multiple inheritance. Espically the Diamond problem.
  class A {
    void show() {
        System.out.println("A");
    }
}

class B extends A {
}

class C extends A {
}

class D extends B, C { // Imagine this were allowed
}

------
D d = new D();
d.show();

----
Which show() should Java use?

B's version?
C's version?
A's version?

This ambiguity is called the Diamond Problem.

      A
     / \
    B   C
     \ /
      D

  -------


  class Father {
    void advice() {
        System.out.println("Father");
    }
}

class Mother {
    void advice() {
        System.out.println("Mother");
    }
}

class Child extends Father, Mother { // Not allowed
}


Java avoids this confusion by disallowing multiple inheritance of classes.

**How Java Solves It: Interfaces**

**Java allows a class to implement multiple interfaces:**


------
---xxxxx-----xxxxxx-----xxxxx----

Dependency Injection : 
- 



