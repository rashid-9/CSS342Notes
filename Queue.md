# Queue

![Queue-Data-structure1](https://github.com/user-attachments/assets/c7a8bc57-693a-4e21-8161-0e3f6c2c9b2c)

There are 2 main implementation for the Queue is:

 - Array based Queue
 - Linked List Queue

<ins> Array based Queue </ins>

 - Fixed Size: This implementation uses a static array with a fixed size. It's simple and fast, but it has the limitation that the maximum size of the stack must be known in advance.
 - Dynamic Size: This uses a dynamic array, which can resize itself when it reaches capacity (like ArrayList in Java or std::vector in C++). This implementation is more flexible but can be slightly more complex due to the need to handle resizing.

 - ** FYI We will use a circular queue for this implementation **

   Operations we need for a queue:
    - Enqeue: Add an elements to the back of the queue
    - Deqeue: Remove an element from the front of the queue
    - Peek: See what is at the front of the queue
    - Display: Print out the contents of the queue

   ## Array Based Queue
  
  ```
#include <iostream>
#include <stdexcept>
using namespace std
template<typename T>

class Queue {
  // Here we are declaring the virtual operations for the queue
  virtual void enqueue(T val) = 0;
  virtual T dequeue() = 0;
  virtual T peek() = 0;
  virtual void diplay() = 0;
  virtual ~Queue() = default;
  
}

template<typename T>
class ArrayQueue : public Queue<T> {

private:
      T *data = nullptr;
      int front = -1;
      int end = -1;
      int size = 0;
      int numElements = 0;

public:
      explicit ArrayQueue(int size){
      data = new T[size];
      this->size = size;
}

~ArrayQueue(){
  delete[] data;
}

bool isFull(){
    if( rear == size - 1 ){
      return true;
    }
    return false;
}

bool isEmpty(){
  if(front == -1 && rear == -1 ){
     return true;
  }
  return false;
}
  
void enqueue(T val) override {
     if(isFull()){
       throw overflow_error("Queue is full");
    }
    else if (isEmpty()){
        front = 0;
    }
    end = (end + 1) % size;
    numElements++;
    data[rear] = val;
}

T dequeue() override {
  if (isEmpty()){
      throw underflow_error("Queue is empty");
}
T returnVal = data[front];
front = (front + 1) % size;
numElements--;
if (numElements == 0) {
 front = -1;
 end = -1;
}
return returnVal;
}

void display() override{
    for(int i = front; i < numElements; i++){
      cout << data[(front + i) % size] << " ";
    }
  cout << endl;
}

T peek() override {
  if(isEmpty()){
    cout << "Queue is empty" << endl;
  }
 }

}

```

## Linked List Queue


                                                                                                                                                                                                                                                          




    

