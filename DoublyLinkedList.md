```

#include <iostream>
unsing namespace std;

template<typename T>
struct Node {
  T data;
  Node<T>* next;
  Node<T>* prev;
  
  Node(T val): data(val), next(nullptr), prev(nullptr){}
  }

template<typename T>
void insertAtBeg(Node<T>*& head, Node<T>*& tail, T val){
  Node<T>* newNode = new Node<T>(val);
  if(head==nullptr){
    head = tail = newNode;
  }
  else {
  newNode->next = head;
  head->prev = newNode;
  head = newNode;
  }
  }

void insertAtEnd(Node<T>*& head, Node<T>*& tail, T val){
  Node<T>* newNode = new Node<T>(val);
  if(head==nullptr){
    head = tail = newNode;
  }
  else{
    tail->next = newNode;
    newNode->prev = tail;
    tail = newNode;
  }
}

int findLength(Node<T>*& head){
  Node<T>* temp = head;
  int length = 0;
  while(temp!=nullptr){
    length++;
    temp = temp->next;
    }
  return length;
  }
  

void insertAtPos(Node<T>*& head, Node<T>*& tail, T val, int pos){
  Node<T>* newNode = new Node<T>(val);

  if(head==nullptr && pos ==0){
    head = tail = newNode;
    }
    else if((head == nullptr && pos != 0) || pos < 0){
      cout<< "Cannot place in position" << endl;
      return;
    }
  if(pos > findLength(head)){
    cout<<"Position exceeds length of linked list"<<endl;
    delete newNode;
  }
  
  else {
  int count = 0;
  Node<T>* current = head;
  while(count < pos - 1 ){
    current = current->next;
    count++;
    }

  newNode->next = current->next;
   if (current->next != nullptr) {
        current->next->prev = newNode;
    }
  newNode->prev = current;
  current->next = newNode;
  }
  if (newNode->next == nullptr) {
        tail = newNode;
    }
  }

void insertAfterPos(Node<T>*& head, Node<T>*& tail, T val, int pos){

  Node<T>* newNode = new Node<T>(val);

  if(head==nullptr && pos ==0){
    head = tail = newNode;
    }
    else if((head == nullptr && pos != 0) || pos < 0){
      cout<< "Cannot place in position" << endl;
      return;
    }
  if(pos > findLength(head)){
    cout<<"Position exceeds length of linked list"<<endl;
    delete newNode;
  }
  
  else {
  int count = 0;
  Node<T>* current = head;
  while(count < pos){
    current = current->next;
    count++;
    }
 
  newNode->next = current->next;
  if (current->next != nullptr) {
        current->next->prev = newNode;
    }
  newNode->prev = current;
  current->next = newNode;
  }
  if (newNode->next == nullptr) {
        tail = newNode;
    }
  }
  
```
    
    

