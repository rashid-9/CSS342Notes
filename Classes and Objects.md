 # Classes and Objects

  **Classes are user-defined data types that serve as blueprints for objects.**
  
 <ins>Access specifier :</ins> Can be private, public or protected
 
 <ins> Data Members:</ins> Variables
 
 <ins>Member Functions:</ins> Methods to access data members

 ```
class Class_name {
   Access Specifier;
   Data members;
   Member functions(){
     //body
   }
};
```

### Access Modifiers

<ins>Private:</ins> Private members can only be accessed from within the class

<ins>Public:</ins> They can be accessed within as well as outside the class

<ins>Protected:</ins> They can be accessed within the class and outside the class with the help of friend function

 ### Object of a class

 An object can be defined as an instance of a class, no memory is allocated when a class is defined. When an object is created that is when memory is allocated

 Syntax: ``` Class_name  Object_name; ```

 Example: ``` Cat cat1; ```

 ### Member Functions

 Any function that is declared as part of a class is called a member function. Member function are invoked by sending messages to an Instance of the class.

 The dot (.) operator is used to access public member functions.

 Example: ``` obj.sum(); ```

 ### Constructors

 It is a special type of member function of a class that is called automatically whenever an object is created

 Parameterized: ``` Class_name (argument); ```

 Non-parameterized: ``` Class_Name(); ```

 ### Destructor

 It is a special member function that destroys or destrcuts the object as soon as the scope of the object ends.

 Syntax: ``` ~Constructor_Name(); ```

  ## Example Code 1

```
#include <iostream>
using namespace std;

class Franchise {
     public:
       void KFC(){
        cout << "We have the best chicken" << endl;
       }
       void BurgerKing(){
        cout << "We have the best burgers" <<  endl;
        }
};

int main(){
 Franchise franchise1;
  franchise1.KFC();
  franchise.BurgerKing();
  return 0;
}
```
### Output
```
We have the best chicken
We have the best burgers
```

 ## Example Code 2

 ```
#include <iostream>
using namespace std;


class Billboard {
 private:
   string title;

  public:
    void setTitle(string x){
      title = x;
    }
    string getTitle(){
      return title;
    }

};

int main(){
  Billboard bill;
  bill.setTitle("BUN DA REST");
  cout << bill.getTitle();
  return 0;
}
```

### Output
```
BUN DA REST
```

## Example code 3: Using Constructors
```
#include<iostream>
using namespace std;

class Billboard{
   private:
    string title;
   public:

     Billboard(string x){
       setTitle(b);
     }
     
     string getTitle(){
        return title;
      }

    void setTitle(string a){
       title = a;
     }
};


int main(){
   Billboard bill("Top 3 brands rising out of UK");
   cout << bill.getTitle() << endl;
   return 0;
}
 ```

### Output
```
Top 3 brands rising out of UK
```

### Example Code 4: Using Destructors

```
#include<iostream>
using namespace std;

class Game{

    public:
      Game(){
       cout<< "This is the constructor" << endl;
      }
      ~Game() {
       cout << "This is the destructor" << endl;
      }
      void display(){
         cout << "You are playing a game" << endl;
     }
};


int main(){
   Game fifa;
   game.display();
   return 0;
}
```
### Output 
```
This is the constructor

You are playing a game

This is the destructor

```
