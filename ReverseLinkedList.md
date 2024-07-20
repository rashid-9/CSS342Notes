# Reverse A Linked List

```
#include <stdexcept>
#include <iostream>

template<typename T>
struct Node {
    T data;
    Node<T>* next;
    Node(T val): data(val), next(nullptr){}
};

int main(){
  Node<T>* head = new Node<T>(10);
  head->next = Node<T>(20);
  head->next->next = Node<T>(30);
  head->next->next->next = Node<T>(40);

  reverseLinkedList(head);

}

template<typename T>
void reverseLinkedList(Node<T>*& head){
    if(head == nullptr) {
      cout << "Linked List is empty";
      return;
    }

    Node<T>* prevNode = nullptr;
    Node<T>* nextNode = nullptr;
    Node<T>* currentNode = head;

    while(currentNode != nullptr){
      nextNode = currentNode->next;
      currentNode->next = prevNode;
      prevNode = currentNode;
      currentNode = nextNode;
    }
    head = prevNode;
}

'''
