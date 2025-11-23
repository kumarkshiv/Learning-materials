# Networks (Assessment/Interview Questions)
Q) A user wants to access/download multiple files (e.g., image, pdf, video, etc.) from a website. How does *HTTP1.1* handles this.?

Q) Why the use of IPv6 is being delayed.? What is the reason for that? 

Q) What is the main goal of CSMA/CD?

# OS (Assessment/Interview Questions)

Q) Trap vs interrupt

Q) Bealedy Anomaly


# Architecture (Assessment/Interview Questions)

Q) TLB

Q) In a pipelining architecture, why the empty slots inserted into the pipeline

Q) RAID5


# OOPs (Assessment/Interview Questions)

Q) Slice in C++:

  - In C++, "slice" (i..e, object slicing) is a concept that happens when a **derived class (child class)** object is assigned to a **base class (parent)** object by value. The extra parts of the derived class get cut off (sliced) and only the base part is kept.
  - Simple Explanation (Imagine a Pizza Slice):
    - A Derived class is like a big pizza with extra toppings.
    - A Base class is like a small plain pizza.
    - If you try to put the big pizza into the small pizza box:
      - The extra toppings get cut off (sliced).
      - That is **object slicing.**

Q) Virtual functions:
  
  - A virtual function in C++ is a function in a **base class (Parent)** that you expect to override in a **derived class (Child)**, and it enables **runtime polymorphism**.
  - A virtual destructor ensures that when you delete a derived object (child) through a base class (parent) pointer, the derived class destructor is also executed.
  - Example:
```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    virtual void sound() {     // virtual keyword
        cout << "Animal makes sound\n";
    }
};

class Dog : public Animal {
public:
    void sound() override {
        cout << "Dog barks\n";
    }
};

int main() {
    Animal* a = new Dog();
    a->sound();   // ✔ Calls Dog::sound()
}
```

Q) Virtual function Destructors:

- A virtual destructor is a destructor in a **base class** that is marked as **virtual**, so that when you delete an object through a base class pointer, the **derived class** destructor is also called.

Q) Friend function in C++:

  - A friend function is not part of the class. It has access to private and protected members of the class. It is declared inside the class using the keyword friend.


# DSA (Assessment/Interview Questions)

Q) Code to validate if the given tree is BST or not. (With and without recursion)

Q) Properties of Red/Black tree and its usecase

Q) What is union find? Why it is used? What are it's supported operations and there time complexity.
