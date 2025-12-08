# C#

## **What is Collection in C#?**

Collections are nothing but a grouping of items into a single unit. Collection classes are specialized classes for data storage and retrieval. Collection classes serve various purposes, such as allocating memory dynamically to elements and accessing a list of items based on an index, etc. These classes provide support for stacks, queues, lists, and hash tables. Most collection classes implement the same interfaces.

These classes create collections of objects of the Object class, which is the base class for all data types in C#.

## **What are the Various Collection Classes?**

The following are the various commonly used classes.

|   | **Generic Collection** | **Non-Generic Collection** |
| --- | --- | --- |
| Data Type | Same datatypes | Object type data |
| Namespace | **System.Collection.Generic** | **System.Collection** |
| Access items by index | List | ArrayList |
| Store items as key/value pairs | Dictionary\<TKey, TValue> | HashTable |
| Use data Last-In-First-Out | Stack | Stack |
| Use items first-in-first-out | Queue | Queue |
| Access items sequentially | LinkedList | NA |
| A sorted collection of key/value | SortedList\<TKey, TValue> | SortedList |

![https://www.tutorialsteacher.com/Content/images/csharp/generic-collections.jpg](../../_resources/image3.jpg)

## What is List & ArrayList

| **List** | **ArrayList** |
| --- | --- |
| List is **strongly typed**. This means that an array can store only **specific types** of items\\elements. | ArrayList can store **any type** of items\\elements. |
| **No need to cast** elements of an array while retrieving. | Items of ArrayList **need to be cast** to appropriate data type while retrieving. |
| Both **resize automatically** as you add the elements. |   |
| Both can store multiple null and duplicate elements. |   |
| Both can be accessed using **indexer**, **for** **loop** or **foreach** statement. |   |

## What is the difference between Dictionary & Hashtable?

| **Dictionary\<TKey, TValue>** | **Hashtable** |
| --- | --- |
| In _Dictionary_, you **must specify the type** of key and value. | In _Hashtable_, there is **no need to specify the type** of the key and value. |
| The data **retrieval is faster** than Hashtable. | The data **retrieval is slower** than Dictionary due to boxing/unboxing. |
| Dictionary **throws an exception** if we try to find a key which does not exist. | Hashtable returns **null** if we try to find a key which does not exist. |
| It always **maintains the order** of stored values. | It **doesn’t maintain the order** of stored values. |
| Use **KeyValuePair** with foreach statement to iterate Dictionary. | Use **DictionaryEntry** with foreach statement to iterate Hashtable. |
| In both the **key must be unique** & **cannot be null.** |   |
| Both can be access using **indexer**, **for** loop or **foreach** statement. |   |

## What is SortedList?

1.  C# has a **generic** and **non-generic** SortedList.
2.  SortedList stores the key-value pairs in **ascending order** **of the key**.
3.  **Key must be unique** and **cannot be null** whereas value can be null or duplicate.
4.  Non-generic SortedList stores keys and values of any data types. So, values need to be cast to an appropriate data type.
5.  Key-value pairs can be cast to **DictionaryEntry**.
6.  Access individual value using the indexer. SortedList indexer accepts the key to return value associated with it.

## What is a Stack?

1.  It represents a **last-in, first-out** collection of objects.
2.  When you **add** an item in the list, it is called **pushing** the item and when you **remove** it, it is called **popping** the item.

```
Stack st = new Stack();
st.Push('A'); 
st.Push('M'); 
st.Push('G'); 
st.Push('W');

foreach (char c in st)
{
    Console.Write(c + " "); // Output is : W G M A
}

st.Pop(); 
st.Pop();

foreach (char c in st) 
{
    Console.Write(c + " "); // Output is : M A
} 
```

## What is Queue?

1.  It represents a **first-in, first out** collection of objects.
2.  When you **add** an item in the list, it is called **enqueue** and when you **remove** an item, it is called **deque**.

```
Queue q = new Queue();
q.Enqueue('A');
q.Enqueue('M');
q.Enqueue('G');
q.Enqueue('W');

foreach (char c in q)
{
    Console.Write(c + " "); // Output is : A M G W
} 

q.Enqueue('V');
q.Enqueue('H');

foreach (char c in q)
{
    Console.Write(c + " ");  // Output is : A M G W V H
} 

Console.WriteLine("Removing some values ");

char ch = (char) q.Dequeue();

Console.WriteLine("The removed value: {0}", ch); // Output is : A

ch = (char) q.Dequeue();

Console.WriteLine("The removed value: {0}", ch); // Output is : M
```

## What is BitArray ?

1.  It represents an array of the **binary representation** using the values 1 and 0.
2.  It is used when you need to store the bits but does not know the number of bits in advance. You can access items using an **integer index**, which starts from zero.

## What is Generic in C#?

Generics allow you to define the specification of the data type of programming elements in a class or a method until it is actually used in the program. In other words, generics allow you to write a class or method that can work with any data type.

*   It helps you to maximize **code reusability**, **type safety**, and **performance**.
*   You can create generic collection classes. The .NET Framework class library contains several new generic collection classes in the _**System.Collections.Generic**_ namespace.
*   You may use these generic collection classes instead of the collection classes in the _**System.Collections**_ namespace.
*   You can create your own generic interfaces, classes, methods, events, and delegates.
*   You may create generic classes **constrained** to enable access to methods on particular data types.
*   You may get information on the types used in a generic data type at run-time by means of reflection.

```
public class MyGenericArray<T>
{
    private T[] array;
    
    public MyGenericArray(int size)
    {
        array = new T[size + 1];
    }

    public T getItem(int index)
    {
        return array[index];
    }

    public void setItem(int index, T value)
    {
        array[index] = value;
    }
}

static void Main(string[] args) 
{

//declaring an int array
MyGenericArray<int> intArray = new MyGenericArray<int>(5);

//setting values
for (int i = 0; i < 5; i++)
{
    intArray.setItem(i, i*5);
}

//retrieving the values
for (int i = 0; i < 5; i++)
{
    Console.WriteLine(intArray.getItem(i));
}

//declaring a character array
MyGenericArray<char> charArray = new MyGenericArray<char>(5);

//setting values
for (int c = 0; c < 5; c++) 
{
    charArray.setItem(c, (char)(c+97));
}

//retrieving the values
for (int c = 0; c< 5; c++) 
{
    Console.Write(charArray.getItem(c) + " ");
}
```

## What is Delegate?

C# delegates are like **pointers to functions**. A delegate is a **reference type** variable that **holds the reference to a method**. The reference can be changed at runtime.

Delegates are specially used for **implementing events** and the **call-back methods**. All delegates are implicitly derived from the **System.Delegate** class.

**Multicasting of a Delegate -** Delegate objects can be composed using the "+" operator. A composed delegate calls the two delegates it was composed from. Only delegates of the same type can be composed. The "-" operator can be used to remove a component delegate from a composed delegate.

1.  **Func Delegate**

Func is a **generic delegate** included in the System namespace. It has **zero or more input** parameters and **one out** parameter. The last parameter is considered as an out parameter.

```
class Program
{
    static int Sum(int x, int y)
    {
        return x + y;
    }

    static void Main(string[] args)
    {
        Func (int, int, int) add = Sum;
        int result = add(10, 10);
        Console.WriteLine(result);
    }
}
```

**Func with an Anonymous Method**

You can assign an anonymous method to the Func delegate by using the delegate keyword.

```cs
Func getRandomNumber = delegate()
{
    Random rnd = new Random();
    return rnd.Next(1, 100);
};
```

**Points to Remember :**

1.  Func is built-in delegate type.
2.  Func delegate type must return a value.
3.  Func delegate type can have zero to 16 input parameters.
4.  Func delegate does not allow ref and out parameters.
5.  Func delegate type can be used with an anonymous method or lambda expression.
6.  **Action Delegate**

An Action type delegate is the same as Func delegate except that the Action delegate **doesn't return a value**. In other words, an Action delegate can be used with a method that has a void return type. Action delegate can have 1 to 16 input parameters.

```
static void ConsolePrint(int i)
{
    Console.WriteLine(i);
}

static void Main(string[] args)
{
    Action <int>printActionDel = ConsolePrint</int>
    printActionDel(10);
}
```

1.  **Predicate**

A predicate is also a delegate like [Func](https://www.tutorialsteacher.com/csharp/csharp-func-delegate) and [Action](https://www.tutorialsteacher.com/csharp/csharp-action-delegate) delegates. It represents a method that contains a set of criteria and checks whether the passed parameter meets those criteria or not. A predicate delegate method **must take one input** parameter and **return a Boolean value**.

```cs
static bool IsUpperCase(string str)
{
    return str.Equals(str.ToUpper());
}

static void Main(string[] args)
{
    Predicate isUpper = IsUpperCase;
    bool result = isUpper("hello world!!");
}
```

An anonymous method can also be assigned to a Predicate delegate type as shown below.

```cs
static void Main(string[] args)
{
    Predicate isUpper = delegate(string s) { return s.Equals(s.ToUpper());};
    bool result = isUpper("hello world!!");
}
```

## **What is Indexer?**

An **indexer** allows an object to be indexed such as an array. When you define an indexer for a class, this class behaves like a **virtual array**. You can then access the instance of this class using the array access operator (**\[ \]**).

**Overloaded Indexers -** Indexers can be overloaded. Indexers can also be declared with multiple parameters and each parameter may be a different type. It is not necessary that the indexes must be integers. C# allows indexes to be of other types, for example, a string.

```cs
class IndexedNames 
{
    private string[] namelist = new string[10];
    static public int size = 10;
    
    public string this[int index] 
    {
        get 
        {
            if(index >= 0 && index <= size-1 ) 
            {
                return namelist[index];
            } 
            else 
            {
                return "";
            }
        }
        set 
        {
            if(index >= 0 && index <= size-1 ) 
            {
                namelist[index] = value;
            }
        }
    }
    
    public int this[string name] 
    {
        get 
        {
            int index = 0;
            while(index < size) 
            {
                if (namelist[index] == name) 
                {
                    return index;
                }
                index++;
            }
            return index;
        }
}
```

**What is Anonymous Type?**

1.  As the name suggests, is a type that **doesn't have any name**.
2.  C# allows you to create an object with the _**new**_ **keyword** without defining its class.
3.  The [**implicitly typed variable - var**](https://www.tutorialsteacher.com/csharp/csharp-var-implicit-typed-local-variable) is used to hold the reference of anonymous types.

var myAnonymousType = new {

firstProperty = "First",

secondProperty = 2,

thirdProperty = true

};

1.  An anonymous type is a **temporary data type** that is inferred based on the data that you include in an object initializer.
2.  It is derived from the **System.Object** class. Also, it is a **sealed class** and all the properties are created as **read-only properties**.
3.  **Nested Anonymous Type -** An anonymous type can have another anonymous type as a property.
4.  An anonymous type will always be **local** to the method where it is defined. Usually, you **cannot pass** an anonymous type to another method as parameter; however, you can pass it to a method that accepts a parameter of **dynamic type**.
5.  We can use anonymous type in **custom LINQ query** output.

## What is the Anonymous Method?

Anonymous methods provide a technique to **pass a code block as a delegate parameter**. Anonymous methods are the **methods without a name**, just the body.

You **need** **not specify the return type** in an anonymous method; it is inferred from the return statement inside the method body.

```cs
delegate void NumberChanger(int n);
NumberChanger nc = delegate(int x)
{
    Console.WriteLine("Anonymous Method: {0}", x);
};
```

## What is the difference between out & ref?

| **Out** | **Ref** |
| --- | --- |
| The _out_ keyword **causes** arguments to be passed by reference. | The _ref_ keyword **indicates** a value that is passed by reference |
| The _out_ arguments **do not** have to be **initialized** before being passed | The _ref_ parameter **must be initialized** before it is passed |
| It is **necessary** **to initialize** the value of a parameter **before returning** to the calling method. | It is **not necessary to initialize** the value of a parameter **before returning** to the calling method. |
| When _out_ keyword is used the data only passed in **unidirectional**. | When _ref_ keyword is used the data may pass in **bi-directional**. |
| The declaring of parameter through o\_ut\_ parameter is useful when a method **returns multiple values**. | The passing of value through _ref_ parameter is useful when the called method also need to **change the value** of passed parameter. |

## What is the difference between var & dynamic?

| **var** | **dynamic** |
| --- | --- |
| var type variables are **statically** typed. | dynamic type variables are **dynamically** typed. |
| In var type whatever **type** is decided at the time initialization **cannot be change** | dynamic can adopt **any type** even user define datatype also |
| The **data type** of the variable is decided **at compile time**. | The **data type** of the variable is decided **at run time**. |
| var type variables **should be initialized** at the time of **declaration**. So that the compiler will decide the type of the variable according to the value it initialized. | dynamic type variables **need not** be **initialized** at the time of declaration. Because the compiler does not know the type of the variable at compile time. |
| If the variable does **not initialize**, it will **throw an error**. | If the variable does not initialize, it will **not** **throw an error**. |
| It **cannot be used for properties or returning values** from the function. It can only use as a local variable in function. | It can be used for properties or returning values from the function. |

**What is Encapsulation?**

In non-object oriented languages, data and behaviors are not tied together. That means any function in the program can modify the data.

In Encapsulation, we **bind** **the data and behaviors in one object**. Only defined behaviors in a class can modify the data. We **hide the state of an object** by using properties and methods. Clients of the object only see these behaviors and by only these behaviors clients can modify the data.

We also protect the data by using access specifiers. We put the private/protected keywords before data to protect it from the outside world.

**What is Abstraction?**

Abstraction is a **technique of taking something specific** and making it less specific.

In OOPS we achieve the abstraction by separating the implementation from interface. We take an implemented class and **took only those method signatures and properties which are required by the class client**. We put these method signatures and properties into an interface or abstract class.

**What is the difference between a struct and a class?**

Structs cannot be inherited. Structs are passed by value and not by reference. Structs are stored on the stack, not the heap. The result is better performance with Structs.

**What is a singleton?**

A singleton is a design pattern used when only one instance of an object is created and shared; that is, it only allows one instance of itself to be created.

Any attempt to create another instance simply returns a reference to the first one.

Singleton classes are created by defining all class constructors as private.

In addition, a private static member is created as the same type of the class, along with a public static member that returns an instance of the class.

Here is a basic example:

```cs
public class SingletonExample
{
    private static SingletonExample _Instance;
    private SingletonExample () { }
    public static SingletonExample GetInstance()
    {
        if (_Instance == null) 
        {
            _Instance = new SingletonExample ();
        }
        return _Instance;
    }
}
```

There are numerous ways to implement Singleton in C#:

*   Standard Singleton Implementation
*   Early Instance Creation
*   Double Checked Locking
*   Using Generics
*   Fully Lazy Instantiation
*   Using Lazy type

**Describe the Async method of C#?**

Async (asynchronous programming) can be described as a method that returns to the calling method before finishing its work fully. It then proceeds to complete its work while the calling method goes along with its execution.

**Is it possible to serialize HashTable?**

It is not possible to serialize HashTable – a collection of key-value pairs – as the .NET Framework prevents serialization of any object that implements the IDictionary interface. The XmlSerializer class will display an error when an attempt is made to serialize a Hashtable.

# Abstract

**When to use Abstract Class?**

When we have a requirement where our base class should provide the default implementation of certain methods whereas other methods should be open to being overridden by child classes use abstract classes.

**What is an Abstract Class?**

A class that is declared by using the keyword abstract is called an abstract class. An abstract class is a partially implemented class used for developing some of the operations which are common for all next level subclasses. So it contains both abstract methods, concrete methods including variables, properties, and indexers.

It is always created as a superclass next to interface in object inheritance hierarchy for implementing common operations from the interface.

An abstract class may or may not have abstract methods. But if a class contains an abstract method then it must be declared as abstract. The abstract class cannot be instantiated directly. It’s compulsory to create/derive a new class from an abstract class in order to provide the functionality to its abstract functions.

**Can you create an instance of an abstract class?**

No, abstract classes are incomplete and we cannot create an instance of an abstract class.

**What is a Sealed Class?**

A sealed class is a class that cannot be inherited from. That means if we have a class called Customer that is marked as sealed. No other class can inherit from the Customer class.

**What is the abstract method?**

A method that does not have the body is called an abstract method. It is declared with the modifier abstract. It contains only the Declaration/signature and does not contain the implementation/ body of the method. An abstract function should be terminated with a semicolon. Overriding of an abstract function is compulsory.

**When to use the abstract method?**

Abstract methods are usually declared where two or more subclasses are expected to fulfill a similar role in different ways.

**Can a sealed class be used as a base class?**

No, the sealed class cannot be used as a base class. A compile-time error will be generated.

**Can an abstract class have a constructor? If so what is the use?**

Yes, an abstract class can have a constructor. In general, a class constructor is used to initialize fields. Along the same lines, an abstract class constructor is used to initialize fields of the abstract class. We would provide a constructor for an abstract class if we want to initialize certain fields of the abstract class before the instantiation of a child-class takes place. An abstract class constructor can also be used to execute code that is relevant for every child’s class. This prevents duplicate code.

**We cannot create an instance of an abstract class. So, what is the use of a constructor in an abstract class?**

Though we cannot create an instance of an abstract class, we can create instances of the classes that are derived from the abstract class. So, when an instance of a derived class is created, the parent abstract class constructor is automatically called.

**Note:** Abstract classes can’t be directly instantiated. The abstract class constructor gets executed through a derived class. So, it is a good practice to use a protected access modifier with the abstract class constructor. Using public doesn’t make sense.

**An abstract method in an abstract class does not have any implementation, so what is the use of calling it from the abstract class constructor?**

If we want the abstract method to be invoked automatically whenever an instance of the class that is derived from the abstract class is created, then we would call it in the constructor of the abstract class.

**When should a class be declared as abstract?**

A class should be declared as abstract

1.  When If it has any abstract methods
2.  If it does not provide implementation to any of the abstract methods it inherited
3.  When it does not provide implementation to any of the methods of an interface

**When should a method be declared as sealed?**

If we don’t want to allow subclasses to override the superclass method and to ensure that all sub-classes use the same superclass method logic then that method should be declared as sealed.

The sealed method cannot be overridden in sub-classes violation leads to a Compile-time error.

**What is the difference between private and sealed method?**

The private method is not inherited whereas the sealed method is inherited but cannot be overridden. So the private method cannot be called from sub-classes whereas the sealed method can be called from sub-classes. The same private method can be defined in sub-class and it does not lead to Compile-time error.

**When should a class be declared as sealed?**

In the below situations we must define the class as sealed

1.  If we don’t want to override all the methods of our class in sub-classes.
2.  If we don’t want to extend our class functionality.

**Why should the method have an abstract keyword if it does not have the body?**

In a class, we are allowed only to define a class with the body. Since we are changing its default property (means removing its body) it must have the abstract keyword in its prototype.

**What are the characteristics of an abstract class?**

1.  The abstract class can contain both abstract methods and non-abstract (concrete) methods.
2.  It can contain both static and instance variables.
3.  The abstract class cannot be instantiated but its reference can be created.
4.  If any class contains abstract methods then it must be declared by using the keyword abstract.
5.  An abstract class can contain sealed methods.
6.  The abstract method or class cannot be declared as sealed.
7.  A subclass of an abstract class can only be instantiated if it implements all of the abstract methods of its superclass. Such classes are called concrete classes to differentiate them from abstract classes.

**Why can the abstract class not be instantiated?**

Because it is not fully implemented in the class as its abstract methods cannot be executed. If the compiler allows us to create the object for the abstract class, then we can invoke the abstract method using that object which cannot be executed by CLR at runtime. Hence to restrict calling abstract methods, the compiler does not allow us to instantiate an abstract class.

**Who will provide the implementation (body) for abstract methods?**

Sub-class developers provide the body for abstract methods according to their business requirements. Basically, in projects, abstract methods (method prototype) are defined by the superclass developer and they are implemented by sub-class developers.

**What type of members can we define in an abstract class?**

We can define all static and non-static members including properties, fields, indexes and also abstract methods.

**Will abstract class members are created when a subclass object is created?**

Yes, its non-static members get memory when its concrete sub-class object is created.

**How can we execute static and non-static concrete members of the abstract class?**

Static members can be executed directly from its main method and its non-static members are executed by using its concrete sub-class object.

**Can we declare the abstract method as static?**

No, we are not allowed to declare the abstract method as static. It leads to CE: the illegal combination of modifier abstract and static. If the compiler allows us to declare it as static, it can be invoked directly which cannot be executed by CLR at runtime. Hence to restrict in calling abstract methods compiler does not allow us to declare the abstract method as static.

**Can we declare the concrete class as abstract?**

Yes, it is allowed. Defining a class as abstract is a way of preventing someone from instantiating a class that is supposed to be extended first. To ensure our class non-static members are only accessible via sub-class objects we should declare the concrete class as abstract.

**Explain the differences between overriding methods and abstract methods?**

The concept of the abstract method is similar to the concept of method overriding because in method overriding if a Parent class contains any virtual methods in it, then those methods can be reimplemented under the child class by using the override modifier.

In a similar way, if a parent class contains any abstract methods in it, those abstract methods must be implemented under the child class by using the same override modifier.

The main difference between method overriding and abstract method is in case of method overriding the child class reimplementing the method is optional but in case of the abstract method, the child class implementing the method is mandatory.

**What is the need for abstract classes in application development?**

The concepts of abstract methods and abstract classes are an extension to the inheritance wherein inheritance we have been discussing that with the help of a parent class we can provide property to the child class that can be consumed by the child classes which gives us reusability.

Along with the parent providing property to the children, the parent can also impose the restriction on the children with the help of abstract methods so that all the child classes have to full fill the restriction without failing.

# Polymorphism

**What is Polymorphism in C#?**

Polymorphism is one of the primary pillars of object-oriented programming. It allows us to invoke derived class methods through a base class reference variable during runtime.

In the base class, the method is declared as virtual and in the derived class, we override the same method. The virtual keyword indicates that the method can be overridden in any derived class.

The same function/ operator will show different behaviors when passed different types of values or the different number of values. So in the simple word we can say that behaving in different ways depending upon the input received is known as polymorphism i.e. whenever the input changes automatically the output or the behavior also changes.

**We can implement polymorphism in our application using three different approaches like**

*   Overloading
*   Overriding
*   Hiding

**Overloading again is of three types**

*   Method overloading
*   Operator overloading
*   Constructor overloading

**Explain the different types of Polymorphism in C#?**

There are two types of polymorphism

1.  Static polymorphism/Compile-time polymorphism /early binding
2.  Dynamic polymorphism/Run-time polymorphism /late binding

**What is compile-time Polymorphism in C#?**

In the case of compile-time polymorphism, the object of class recognizes which method to be executed for a particular method call at the time of program compilation and binds the method call with method definition.

This happens in case of **overloading** because in case of overloading each method will have a different signature and basing on the method call we can easily recognize the method which matches the method signature.

It is also called as static polymorphism or early binding. Static polymorphism is achieved by using function overloading and operator overloading

**What is Runtime Polymorphism in C#?**

In the case of runtime polymorphism for a given method call, we can recognize which method has to be executed exactly at runtime but not in compilation time because in case of overriding and hiding we have multiple methods with the same signature. So which method to be given preference and executed that is identified at runtime and binds the method call with its suitable method.

It is also called as dynamic polymorphism or late binding. Dynamic polymorphism is achieved by using function **overriding**.

**Explain different types of Overloading in C#?**

Again overloading is classified into three types, such as

1.  Method overloading / Function overloading
2.  Constructor overloading
3.  Operator overloading.

**What is function overloading?**

Function overloading and method overloading terms are used interchangeably. Method overloading allows a class to have multiple methods with the same name but with a different signature. So in C# functions can be overloaded based on the number, type (int, float, etc) and kind (Value, Ref or Out) of parameters.

The signature of a method consists of the name of the method and the type, kind (value, reference, or output) and the number of its formal parameters. The signature of a method does not include the return type and the params modifiers. So it is not possible to overload a method just based on the return type and params modifier.

A function overloading can be compared with person overloading. If a person has already some work to do and if we are assigning additional work to the person then the person will be overloaded.

In the same way, a function will have already some work to do and if we assign different work to the same function, then we say the function is overloaded. It is an approach of defining multiple methods with the same method name by changing the signature. Changing the signature means we can either change the no of parameters being passed to the method or type of parameters being passed to the method or order of parameters being passed to the function.

**When should we overload methods?**

To execute the same logic with different types of argument we should overload methods. For example to add two integers, two floats and two strings we should define three methods with the same name as shown in the below application

**What are the advantages of using overloading OR what are the disadvantages if we define methods with a different name?**

If we overload the method, the user of our application gets comfort feeling in using the method with the impression that he/she calling one method by passing different types of values.

The best example for us is the “WriteLine()” method. It is an overloaded method, not a single method of taking different types of values.

**When is a method considered as an overloaded method?**

If two methods have the same method name those methods are considered as overloaded methods.

Then the rule we should check is both methods must have different parameter types/list/order. But there is no rule on return type, non-accessibility modifier and accessibility modifier means overloading methods can have its own return type, non-accessibility modifier, and accessibility modifier because overloading methods are different methods

**Can we overload methods in the same class?**

Yes, it is possible no CE, no RE. Methods can be overloaded in the same or in super and subclasses because overloaded methods are different methods.

But we can’t override the method in the same class it leads to CE: “method is already defined” because overriding methods are the same methods with a different implementation.

**What is the execution control flow of overloaded methods?**

The compiler always checks for the called method definition in reference variable type class with the given argument type parameter. So in searching and executing a method definition, we must consider both reference variable type and argument type. Referenced variable type for deciding from which class method should be to bind. Argument type for deciding which overloaded method should be bind. For example:

**B b = new B();**  
**A a = new B();**  
**b.m1(50) => b.m1(int);** In this method call we should search m1() method definition in B class with integer parameter at the time of program compilation and bind that method definition.

**a.m1(50); => a.m1(int);** In this method call we should search m1() method defined in class A with int parameter not in class B even though the object is B.

**What is inheritance based overloading?**

A method that is defined in a class can be overloaded under its child class if we overload a method in this process we call it as inheritance-based overloading.

**What is the function/method overriding?**

Redefining the superclass non-static method in the subclass with the same prototype is called method overriding. The overriding method is always executed from the current objects class.

In object-oriented programming method overriding is a language feature that allows a subclass to provide a specific implementation of a method that is already provided by one of its superclasses.

The implementation of the subclass overrides (replaces) the implementation of superclass methods. So the overridden method is always executed from the object whose object is stored in the reference variable. The superclass method is called the overridden method and the sub-class method is called the overriding method.

**When must a method be overridden?**

If superclass method logic is not fulfilling sub-class business requirements, the subclass should override that method with required business logic. Usually, superclass methods are defined with generic logic which is common for all sub-classes.

**When is a sub-class method treated as an overriding method?**

If a method in sub-class contains the same signature as the superclass non-private method then the subclass method is treated as the overriding method and the superclass method is treated as the overridden method.

**How can we override a parent class method under child class?**

If we want to override a parent class method in its child class, first the method in the parent class must be declared as virtual by using the keyword **virtual** then only the child classes get the permission for overriding that method. Declaring the method as virtual is marking the method is overridable.

If the child class wants to override the parent class virtual method then the child class can do it with the help of the **override** modifier. But overriding the method under child class is not mandatory for the child classes. The Syntax is given below:

Class1:

Public virtual void show() //virtual function (overridable)

Class2: Class1

Public override void show() //overriding

Even if the method declared as virtual the child class may or may not override the method.

In overriding, the parent class defines a method as virtual and gives it to child class to consume that method. So the child class now consume the method as it is or override that method as per the requirement of the child class. So overriding parent class virtual method under a child class is only optional.

**How can we execute the superclass method if it is overridden in the sub-class?**

After re-implementing parent class methods under child class, the object of the child class calls its own methods but not its parent class method, whereas if we want to still consume or call the parent class’s methods from child class, it can be done in two different ways.

By creating a parent class object under the child class, we can call the parent class methods from the child class. Or by using the base keyword, we can call parent class methods from child class, but this and base keyword cannot be used under the static block.

**What is the difference between function overloading and function overriding?**

![Polymorphism Interview Questions and Answers in C#](../../_resources/image1.png)

**What is method hiding?**

Use the **new** keyword to hide a base class member. We will get a compile warning if we miss the new keyword. This is also used for re-implementing a parent class method under child Class.

Re-implementing parent class methods under child classes can be done using two different approaches, such as

1.  Method overriding
2.  Method hiding

In the first case, we re-implement the parent class methods under child classes with the permission of parent class because here in parent class the method is declared as virtual giving the permission to child classes for overriding the methods.

In the 2nd approach, we re-implement the method of parent class even if those methods are not declared as virtual that is without parent permission we are re-implementing the methods. The Syntax is given below.

Class1:

Public void display()

Class2 : Class1

Public new void display()

Using the new keyword for re-implementing the methods in the child class is optional and if used will give information to hiding.

**What is the difference between Method Overriding and Method Hiding?**

A parent class method can be redefined under its child class using two different approaches.

1.  Method Overriding.
2.  Method Hiding.

In Method overriding, the parent class gives permission for its child class to override the method by declaring it as **virtual**. Now the child class can override the method using the **Override** keyword as it got permission from the parent. The parent class methods can be redefined under child classes even if they were not declared as **Virtual** by using **‘new’** keyword.

In method overriding a base class reference variable pointing to a child class object will invoke the overridden method in the child class. In method hiding a base class reference variable pointing to a child class object will invoke the hidden method in the base class.

For hiding the base class method from the derived class simply declare the derived class method with the new keyword. Whereas in C#, for overriding the base class method in a derived class, we need to declare the base class method as virtual and the derived class method as the override.

If a method is simply hidden then the implementation to call is based on the compile-time type of the argument “this”. Whereas if a method is overridden then the implementation to be called is based on the run-time type of the argument “this”. New is reference-type specific, overriding is object-type specific.

**When can a derived class override a base class member?**

A derived class can override a base class member only if the base class member is declared as virtual or abstract.

**What is the difference between a virtual method and an abstract method?**

A virtual method must have a body whereas an abstract method should not have a body.

A Base class virtual method may or may not be overridden in the Derived class whereas a Base class Abstract method has to be implemented by the derived class.

**Can fields inside a class be virtual?**

No, Fields inside a class cannot be virtual. Only methods, properties, events and indexers can be virtual.

**Can you access a hidden base class method in the derived class?**

Yes, Hidden base class methods can be accessed from the derived class by casting the instance of the derived class to an instance of the base class as shown in the example below.

public class BaseClass

{

public virtual void Method()

{

Console.WriteLine("I am a base class method.");

}

}

public class DerivedClass : BaseClass

{

public new void Method()

{

Console.WriteLine("I am a child class method.");

}

public static void Main()

{

DerivedClass DC = new DerivedClass();

((BaseClass)DC).Method();

}

}

# Inheritance

**What are the 4 pillars of any object-oriented programming language?**

1.  Abstraction
2.  Inheritance
3.  Encapsulation
4.  Polymorphism

**Do structs support inheritance?**

No, structs do not support inheritance, but they can implement interfaces.

**What is the main advantage of using inheritance?**

Code reuse

**Is the following code legal?**

class ChildClass : ParentClassA, ParentClassB

{

}

No, a child class can have only one base class. We cannot specify 2 base classes at the same time. C# supports single class inheritance only. Therefore, we can specify only one base class to inherit from. However, it does allow multiple interface inheritance.

**Does C# support multiple class inheritance?**

No, C# supports single class inheritance only. However, classes can implement multiple interfaces at the same time.

**Why does C# not support multiple class inheritance?**

C# does not support multiple class inheritance because of the diamond problem that is associated, with multiple class inheritance. Let us understand the diamond problem of multiple class inheritance with an example.

![Inheritance and Interface Interview Questions in C# with Answers](../../_resources/image2.png)

As shown in the image above, I have 2 classes – Class B and Class C and Both of these classes are inherited from Class A. Now, we have another class i.e. Class D which is inherited from both Class B and Class C

So if a method in Class D calls a method defined in Class A and Class D has not overridden the invoked method. But both Class B and Class C have overridden the same method differently. Now, the ambiguity is, from which class does, Class D inherits the invoked method: Class B, or Class C?

In order not to have these problems, C# does not support multiple class inheritance.

**What is the difference between interfaces and abstract classes?**

There are several differences between an abstract class and an interface as listed below.

1.  Abstract classes can have implementations for some of its members, but the interface can’t have the implementation for any of its members.
2.  Interfaces cannot have fields whereas an abstract class can have fields.
3.  An interface can inherit from another interface only and cannot inherit from an abstract class whereas an abstract class can inherit from another abstract class or another interface.
4.  A class can inherit from multiple interfaces at the same time, whereas a class cannot inherit from multiple abstract classes at the same time.
5.  Abstract class members can have access modifiers whereas interface members cannot have access modifiers as they are by default public.

**When do you choose interface over an abstract class or vice versa?**

If we have an implementation that will be the same for all the derived classes, then it is better to go for an abstract class instead of an interface. So, when we have an interface, we can move our implementation to any class that implements the interface. Whereas, when we have an abstract class, we can share implementation for all derived classes in one central place, and avoid code duplication in derived classes.

**What are the advantages of using interfaces?**

Interfaces are very powerful. If properly used, **interfaces provide all the advantages** as listed below.

1.  Interfaces allow us to implement polymorphic behavior. Of course, abstract classes can also be used to implement polymorphic behavior.
2.  The Interfaces allow us to develop very loosely coupled systems.
3.  Interfaces enable mocking for better unit testing.
4.  The Interfaces enable us to implement multiple inheritances in C#.
5.  Interfaces are great for implementing Inversion of Control or Dependency Injection.
6.  The Interfaces enable parallel application development.

**Can an Interface contain fields?**

No, an Interface cannot contain fields

**What is the difference between class inheritance and interface inheritance?**

Classes and structs can inherit from interfaces just like how classes can inherit a base class or struct. However, there are 2 differences.

A class or a struct can inherit from more than one interface at the same time whereas a class or a struct cannot inherit from more than one class at the same time

When a class or struct inherits an interface, it inherits only the method names and signatures, because the interface itself contains no implementations.

**Can an interface inherit from another interface?**

Yes, an interface can inherit from another interface. It is possible for a class to inherit an interface multiple times, through base classes or interfaces it inherits. In this case, the class can only implement the interface one time, if it is declared as part of the new class. If the inherited interface is not declared as part of the new class, its implementation is provided by the base class that declared it. It is possible for a base class to implement interface members using virtual members; in that case, the class inheriting the interface can change the interface behavior by overriding the virtual members.

**Can you create an instance of an interface?**

No, we cannot create an instance of an interface.

**If a class inherits an interface, what are the 2 options available for that class?**

**Option1:** Provide Implementation for all the members, inherited from the interface.

**Option2:** If the class does not wish to provide Implementation for all the members inherited from the interface, then the class has to be marked as abstract.

**What do you mean by “Explicitly Implementing an Interface”? Give an example?**

If a class is implementing the inherited interface member by prefixing the name of the interface, then the class is “Explicitly Implementing an Interface member”. The disadvantage of Explicitly Implementing an Interface member is that the class object has to be typecasted to the interface type to invoke the interface member. An example is shown below.

namespace Interfaces

{

interface Car

{

void Drive();

}

class Demo : Car

{

// Explicit implementation of an interface member

void Car.Drive()

{

Console.WriteLine("Drive Car");

}

static void Main()

{

Demo DemoObject = new Demo();

[//DemoObject.Drive](//DemoObject.Drive)();

// Error: Cannot call explicitly implemented interface method

// using the class object.

// Type cast the demo object to interface type Car

((Car)DemoObject).Drive();

}

}

}

**When to use Interface?**

If your child classes should implement a certain group of methods/functionalities but each of the child classes is free to provide its own implementation then use interfaces.