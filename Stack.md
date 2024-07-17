# Stack

![stack_representation](https://github.com/user-attachments/assets/6cffe763-e1a8-460f-9e08-98b9b9ed90a5)

There are 2 main implementaitons of stack: 
 - Array based Stack
 - Linked List stack


<ins> Array Based Stack </ins>

An array based stack using an array to store fixed size elements of the stack, the size of the stack must be known in advance to use this implementation.

Operations: 

  - Push: Add an element to the top of the stack.
  - Pop: Remove an element from the top of the stack.
  - Peek/Top: View the top element of the stack without removing it.
  - isEmpty: Check if the stack is empty.
  - isFull: Check if the stack is full (in fixed-size array implementation).

## Array Based Stack

```

#include <iostream>
#include <stdexcept>
using namespace std;

template<typename T>
class ArrayStack{
  int top = -1;
  int size;
  T* stack;

  public:

  ArrayStack(int size) : size(size), top(-1){
    stack = new T[size];
    }
 
  bool isFull(){
    if(top == size - 1){
    return true;
    }
    return false;
  }

  bool isEmpty(){
   if(top == -1){
     return true;
     }
    return false;
  }
  
  void push(T val){
    if(isFull()){
      throw overflow_error("Stack is full");
      }
    else{
    top++;
    stack[top] = val;
    }
  }

  T pop(){
    if(isEmpty()){
     throw underflow_error("Stack is empty");
     }
    else{
    T returnVal = stack[top];
    top--;
    return returnVal;
      }
  }

  T peek() {
    if(isEmpty()){
      throw underflow_error("Stack is empty");
      }
    else {
      return stack[top];
      }
    }

    void display() {
      if(isEmpty()){
      throw underflow_error("Stack is empty");
      }
      else {
        int current = top;
        while (current >= 0) {
         cout << stack[current] << " ";
         current--;
         }
      }
    }

    ~ArrayStack(){
      delete[] stack;
    }
};

```
  
