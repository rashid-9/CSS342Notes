# Reverse A Linked List

```
#include <stdexcept>
#include <iostreams>

template<typename T>
struct Node {
    int data;
    Node<T>* next;
    Node(T val): data(val), next(nullptr);
};

int main(){
  Node<T>* head = Node<T>(10);
  head->next = Node<T>(20);
  head->next->next = Node<T>(30);
  head->next->next->next = Node<T>(40);

  reverseLinkedList(head);

}

void reverseLinkedList(Node<T>* head){
    if(head == nullptr) {
      cout << "Linked List is empty";
      return;
    }
    if(head->next == nullptr){
     return;
    }
    Node<T>* prevNode = nullptr;
    Node<T>* nextNode = head;
    Node<T>* tempNode = head;
    while(nextNode != nullptr){
      nextNode = nextNode->next;
      tempNode->next = prevNode;
      prevNode = tempNode;
      tempNode = nextNode;
    }
    head = tempNode;
    delete temp;
    delete currentNode;
    delete prevNode;
}
