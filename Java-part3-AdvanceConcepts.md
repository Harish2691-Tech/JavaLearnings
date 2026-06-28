Java advanced concepts :

- All applications encounter error when they runs.
- In java these errors are represented as Exceptions.
- Exception objects, Different types of exception , Handling exceptions, Custom exception type, Chaining exceptions.

---xxx---xx-x-x-x-x-x
Exceptions : 

- Checked exception - java compiler checks them at compile time.
- unchecked - this is run time exception - (null pointer exception is the example)
  - NullPointerException
• ArithmeticException - value divide by 0
• IllegalArgumentException - the argument that we passes is not accepted is the exeption
• IndexOutOfBoundsException - If we try to access an element in an array or a string or a list using an invalid index.(we have 5 element in array and tryto access 10th element)
• IllegalStateException - we try to call a mthod but the underlying object not in the right state

- Error exception --> stack overflow error or out ofmemory error...when there is a problem in jvm...java virtual machine.

---x-x-x-x-x-x-x-x-x-x-x-x-x

Exceptions heierarchy : 


THROWABLE CLASS -> (Parent, top most class). It has below 2 classes.
  1. EXCEPTION CLASS (CHECKED)                        2. ERROR CLASS -> It represents error that are external to our application (out of memory error)
     a.RUN TIME EXCEPTION (UNCHECKED)

  Every exception has a) error message    and    b) stack trace. 


------xxx-x-x--x-x-x-x-x

Catching exceptions : 
try {
var reader = new FileReader (fileName: "file.txt");
System.out-println("File opened"');|
} catch (FileNotFoundException ex) {
System.out-println(ex.getMessage());
｝

in the ex object we have the exception information.

---xxx-x-x-x-x-x-x-x-x---

Catching multiple types of exception : 

try {
var reader = new FileReader (fileName: "file.txt");
System.out.println("File opened"');
var value = reader.readData();
}

catch (FileNotFoundException ex) {
System.out.println(ex.getMessage());
｝
catch (IOException e){
System.out.println("Could not read data");
}

- multiple catch block
- Each catch block target a specific type of exception
- IOException is parent for FileNotFoundException.

- Using vertical bar(|) we can combine multiple exception class -> catch (IOException | Parsexception e)

-x-x-x-x-x-x-x-x-x-x-x-x-x-x-

Finally block : 
- write after the catch block
- finally{
    reader.close();
  }
---------x-x-x-x-x-x-x-x-x-x-x

try with resources statement : 
- Inside try we can write code inside () block. we can write multiple line statements.
- FileReader will use the interface to close it. dont need to explicitelt implement it.
- 

public static void show() {
try ( var
reader = new FileReader (fileName: "file.txt");
var
writer = new FileWriter (fileName: "
...
｝
var value = reader. read ();
catch (IOException e) {
System. out-println "Could not read data.");
｝
}

---x-x-x-x-x-x-x-x
throw exceptions : 
- try... catch ...
public class Account{
  public void deposit(float value){
    if(value <=0){
      throe new IllegalArgumentException();
    }
  }
}

--- the above one is called defensive programming. It avoids the serious problem doen the road. 
- returnType methodName() throws ExceptionType
- void deposit() throws IOException {
  if(value<=0)
  throw new IOException();
  }

 - We are telling this methods it may throw IOException.
 - It is API or Interface of this method. 

--------x-x-x-x-x-x-x-x

Rethrowing exceptions : 
- In the catch section we mention throw ex, this means we re-throwing the exception and inform the caller that an exception happened.
- Without throw e, the exception would stop in the catch block and the caller would never know that an error occurred.
- catch(IOException e){
  system.out.println("Logging");
  throw e;  // this line tells the caller that an exception occured. Caller receives IOException
  }
- in the Caller method in catch we can have IOException or Exception or Throwable class. Throwable is parent of all exception classes.
- 
---x-x-x-x-x-x-x-x-x-x-x-x-x-x
Custom exceptions :
- To write custom exception we can inherit or extends Exception or RunTimeException
- Exception -check exception / compile time exception
- RunTimeException - unchecked

- public class InsufficientFundException extends Exception {
   public InsufficientFundException(){
    super("insufficient funds")
    }
   public InsufficientFundException(string message){
    super(message)
    }
  }
-----

  catch(InsufficientFundException e){
  System.out.println(e.getMessage());
  }
------x-x-x-x-x-x-x-x-x-x-x-x-x-
Chaining Exceptions : 
- Wraping an exception inside a general xception.
------
  Real-World Layer Example
  Controller Layer
      |
Service Layer
      |
Repository Layer
      |
Database

Database fails: :
SQLException

Repository catches and wraps::
throw new RepositoryException("DB Error", e);

Service catches and wraps again:
throw new ServiceException("Account Creation Failed", e);

Result:
ServiceException
    Caused by RepositoryException
        Caused by SQLException

------
Summary

Exception chaining = one exception contains another exception as its cause.
----
Common pattern:
catch (Exception e) {
    throw new CustomException(
        "Meaningful message",
        e
    );
}

-----
Benefits:

Preserves the original error.
Adds business-specific context.
Makes debugging much easier.
Produces a complete "Caused by" stack trace.

---x-x-x-x-x-x-x-x-x-x-x-x-xxxxxxx----xxxxxx----
xxxxxxx----xxxxxx-----xxxxx------xxxxx---------

Generics : 
- Manu of the collection classes are implemented using Generics. 
- we can use object type as generic functions. but if u provide int or bool we have to explecitly cast it to convert. if 2nd avlue is some other type we get casscastexception error. To avoid this we use generics.
- **Every primitive type in jave have a wrapper class.**

- We cant use primitive types in generics, to overcome this we can use wrapper class of the primitive type.
- int -- Integer
- float -- Float class
- boolean -- Boolean class

  --x-x-x-x-x-x-x-x-x-x-x-x-x-x-x-x

  Generics and primitve types : 

- Example :
   GenericList<Integer> numbers = new GenericList<Integer>();
  or
   GenericList<Integer> numbers = new GenericList<>();

    numbers.add(1);
  - java compiler is going to put this primitive value inside a box is called as Boxing
 
  - int number  = numbers.get(0); // unboxing
   Java compiler is going to extract the value from Integer object.
    
  -x-x-x-x-x-x-x-x-x-x--x-x-x-x-x-x-x-x-x--x-x
Generic Classes :

   public class GenericList<T>{
    private T[] items = (T[]) new Object[10];
    private int count;

    public void add(T item){
      items[count++] = item;
    }

  public T get(int index){
    return items[index];
  }
  
  }

  Main class :

  var list = new GenericList<Integer>();
  list.add(1); // here we can add string. this is the benifiut of Generics.


----

If we need to use User object
 var list = new GenericList<User>();
  list.add(new User());

  User user = list.get(0);

-- we dont need explict cast here.
-- we get compile time type safety here.

  

  to create object :
  -  new GenericList<User>(); // here T is User
  -  new GenericList<String>(); // here T is String
 
  -  For array declaration we need type.
  -  private T[] items = (T[]) new Object[10];
  -  

   - Just like a method can have parameter, a class also can have parameter-> T . --> T -> the type of objects we can store in that list
   - 

  xxxx-x-x-x-x--x-x-x-x-x--x-x-x
constraints :
- need to study deeply

- xxx-x-x-x-x-x--x-x--x-x--x-x

Type Erasure:
- after compile the java code will convert into bute code. this is platform independent. bcoz, byte code can run in any platfor like windows, mac and linux
- the generic code to byte code-> if we use constraint, it converts to particular constraint type  or else it will be object array.

- Type Erasure is the process by which Java removes generic type information during compilation.

-------
Bounded Generics
Source Code

class Box<T extends Number> {
    T value;
}

After Erasure
class Box {
    Number value;
}

When a bound exists, Java replaces T with the bound.
----

Limitation 1: Cannot Create Generic Arrays
T[] arr = new T[10];
Because at runtime Java doesn't know what T is.

Limitation 2: Cannot Use instanceof with Generic Types
if(list instanceof List<String>) {
}
Because runtime doesn't know about String.

----x-x-x--x-x-x--x-x
Comparable Interface : 
- Comparable interface is used to compare the objects.
- Comparable is a generic interface.because here we have <T> parameter
- this interface as a single method -> int compareTo(T o) -> Compares this object to a specific object.

- For our class if we want to use this interface, we have to implement it with type. -> Comparable<T> --> eg : Comparable<User>
- If we pass with out type i mean -->  Class User implements Comparable {}
- it render the --> int compareTo (object o)  { return 0};
- It will comaprethe Object class.
- Problem with Object class is -> we have to done explicet cating here. Also it is possible to get Cating exception at run time.
- Thats why we have to specify the generic type argument. Comparable<User> { }

---x-x-x-x-x-x-x-x-x-

Generic Methods: 

- We can create Generic methods inside Generic class and also normal classes.
- Normal class :

    public class Utils {
    
    public static  int max(int first, int second) {
      return (first > second ? first : second);
    }
    
    }
  this is normal method... below is the generic method

 public class Utils {
    
    public static <T> T max(T first, T second) {
      return (first > second ? first : second);
    }
    
    }

  - in this approach, it will show one error as cant apply <,> compare operator in generic.
  - to resolve this , we need to use Comparable interface
  - <T extends Comparable<T>>
  
 public class Utils {
    
    public static <T Comparable<T>> T max(T first, T second) {
      return (first.compareTo(second) <0 ) ? second : first ; 
    }
    
    }

    Utils.max(10,20);
- Once we enter the 10, at the moment, it knows the T is Integer. for the 2nd parameter too.
- instead of using Object parameter , if we use T generics, at run time ensure to avoid error.     

--x-x-x-x--x-x-x-x-x

Multiple Type Parameter : 
- consider we can have multiple parameters in a method. Each paramter may have different type. one in int and one in string and one is boolean.
- we can use K and V  for different type parameter. or whatever name we can use.

- public static <K,V> void print(K key, V value){
    Sysytem.out.println(key +" " + value);
  }

Main class: 

Utils.print(10,20);

Utils.print(10,"success");

 - in this example K can have differnt type and V can have different type. It may have Class as a type also .
------
Multiple Type parameters in Java : 
- In

- public class KeyValuePairs <K,V> {
    private K key;
    private V value;

    public KeyValuePairs(K key, V value) {
      this.key = key;
      this.value = value;
    }
  
  }


-------

Generic classes and inheritance :

-----

Wildcards :

- with wildcards, we can cast generic types.
-------

-x-x-x-x-x--x-x-x-x-x--x-x-x-x-x-x--x-x-x-x-x-x--x-x-x-x-x-x-x-x-x-x-x-x--x-x-x-x

Collections :

- Collection farmeworks
- parent of collection framework is Iterable interface.
- Iterable -> Collection
                  |
  ----------------------------
  |            |             |
  List        Queue          Set
  |              |            |
ArrayList  Priority Queue    HashSet
  |
LinkedList


Collections :
- Collection is an interface. ArrayList is a class that implement the Collections interface.
- In collections we dont care about the indexes of object. we just care about adding or removing them from a collection.

- code :
   Collection<String> collection =  new rrayList<>();
   Collections.addAll(collection, "a","b","c",);
   collection.size(); // it shows the length of the collection
   collection.isEmpty(); // it provides boolean value true / false;
   collection.remove("a") // this a item will be removed from collection object.

   collection.clear() // remove all items from the object. it displays [] array;
   collection.contains("a"); // it checks the collection whether it have a or not provide true / false ;

To check two different collection objects : 
- (colObject1.equals(colObject2))

---x-x-x-x-x-x-x-x-x-x-x--x-x-x--x

List : 
- List interface
- java.util.List
- java.util.ArrayList
- It represents a order collection also called sequence.
- With list we can access object by index.

- Iterable
     |
 Collections
     |
    List

-  In collections we dont care about the indexes of object. we just care about adding or removing them from a collection.
-  But in List we should care about index of bjects and a collection. we should use the list interface.

-  CODE :
   List<String> list = new ArrayList<>();
   list.add("a"); // add singke element.
   list.add(0,"a+"); // add elementr in the mentioned index.

   // to add multiple elements
   List<String> list = new ArrayList<>();
   Collections.addAll(list,"a","b","c");

   // To get the 1st element to display
   System.out.println(list.get(0));

   // replace an object in the given index
   list.set(0,"a+");

   // remove an in dex of element
   list.remove(0);

   // index of the element
   list.indexOf("a");

   // last index of an element
   list.lastIndexOf("a") // if a multiple times present, it gives the last index of a

   // sublist
   // fromIndex → Inclusive (included)
   // toIndex → Exclusive (not included)
   list.subList(0,2) // 0 -> start index and 2 is last index

  -x-x-x-x-x-x-x-x-x-x-x-x--x-x-x-x-x

   Comparable interface : 
   - For a user defined class, to use Collections.sort(customes) functionality, we have to implement Comparable interface on that class.

   - we have to override the compareTo method

      Public int compareTo( Customer other){
      return name.compareTo(other.name);
     }

    - still we wont get the proper output, it will give the object refernce in the heap. default representation of a customer object as a string
    -- To get proper output, use 

    Public String  toString(){
    return name
    }

   
Yes. When an object is passed to System.out.println(), Java invokes that object's toString() method. If the class does not override toString(), the default implementation from Object is used, which prints ClassName@hashcode


-x-x-x-x-x-x-x-x-x--x-x-x-x--x-x-x-x-x

Comparator interface :
- 

class EmailComparator implements Comparator<Customer> {

    @Override
    public int compare(Customer c1, Customer c2) {
        return c1.email.compareTo(c2.email);
    }
}


Think of it like:

Collections.sort(customers, sortingRule);

Why use Comparator when Customer already implements Comparable?

Because you may need multiple sorting strategies.
Customer
├── sort by name
├── sort by email
├── sort by age
└── sort by salary

Comparable gives one default ordering.

Comparator gives multiple custom orderings.


 ---------x-x-x-x-x-x-x-x-x-x--x-x-x-x-x-x-x

 The Queue interface : 
 - 
 
  
  
  

  





  
  


   




  
