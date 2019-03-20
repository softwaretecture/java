
## Language Keywords
Reserved for Java language only
`for`, `while`, `if...else`, `class`, `enum`, `null`, `do`, etc

## Variables

**Declaration** 

`<Data Type> <variable name>;`

Where `<Data Type>` can be:
1. a primitive type such as `int`,`double`,`byte`, etc 
2. a complex type such as a `class`, `enum`, `Array`, `ArrayList`, etc
	1. `String`, `Pizza`, `MyCar`, `ArrayList<>`, etc
	2. Enumerations `PizzaTopings`, `Color`, etc

**Value Assignment** 

Primitive types:
`<Data Type> <variable name> = <value>;`
```Java
	int count;
	double price = 1.5;
```

Classes:
`<Class Data Type> <variable name> = new <Class Data Type>();`

```Java
	//declare a class MyClass
	public class MyClass{
	}

	//use class by creating an instance
	MyClass myClass = new MyClass();
```

Enumerations:
`<Enum Data Type> <variable name> = <Enum Data Type>.<ENUM VALUE>;`

```Java
	//declare enum MyColors
	public enum MyColors{
		YELLOW,
		GREEN
	}

	//use MyColors
	MyColors myColors;
	System.out.println(myColors.GREEN);
```



## Class Methods
Methods are functions defined inside a class.

**Definition**
`<public/private> <return Data Type/void> <method name>([Data Type param1, Data Type param2,...]){ .... }`


```Java
	// methods are always declared inside a class
	public class Pizza{

		//declare a simple void method
		public void Bake(){
			System.out.println("Baking your pizza...");
		}
	}

	//use Pizza class by creating an instance first
	Pizza myPizza = new Pizza();
	
	//use Bake method of the class instance
	myPizza.Bake();
```

Methods with parameters:
```Java
	// methods are always declared inside a class
	public class Pizza{

		//declare a simple void method that bakes a pizza for a given number of minutes 
		public void Bake(int minutes){
			System.out.println("Baking your pizza for " + minutes);
		}
	}

	//use Pizza class by creating an instance first
	Pizza myPizza = new Pizza();
	
	//use Bake method of the class instance and provide a number of minutes to bake the pizza
	myPizza.Bake(15);
```


Methods with return values:
```Java

	// methods are always declared inside a class
	public class Pizza{

		//declare a simple method that bakes a pizza for a given number of minutes 
		//and returns number of minutes left to bake 
		public void Bake(int minutes){
			System.out.println("Baking your pizza for " + minutes);
			//returns number of minutes left to bake
			return (minutes - 1);
		}
	}

	//use Pizza class by creating an instance first
	Pizza myPizza = new Pizza();
	
	//use Bake method of the class instance and provide a number of minutes to bake the pizza
	System.out.println("Time left to bake " + myPizza.Bake(15));
```



## Static Methods
Static methods are declared inside a class however, do not belong to the instance of a class. There is only one copy of static method in memory.

**Definition**
`<public/private> static <return Data Type/void> <method name>([Data Type param1, Data Type param2,...]){ .... }`

To use a `static` method, you don't need to create an istance of the class where it is declared. Insread, you need to use the name of the class or Class Data Type.

```Java
	// static methods are always declared inside a class
	public class Pizza{

		//declare a simple static void method
		public static void Bake(){
			System.out.println("Baking your pizza...");
		}
	}

	//To use as static Bake method of the class
	Pizza.Bake();
```



## Class Constructors
Class constructors are special methods that are declared inside a class and get invoked automatically when your first create an instance of a class.
***NOTE: The code inside a constructor executes only once, when you first create a class instance. You cannot call a constructor after the instance has been created.***
Constructors are always named the same way as the class name. They cannot return anything or use void.

**Definition**

`<public/private> <Class Name>([Data Type param1, Data Type param2,...]){ .... }`

```Java

	//declare a new enum for pizza toppings
	public enum PizzToppings{
		MUSHROOM,
		OLIVE
	}


	// constructors are always declared inside a class
	public class Pizza{

		//declare a constructor that takes a type of pizza to create.
		//the type of pizza is defined by the enum above
		//NOTE: the PizzToppings is the data type used to define the parameter 'toppings' in the constructor
		public Pizza(PizzToppings toppings){
			System.out.println("Baking your " + toppings + " pizza...");
		}
	}

	//use Pizza class by creating an instance first
	//because it has a constructor that requires the toppings, must provide the toppings
	Pizza myPizza = new Pizza(PizzToppings.OLIVE);

```

## Method Overloading
Method overloading provides a way of creating methods with the same name but different input parameter Data Types.
You can create as many method overloads as needed (same method name), as long as they all have different parameter Data Types.

```Java
	// methods are always declared inside a class
	public class Pizza{

		//declare a void method that bakes a pizza
		public void Bake(){
			System.out.println("Baking your pizza.");
		}


		//declare a method overload that bakes a pizza for a given number of minutes 
		public void Bake(int minutes){
			System.out.println("Baking your pizza for " + minutes);
		}
	}

	//use Pizza class by creating an instance first
	Pizza myPizza = new Pizza();
	
	//use Bake method of the class instance
	myPizza.Bake();

	//use Bake overload method of the class instance and provide a number of minutes to bake the pizza
	myPizza.Bake(15);
```

## Constructor Overloading
Similar to method overloading, constructor overloading allows to create multiple constructors with the same name in the same class as long as the constructor arguments are of different Data Types.
 

```Java

	//declare a new enum for pizza toppings
	public enum PizzToppings{
		MUSHROOM,
		OLIVE
	}


	// constructors are always declared inside a class
	public class Pizza{

		//default constructor
		public Pizza(){
			System.out.println("Baking your pizza...");
		}

		//declare a constructor that takes a type of pizza to create.
		//the type of pizza is defined by the enum above
		//NOTE: the PizzToppings is the data type used to define the parameter 'toppings' in the constructor
		public Pizza(PizzToppings toppings){
			System.out.println("Baking your " + toppings + " pizza...");
		}

		//declare a constructor that takes a type of pizza to create
		//and the size of the pizza
		public Pizza(PizzToppings toppings, int size){
			System.out.println("Baking your " + size + " inches " + toppings + " pizza...");
		}
	}

	//use Pizza class by creating an instance first
	//use the default constructor
	Pizza myPizza1 = new Pizza();

	//use Pizza class by creating an instance first
	//because it has a constructor that requires the toppings, must provide the toppings
	Pizza myPizza2 = new Pizza(PizzToppings.OLIVE);

	//use Pizza class by creating an instance first
	//because it has a constructor that requires the toppings and size, 
	//must provide the toppings and the size
	Pizza myPizza3 = new Pizza(PizzToppings.MUSHROOM, 12);

```

## Calling Constructor from a Constructor
When multiple constructors are used in single class, you can call one constuctor from another to avoid repeting code in every constructor.

Not as clean way
```Java

	public class Pizza{
		PizzToppings toppings;
		int size;

		//set the pizza toppings when the constructor is called;
		public Pizza(PizzToppings _toppings){
			toppings = _toppings;
		}

		//set the pizza toppings and size when the constructor is called;
		public Pizza(PizzToppings _toppings, int _size){
			toppings = _toppings; //this line is repeated, not good
			size = _size;
		}
	}
```

as this calling a constructor from a constructor
```Java

	public class Pizza{
		PizzToppings toppings;
		int size;

		//set the pizza toppings when the constructor is called;
		public Pizza(PizzToppings _toppings){
			toppings = _toppings;
		}

		//set the pizza toppings and size when the constructor is called;
		public Pizza(PizzToppings _toppings, int _size){
			//call the first constructor to set the toppings
			this(_toppings);

			size = _size;
		}
	}
```


## Class variables

Similar to method variables that are declared inside a method and are only available within that method scope, classes can have variables as well. Class variables available within the entire class scope. The class variables must be declared outside of the class methods and use `private` or `public` keyword. It is the best practice to make all class variables `private`. 

`private <Data Type> <variable name> = <value>;`


```Java
	// methods are always declared inside a class
	public class Pizza{

		//class variables are declared inside the class
		private int pizzaSize;


		//declare a constructor that takes a the size of the pizza to bake
		public Pizza(int size){	
		
			//store the given size of pizza to the class variable
			pizzaSize = size;
		}

		//declare a void method that bakes a pizza
		public void Bake(){
			//use the pizza size stored in the class variable
			System.out.println("Baking your " + pizzaSize + " inch pizza.");
		}
	}

	//use Pizza class by creating an instance first by giving it the size
	Pizza myPizza = new Pizza(12);
	
	//use Bake method of the class instance
	myPizza.Bake();

```


## Internal Class References

Within a class, the instance of the class is referred to using the `this` keyword. That is why we refer to constructors within a class as `this(...)`. All non-static methods or class variables can be referred to using the `this.` notation as well.

```Java

	public class Pizza{
		PizzToppings toppings;
		int size;

		//set the pizza toppings when the constructor is called;
		public Pizza(PizzToppings _toppings){
			//use "this" qualifier
			this.toppings = _toppings;
		}

		//set the pizza toppings and size when the constructor is called;
		public Pizza(PizzToppings _toppings, int _size){
			//call the first constructor to set the toppings
			this(_toppings);

			//use "this" qualifier
			this.size = _size;
		}
	}
```  
Another example where we actually return the instance of the class from the class itself.

```Java

	public class Pizza{
		PizzToppings toppings;
		int size;

		//set the pizza toppings when the constructor is called;
		public Pizza(PizzToppings _toppings){
			//use "this" qualifier
			this.toppings = _toppings;
		}

		//set the pizza toppings and size when the constructor is called;
		public Pizza(PizzToppings _toppings, int _size){
			//call the first constructor to set the toppings
			this(_toppings);

			//use "this" qualifier
			this.size = _size;
		}

		//NOTE: returns the instance of this class
		public Pizza getPizzaInstance(){
			return this;
		}
	}
```  
It whould be used like this:

```Java
	//use Pizza class to create an instance
	Pizza myPizza = new Pizza(PizzToppings.OLIVE, 12);
	
	//get the instance of Pizza class that we just created
	//and save it in another variable
	Pizza myPizzaReference = myPizza.getPizzaInstance();

```


## ArrayList

ArrayLists are classes that allow you to store items of the Data Type that you designate.

For example, if you want to store a list of Pizza classes you would do the following:

```Java

	//create a Pizza class
	public class Pizza{
		PizzToppings toppings;
		int size;

		//set the pizza toppings when the constructor is called;
		public Pizza(PizzToppings _toppings){
			this.toppings = _toppings;
		}

		//set the pizza toppings and size when the constructor is called;
		public Pizza(PizzToppings _toppings, int _size){
			//call the first constructor to set the toppings
			this(_toppings);
			this.size = _size;
		}

		public PizzToppings getPizzaType(){
			return this.toppings;
		}
	}

	//in Main.java

	//use Pizza class to create an instance
	Pizza myPizza1 = new Pizza(PizzToppings.OLIVE, 12);
	Pizza myPizza2 = new Pizza(PizzToppings.MUSHROOM, 10);

	//create an instance of an array list
	ArrayList<Pizza> pizzas = new ArrayList<Pizza>();

	//add pizza instances to it
	pizzas.add(myPizza1);
	pizzas.add(myPizza2);

	
	//call method to print all pizzas in the list
	showBakingPizzas(pizzas)


	private static void showBakingPizzas( ArrayList<Pizza> pizzas){
		for(Pizza pizza : pizzas){
			System.out.println("Baking pizza " + pizza.getPizzaType());
		}
	}

```


## Inheritance
Inheritance allows one class to "assume" or "inherit" all of functionality of another class.
For example `class` Animal may have a method `eat()`. A `class` Dog has a method `bark()` and a `class` Bird has a method `fly()`.
Both birds and dogs can eat but only a dog can bark and only a bird can fly. To avoid repeating the code for method `eat()` in both Dog and Bird, we can use inheritance to include all of the functionality from the class Animal using a special `extends` keyword.

```Java

	//create a class Animal with method eat()
	public class Animal {
		
		public void eat(){
			System.out.println("Eating..");
		}
	}

	//create a class Dog with method bark() and inherit from the Animal class
	public class Dog extends Animal {
		
		public void bark(){
			System.out.println("Barking..");
		}
	}


	//create a class Bird with method fly() and inherit from the Animal class
	public class Bird extends Animal {
		
		public void fly(){
			System.out.println("Flying..");
		}
	}


	//in Main.java

	//create an instance of the Dog class
	Dog dog = new Dog();
	//use the method from the Dog class
	dog.bark();
	//use the method from the inherited class Animal
	dog.eat();


	//create an instance of the Bird class
	Bird bird = new Bird();
	//use the method from the Bird class
	bird.fly();
	//use the method from the inherited class Animal
	bird.eat();

```

## Interfaces

## Static Variables

## Abstract Classes

