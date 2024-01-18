whenever we create a class it needs a constructor , but when we don't provide a constructor then it uses a default constructor

### Default constructor

default constructors initialises default value for all instance variables when we instantiate a new object from that class .in most cases default value of primitive type is undefined 

### `Custom default constructor` 

This is different from primitive default constructor, primitive default constructor doesn't define any constructor in the class implementation, but Custom default constructor in one which we define with zero `0` arguments. The below is example of custom default constructor

```cpp
class Car{
	public :
		int speed;
		double petrol:
	// class constructor is function with name same of the class. 
		Car(){
			this->speed = 0;
			this->petrol = 50.5; // assume it to be litres  
		}
}
```
