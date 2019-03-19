
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

## Methods
Methods are functions defined inside a class.

**Definition**
`<public/private> [static] <return Data Type/void> <method name>([Data Type param1, Data Type param2,...]){ .... }`


```Java
	// methods are always declared inside a class
	public class Pizza{

		//declare a siple void method
		public void Bake(){
			System.out.println("Baking your pizza...");
		}
	}

	//use Pizza class by creating an instance first
	Pizza myPizza = new Pizza();
	
	//use Bake method of the class instance
	myPizza.Bake();

```