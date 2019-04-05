# Self-definition class of C++
- Header file: "xxx.h", declaration of the class;
- C++ file: Implementation of the class;
- Call the self-defined class.

***

## Header file "person.h"
```c++
#ifndef _PERSON_H
#define _PERSON_H

#include <iostream>
#include <string>

using namespace std;

class Person {
    private:
        string name;
        int age;

    public:
        Person();
        Person(const string &_name);
        Person(const string &_name, const int &_age);

    public:
        int getAge();
        string getName();

    public:
         ~Person();
};

#endif
```

## C++ file "person.cpp"
```c++
#include "person.h"

using namespace std;

Person:: Person(): name("anonymous"), age(20) {
    cout << "Defaul constructor has been called!" << endl;
}

Person:: Person(const string &_name): name(_name) {
    cout << "Constructor Person(const string &_name) has been called!" << endl;
}

Person:: Person(const string &_name, const int &_age): name(_name), age(_age) {
    cout << "Constructor Person(const string &_name, const int &_age) has been called!" << endl;
}

string Person:: getName() {
    return name;
}

int Person:: getAge() {
    return age;
}

Person:: ~Person() {
    cout << "Object has been deleted!" << endl;
}
```

## C++ file of calling class "Person"
```c++
#include <iostream>
#include "person.h"

using namespace std;

int main() {
    Person p("C++", 20);

    cout << "Name: " << p.getName() << "   age: " << p.getAge() << endl;
    return 0;
}
```

## Output
```
Constructor Person(const string &_name, const int &_age) has been called!
Name: C++   age: 20
Object has been deleted!
```
