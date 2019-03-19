
## Language Keywords
Reserved for Java language only
`for`, `while`, `if...else`, `class`, `enum`, `null`, `do`, etc

## Variables

**Declaration** 

`<Data Type> <variable name>;`

Where `<Data Type>` can be:
1. a primitive type such as `int`,`double`,`byte`, ets 
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