
Heap memory allows us to create memory which is independent of the function lifecycle.

`new` operator is used to allocate memory in heap , new operator just returns the pointer to the data allocated in the heap, it doesn't do anything with the data.

### Functions of `New` Operator

- allocated the memory for the expected data structure
- initializes the data structure ( data structure can be a class , or other primitive value)
- returns the pointer to the allocated heap memory


### `Delete` operator

That allocated memory is released or reclaimed by the OS only after we pass that pointer to the `Delete` operator.

#### Creating a heap Allocated memory 

```cpp
int main (){
	int* num_ptr = new int;
}
```

	the above actually does creates two values the num value in heap and a pointer in the stack pointing to heap, as we havent initialized the value of it points to nothing

[c++/oop/attachments/Pasted image 20240110072431.png]

in the below program a square class is defined and it instantiated on heap and stack, objects living in stack its properties can be read directly using `.` operator but for the objects living in heap we have to deference the value first and then access its attributes and methods `(*obj).method()`.

but we also have an operator arrow operator `->` for this purpose making it easy to access heap allocated memory's pointers easily  `heapObj->method()`.
```

```c++

#include <iostream>
class Square {
    public :
        int length;
        int breadh;
        void setLength(int length){
            // `this` - is a pointer to the object on which the method is called
            this->length = length;
        }

};
int main(){
    // stack allocated
    Square square1;
    square1.setLength(20);
    
    // head allocated 
    Square* square2 = new Square;
    square2->setLength(10);
    std::cout << square2->length << std::endl;
    // as we have created the memory in heap we need to delete them
    delete square2;
    // its now a dangling pointer,pointing to the memory which it not part of this program anymore
    // so assign nullptr to it
    square2 = nullptr;
    return 0;
}

```

when we have to give a value to the pointed memory we can do that by dereferencing the pointer, and we should not leave the a pointer without assigning any value it creates a `dangling pointer` . dangling pointer may point to anything in the memory which causes unexpected behavior, security vulnerabilities and crash, so we should assign a `nullptr` whenever a pointer is pointing to nothing. 

	accessing a property from the a pointer pointing nullptr will cause segmentation fault (nullPointer expection).