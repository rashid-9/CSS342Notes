# C++ Basics

### <ins>Printing out Statements</ins>

```
#include <iostream>
int main() {
 std:: cout << "Hello World" ;
 return 0;
 }
 ```

``` :: ``` - Scope Resolution Operator. This tells the compiler to use the cout object from the std namespace. it specificies which namespace it should use, because many libraries will use cout. The std namespace is available through the iostream file.

``` << ``` - Insertion Operator. It is used to format the data according to its data type and then send it to the cout object, which displays it in the terminal.

A <ins>**namespace**</ins> is a feature in C++ that allows you to group related code together to avoid naming conflicts:
 - 1 single line of code = statement
 - A group of statements = function
 - A group of functions and variable = class
 - A collection of different classes, objects, functions and variables = Namespace.

 ### <ins>Declaring variables</ins>

 ```
int lucky_number;
```

``` int ``` - Specify datatype.

``` lucky_number ``` - Specify name of variable.

 ### <ins>Printing variables</ins>


```
std:: cout << lucky_number:
```

To print to the next line add ``` << std:: endl; ```

### <ins>Tip</ins>

If you don't want to specify namespace std each time when printing all you have write is:
``` using namespace std ```

After your ``` #include ``` lines.

### <ins>Taking Inputs</ins>

```
cin >> lucky_number;
```
So first you would write a print statement before the cin line saying: Enter a number

### <ins>Loops</ins>

**While loop**
```
while(a<5){
 cout << a << endl;
 a++;
}
```

```cout << a << endl; ``` - This prints the variable a. Because we said using namespace std before we don't have to write std.

**Do While Loop**
```
int a =0;
do {
 cout << a << endl;
 a++;
} while(a<5);
```
It will do what's inside the code then check the condition. This is useful if you want  something to be executed first then condition checked after

**For Loop**
```
for(int i = 0; i < 5; i++){
 cout << i << endl;
}
```

### <ins>Conditional Statements</ins>

**If Statements**
```
int a = 5;
int b = 6;
if( a > b ){
 cout << "A won!" << endl;
}
else {
 cout << "B won!" << endl;
 }
else if ( a == b ) {
 cout << "They are equal" << endl;
}
```

**Switch Statement**
```
int num_of_likes = 400;
switch(num_of_likes){
 case 10:
  cout << "Low likes" << endl;
  break;
 case 500:
  cout << "High likes" << endl;
  break;
 default:
  cout << "Not enough information" << endl;
  break;
}
```

### <ins>Functions</ins>
```
int add(int a, int b) {
 return a+b;
}

int main() {
 int sum;
 sum = add(5,3);
 return 0;
}
```

``` int ``` - Return type

``` add ``` - Function name

``` (int a, int b) ``` - Parameters and Type.

### <ins>Constants</ins>
```
const double pi = 3.14;
```

```const``` - Declare const


### <ins>To Run C++ Program</ins>

Type into terminal:
```
g++ hello_world.cpp -o hello
```

Then type - ```./hello.exe```

``` hello_world.cpp ``` -  The file you want to run

``` hello ``` - Name you want for output file

 

