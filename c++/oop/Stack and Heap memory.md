 Every variable in c++ has four things.
 + type
 + name 
 + value 
 + and a location in memory (memory address)


```cpp
// some where in the ram , this num variable is allocated
int num = 7;

// to get its address we use the `&` opertaor 
std::cout << &num << std::endl; 
// this prints  hexadecimal value of the memory address where the `num` lives
```


### Stack : 

stack memory is the default memory space every variable is placed.

a stack frame is created for every function call , any variable declared within the function lives as long as the function is executed .

a stack allocated memory's lifecyle is associated to its function, when a function ends then variable within them is realeased.

stack memory always starts from the high address and grows down to the lowe address
`0xffff00f0` -> `0xffff00a8` ,


### Pointer :

pointer is a variable that stores the memory address of a data, the pointer to that data 

pointer doesn't directly store the value . it just points the data.

in c++ a pointer is defined with `*`  operator 

```cpp
int num = 10;
// getting the pointer of the var num 
int* num_pointer = &num;
```

To store a pointer we define the variable with the pointer type of the value `int*` then we get the memory address of num using `&` .

#### Dereference operator :

to get the value of the pointer pointing to we use the same `*` operator.

while defining a varaible we use the `*` operator along with a primitive type to denote its type,

when reading the pointer
```
int num = 10;
int* num_poniter = &num;

	// we use the same * operator here, to deference the value of num_pointer
std::cout << *num_pointer << std::endl 
```

so when a * is prepended to a variable ,c++ considers it to be a dereferencing ,

	never return a value of a stack allocated memory , when a function ends all the values inseide the function is released so that memory, can't be used anymore. so it would lead into an unexpected behaviour.
```cpp

int* add(int num1,int num2){
	int total = num1+ num2;
	// returing a reference to a stack value
	return &total;
}

int main (){
	int* total = add(2,4);
}
```

[Heap](/c++/oop/Heap)