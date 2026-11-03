# OOP Practical Programs — C++ Solutions

**Formatting note:** The code below is taken from the supplied PDF. Only indentation/spacing has been standardized for readability; program logic and statements have not intentionally been changed.

**Contents**
1. [Student Class](#student-class)
2. [Student Percentage](#student-percentage)
3. [Employee Display](#employee-display)
4. [Employee Array — Salary Greater Than 5000](#employee-array-salary-greater-than-5000)
5. [Rectangle Area](#rectangle-area)
6. [BankAccount](#bankaccount)
7. [Book Display](#book-display)
8. [Book Array — Price Greater Than 50](#book-array-price-greater-than-50)
9. [Student With Highest Percentage](#student-with-highest-percentage)
10. [Employee Total Salary (DA and HRA)](#employee-total-salary-da-and-hra)
11. [Method Overloading — Shape Areas](#method-overloading-shape-areas)
12. [Mobile Class](#mobile-class)
13. [Constructor Overloading — Shape Areas](#constructor-overloading-shape-areas)
14. [Parameterized Constructor — Rectangle](#parameterized-constructor-rectangle)
15. [Student Activity — Struct and Enum](#student-activity-struct-and-enum)
16. [Pointer to Derived Class](#pointer-to-derived-class)
17. [Diamond Problem — Virtual Base Class](#diamond-problem-virtual-base-class)
18. [Function Template Swap](#function-template-swap)
19. [Server / Client Inheritance](#server-client-inheritance)
20. [File Handling](#file-handling)
21. [Multilevel Inheritance](#multilevel-inheritance)
22. [Single Inheritance](#single-inheritance)

## Program 1: Student Class

Source file: `Program_01_Student_Class.cpp`

```cpp
#include <iostream>
#include <string>
using namespace std;
class Student {
    int rollno;
    string name;
    float marks;
    public:
    void accept() {
        cout << "Enter roll number: ";
        cin >> rollno;
        cin.ignore();
        cout << "Enter name: ";
        getline(cin, name);
        cout << "Enter marks: ";
        cin >> marks;
    }
    void display() {
        cout << "\n--- Student Details ---\n";
        cout << "Roll No : " << rollno << endl;
        cout << "Name    : " << name << endl;
        cout << "Marks   : " << marks << endl;
    }
};
int main() {
    Student s;
    s.accept();
    s.display();
    return 0;
}
```

## Program 2: Student Percentage

Source file: `Program_02_Student_Percentage.cpp`

```cpp
#include <iostream>
#include <string>
using namespace std;
class Student {
    int rollno;
    string name;
    float m1, m2, percentage;
    public:
    void accept() {
        cout << "Enter roll number: ";
        cin >> rollno;
        cin.ignore();
        cout << "Enter name: ";
        getline(cin, name);
        cout << "Enter marks of subject 1 (out of 100): ";
        cin >> m1;
        cout << "Enter marks of subject 2 (out of 100): ";
        cin >> m2;
    }
    void calculate() {
        percentage = (m1 + m2) / 200 * 100;
    }
    void display() {
        cout << "\n--- Student Record ---\n";
        cout << "Roll No    : " << rollno << endl;
        cout << "Name       : " << name << endl;
        cout << "Subject 1  : " << m1 << endl;
        cout << "Subject 2  : " << m2 << endl;
        cout << "Percentage : " << percentage << "%" << endl;
    }
};
int main() {
    Student s;
    s.accept();
    s.calculate();
    s.display();
    return 0;
}
```

## Program 3: Employee Display

Source file: `Program_03_Employee_Display.cpp`

```cpp
#include <iostream>
#include <string>
using namespace std;
class Employee {
    int empId;
    string name;
    float salary;
    public:
    Employee(int id, string n, float s) {
        empId = id;
        name = n;
        salary = s;
    }
    void display() {
        cout << "--- Employee Details ---\n";
        cout << "Employee ID : " << empId << endl;
        cout << "Name        : " << name << endl;
        cout << "Salary      : " << salary << endl;
    }
};
int main() {
    Employee e(501, "Rahul Sharma", 45000.50);
    e.display();
    return 0;
}
```

## Program 4: Employee Array — Salary Greater Than 5000

Source file: `Program_04_Employee_Array_Salary_Greater_Than_5000.cpp`

```cpp
#include <iostream>
#include <string>
using namespace std;
class Employee {
    string emp_name;
    int emp_id;
    float salary;
    public:
    void accept() {
        cout << "Enter employee name: ";
        cin >> ws;
        getline(cin, emp_name);
        cout << "Enter employee id: ";
        cin >> emp_id;
        cout << "Enter salary: ";
        cin >> salary;
    }
    void display() {
        cout << emp_id << "\t" << emp_name << "\t\t" << salary << endl;
    }
    float getSalary() { return salary; }
};
int main() {
    Employee e[5];
    for (int i = 0; i < 5; i++) {
        cout << "\nEmployee " << i + 1 << ":\n";
        e[i].accept();
    }
    cout << "\nEmployees with salary greater than 5000:\n";
    cout << "ID\tName\t\tSalary\n";
    for (int i = 0; i < 5; i++) {
        if (e[i].getSalary() > 5000)
        e[i].display();
    }
    return 0;
}
```

## Program 5: Rectangle Area

Source file: `Program_05_Rectangle_Area.cpp`

```cpp
#include <iostream>
using namespace std;
class Rectangle {
    float length, breadth;
    public:
    void accept() {
        cout << "Enter length : ";
        cin >> length;
        cout << "Enter breadth: ";
        cin >> breadth;
    }
    float area() {
        return length * breadth;
    }
    void display() {
        cout << "Area of rectangle = " << area() << endl;
    }
};
int main() {
    Rectangle r;
    r.accept();
    r.display();
    return 0;
}
```

## Program 6: BankAccount

Source file: `Program_06_BankAccount.cpp`

```cpp
#include <iostream>
using namespace std;
class BankAccount {
    long accNo;
    float balance;
    public:
    void accept() {
        cout << "Enter account number: ";
        cin >> accNo;
        cout << "Enter balance: ";
        cin >> balance;
    }
    void display() {
        cout << "\n--- Account Details ---\n";
        cout << "Account Number : " << accNo << endl;
        cout << "Balance        : Rs. " << balance << endl;
    }
};
int main() {
    BankAccount b;
    b.accept();
    b.display();
    return 0;
}
```

## Program 7: Book Display

Source file: `Program_07_Book_Display.cpp`

```cpp
#include <iostream>
#include <string>
using namespace std;
class Book {
    string title, author;
    float price;
    public:
    Book(string t, string a, float p) {
        title = t;
        author = a;
        price = p;
    }
    void display() {
        cout << "--- Book Details ---\n";
        cout << "Title  : " << title << endl;
        cout << "Author : " << author << endl;
        cout << "Price  : " << price << endl;
    }
};
int main() {
    Book b("The C++ Programming Language", "Bjarne Stroustrup", 799.0);
    b.display();
    return 0;
}
```

## Program 8: Book Array — Price Greater Than 50

Source file: `Program_08_Book_Array_Price_Greater_Than_50.cpp`

```cpp
#include <iostream>
#include <string>
using namespace std;
class Book {
    string title, author;
    float price;
    public:
    void accept() {
        cout << "Enter title : ";
        cin >> ws;
        getline(cin, title);
        cout << "Enter author: ";
        getline(cin, author);
        cout << "Enter price : ";
        cin >> price;
    }
    void display() {
        cout << title << "\t" << author << "\t" << price << endl;
    }
    float getPrice() { return price; }
};
int main() {
    Book b[5];
    for (int i = 0; i < 5; i++) {
        cout << "\nBook " << i + 1 << ":\n";
        b[i].accept();
    }
    cout << "\nBooks with price greater than 50:\n";
    cout << "Title\tAuthor\tPrice\n";
    for (int i = 0; i < 5; i++) {
        if (b[i].getPrice() > 50)
        b[i].display();
    }
    return 0;
}
```

## Program 9: Student With Highest Percentage

Source file: `Program_09_Student_With_Highest_Percentage.cpp`

```cpp
#include <iostream>
#include <string>
using namespace std;
class Student {
    int rollno;
    string name;
    float m1, m2, percentage;
    public:
    void accept() {
        cout << "Enter roll number: ";
        cin >> rollno;
        cout << "Enter name: ";
        cin >> ws;
        getline(cin, name);
        cout << "Enter marks of subject 1: ";
        cin >> m1;
        cout << "Enter marks of subject 2: ";
        cin >> m2;
        percentage = (m1 + m2) / 200 * 100;
    }
    void display() {
        cout << "Roll No    : " << rollno << endl;
        cout << "Name       : " << name << endl;
        cout << "Subject 1  : " << m1 << endl;
        cout << "Subject 2  : " << m2 << endl;
        cout << "Percentage : " << percentage << "%" << endl;
    }
    float getPercentage() { return percentage; }
};
int main() {
    Student s[2];
    for (int i = 0; i < 2; i++) {
        cout << "\nStudent " << i + 1 << ":\n";
        s[i].accept();
    }
    cout << "\n--- Student with highest percentage ---\n";
    if (s[0].getPercentage() >= s[1].getPercentage())
    s[0].display();
    else
    s[1].display();
    return 0;
}
```

## Program 10: Employee Total Salary (DA and HRA)

Source file: `Program_10_Employee_Total_Salary_DA_and_HRA.cpp`

```cpp
#include <iostream>
#include <string>
using namespace std;
class Employee {
    int empid;
    string name;
    float basic, da, hra, total;
    public:
    void accept() {
        cout << "Enter employee id: ";
        cin >> empid;
        cout << "Enter name: ";
        cin >> ws;
        getline(cin, name);
        cout << "Enter basic salary: ";
        cin >> basic;
    }
    void calculate() {
        da = 0.10 * basic;
        hra = 0.20 * basic;
        total = basic + da + hra;
    }
    void display() {
        cout << "Emp ID       : " << empid << endl;
        cout << "Name         : " << name << endl;
        cout << "Basic Salary : " << basic << endl;
        cout << "DA (10%)     : " << da << endl;
        cout << "HRA (20%)    : " << hra << endl;
        cout << "Total Salary : " << total << endl;
    }
};
int main() {
    Employee e[2];
    for (int i = 0; i < 2; i++) {
        cout << "\nEmployee " << i + 1 << ":\n";
        e[i].accept();
        e[i].calculate();
    }
    cout << "\n===== Salary Details =====\n";
    for (int i = 0; i < 2; i++) {
        cout << "\nEmployee " << i + 1 << ":\n";
        e[i].display();
    }
    return 0;
}
```

## Program 11: Method Overloading — Shape Areas

Source file: `Program_11_Method_Overloading_Shape_Areas.cpp`

```cpp
#include <iostream>
using namespace std;
class shape {
    public:
    // Circle: one float argument (radius)
    float area(float r) {
        return 3.14159 * r * r;
    }
    // Square: one int argument (side)
    int area(int side) {
        return side * side;
    }
    // Rectangle: two float arguments (length, breadth)
    float area(float l, float b) {
        return l * b;
    }
    // Triangle: two int arguments (base, height)
    float area(int b, int h) {
        return 0.5 * b * h;
    }
};
int main() {
    shape s;
    cout << "Area of Circle (r = 5.0)         : " << s.area(5.0f) << endl;
    cout << "Area of Square (side = 4)        : " << s.area(4) << endl;
    cout << "Area of Rectangle (6.5 x 3.2)    : " << s.area(6.5f, 3.2f) << endl;
    cout << "Area of Triangle (b = 8, h = 5)  : " << s.area(8, 5) << endl;
    return 0;
}
```

## Program 12: Mobile Class

Source file: `Program_12_Mobile_Class.cpp`

```cpp
#include <iostream>
#include <string>
using namespace std;
class Mobile {
    string Company_name;
    float Screen_Size;
    public:
    void accept() {
        cout << "Enter company name: ";
        getline(cin, Company_name);
        cout << "Enter screen size (inches): ";
        cin >> Screen_Size;
    }
    void display() {
        cout << "\n--- Mobile Details ---\n";
        cout << "Company Name : " << Company_name << endl;
        cout << "Screen Size  : " << Screen_Size << " inches" << endl;
    }
};
int main() {
    Mobile m;
    m.accept();
    m.display();
    return 0;
}
```

## Program 13: Constructor Overloading — Shape Areas

Source file: `Program_13_Constructor_Overloading_Shape_Areas.cpp`

```cpp
#include <iostream>
using namespace std;
class shape {
    float area;
    const char *type;
    public:
    // Circle: (double radius)
    shape(double r) {
        area = 3.14159 * r * r;
        type = "Circle";
    }
    // Square: (int side)
    shape(int side) {
        area = side * side;
        type = "Square";
    }
    // Rectangle: (double length, double breadth)
    shape(double l, double b) {
        area = l * b;
        type = "Rectangle";
    }
    // Triangle: (int base, int height)
    shape(int b, int h) {
        area = 0.5 * b * h;
        type = "Triangle";
    }
    void display() {
        cout << "Area of " << type << " = " << area << endl;
    }
};
int main() {
    shape c(5.0);        // circle, radius 5.0
    shape s(4);          // square, side 4
    shape r(6.5, 3.2);   // rectangle, 6.5 x 3.2
    shape t(8, 5);       // triangle, base 8, height 5
    c.display();
    s.display();
    r.display();
    t.display();
    return 0;
}
```

## Program 14: Parameterized Constructor — Rectangle

Source file: `Program_14_Parameterized_Constructor_Rectangle.cpp`

```cpp
#include <iostream>
using namespace std;
class Rectangle {
    float length, width;
    public:
    Rectangle(float l, float w) {   // parameterized constructor
        length = l;
        width = w;
    }
    float area() {
        return length * width;
    }
    void display() {
        cout << "Length = " << length << ", Width = " << width
        << ", Area = " << area() << endl;
    }
};
int main() {
    Rectangle r1(10, 5);
    Rectangle r2(7.5, 4.2);
    cout << "Rectangle 1: ";
    r1.display();
    cout << "Rectangle 2: ";
    r2.display();
    return 0;
}
```

## Program 15: Student Activity — Struct and Enum

Source file: `Program_15_Student_Activity_Struct_and_Enum.cpp`

```cpp
#include <iostream>
#include <string>
#include <iomanip>
using namespace std;
enum ParticipationStatus { NotParticipated, Participated, Completed };
struct Activity {
    string activityName;
    int durationHours;
    ParticipationStatus status;
};
class Student {
    string name;
    int rollNo;
    char division;
    float activityScore;
    Activity activity;
    public:
    void accept() {
        int choice;
        cout << "Enter student name: ";
        cin >> ws;
        getline(cin, name);
        cout << "Enter roll number: ";
        cin >> rollNo;
        cout << "Enter division (A/B/C): ";
        cin >> division;
        cout << "Enter activity score: ";
        cin >> activityScore;
        cout << "Enter activity name: ";
        cin >> ws;
        getline(cin, activity.activityName);
        cout << "Enter duration (hours): ";
        cin >> activity.durationHours;
        do {
            cout << "Status (0-NotParticipated, 1-Participated, 2-Completed): ";
            cin >> choice;
        } while (choice < 0 || choice > 2);
        activity.status = static_cast<ParticipationStatus>(choice);
    }
    string statusText() {
        switch (activity.status) {
            case NotParticipated: return "Not Participated";
            case Participated:    return "Participated";
            case Completed:       return "Completed";
        }
        return "Unknown";
    }
    void display() {
        cout << left << setw(12) << name
        << setw(6)  << rollNo
        << setw(6)  << division
        << setw(8)  << activityScore
        << setw(16) << activity.activityName
        << setw(8)  << activity.durationHours
        << statusText() << endl;
    }
};
int main() {
    int n;
    cout << "Enter number of students: ";
    cin >> n;
    Student s[10];
    for (int i = 0; i < n; i++) {
        cout << "\nStudent " << i + 1 << ":\n";
        s[i].accept();
    }
    cout << "\n=========== Activity Participation Summary ===========\n";
    cout << left << setw(12) << "Name" << setw(6) << "Roll"
    << setw(6) << "Div" << setw(8) << "Score"
    << setw(16) << "Activity" << setw(8) << "Hours"
    << "Status" << endl;
    cout << string(70, '-') << endl;
    for (int i = 0; i < n; i++)
    s[i].display();
    return 0;
}
```

## Program 16: Pointer to Derived Class

Source file: `Program_16_Pointer_to_Derived_Class.cpp`

```cpp
#include <iostream>
using namespace std;
// ---------- Single inheritance ----------
class Base {
    public:
    int b;
    void showBase() { cout << "Base class: b = " << b << endl; }
};
class Derived : public Base {
    public:
    int d;
    void showDerived() { cout << "Derived class: d = " << d << endl; }
};
// ---------- Multilevel inheritance ----------
class A {
    public:
    int a;
    void showA() { cout << "Class A: a = " << a << endl; }
};
class B : public A {
    public:
    int b;
    void showB() { cout << "Class B: b = " << b << endl; }
};
class C : public B {
    public:
    int c;
    void showC() { cout << "Class C: c = " << c << endl; }
};
int main() {
    cout << "===== Single Inheritance =====\n";
    Derived obj;
    Derived *dptr = &obj;          // pointer to derived class
    dptr->b = 10;                  // base member through derived pointer
    dptr->d = 20;
    dptr->showBase();
    dptr->showDerived();
    Base *bptr = &obj;             // base pointer to derived object
    cout << "Using base pointer: ";
    bptr->showBase();
    cout << "\n===== Multilevel Inheritance =====\n";
    C objC;
    C *cptr = &objC;               // pointer to derived (class C)
    cptr->a = 1;
    cptr->b = 2;
    cptr->c = 3;
    cptr->showA();
    cptr->showB();
    cptr->showC();
    B *bp = &objC;                 // pointer to intermediate class
    A *ap = &objC;                 // pointer to root class
    cout << "Using pointer of class B: ";
    bp->showB();
    cout << "Using pointer of class A: ";
    ap->showA();
    return 0;
}
```

## Program 17: Diamond Problem — Virtual Base Class

Source file: `Program_17_Diamond_Problem_Virtual_Base_Class.cpp`

```cpp
#include <iostream>
using namespace std;
class Person {                       // common base (top of diamond)
    public:
    string name;
    Person() { cout << "Person constructor called\n"; }
};
// 'virtual' ensures only ONE copy of Person is inherited
class Teacher : virtual public Person {
    public:
    Teacher() { cout << "Teacher constructor called\n"; }
};
class Researcher : virtual public Person {
    public:
    Researcher() { cout << "Researcher constructor called\n"; }
};
class Professor : public Teacher, public Researcher {
    public:
    Professor() { cout << "Professor constructor called\n"; }
    void show() {
        // Without virtual: "request for member 'name' is ambiguous" error
        cout << "Professor name: " << name << endl;
    }
};
int main() {
    Professor p;
    p.name = "Dr. Shital Mehta";
    p.show();
    cout << "Size of Professor object: " << sizeof(p) << " bytes\n";
    return 0;
}
```

## Program 18: Function Template Swap

Source file: `Program_18_Function_Template_Swap.cpp`

```cpp
#include <iostream>
using namespace std;
template <class T>
void swapValues(T &a, T &b) {
    T temp = a;
    a = b;
    b = temp;
}
int main() {
    int i1, i2;
    float f1, f2;
    cout << "Enter two integers: ";
    cin >> i1 >> i2;
    cout << "Enter two floats  : ";
    cin >> f1 >> f2;
    cout << "\nBefore swap: i1 = " << i1 << ", i2 = " << i2 << endl;
    swapValues(i1, i2);
    cout << "After swap : i1 = " << i1 << ", i2 = " << i2 << endl;
    cout << "\nBefore swap: f1 = " << f1 << ", f2 = " << f2 << endl;
    swapValues(f1, f2);
    cout << "After swap : f1 = " << f1 << ", f2 = " << f2 << endl;
    return 0;
}
```

## Program 19: Server / Client Inheritance

Source file: `Program_19_Server_Client_Inheritance.cpp`

```cpp
#include <iostream>
#include <string>
using namespace std;
class Server {
    protected:
    string serv_name;
    int serv_port;
    public:
    void accept() {
        cout << "Enter server name: ";
        cin >> ws;
        getline(cin, serv_name);
        cout << "Enter server port: ";
        cin >> serv_port;
    }
    void show() {
        cout << "Server Name : " << serv_name << endl;
        cout << "Server Port : " << serv_port << endl;
    }
};
class Client : public Server {
    string client_name;
    int Client_port;
    public:
    void accept() {
        Server::accept();
        cout << "Enter client name: ";
        cin >> ws;
        getline(cin, client_name);
        cout << "Enter client port: ";
        cin >> Client_port;
    }
    void show() {
        Server::show();
        cout << "Client Name : " << client_name << endl;
        cout << "Client Port : " << Client_port << endl;
    }
};
int main() {
    Client c;
    c.accept();
    cout << "\n--- Server and Client Records ---\n";
    c.show();
    return 0;
}
```

## Program 20: File Handling

Source file: `Program_20_File_Handling.cpp`

```cpp
#include <iostream>
#include <fstream>
#include <string>
using namespace std;
int main() {
    // ----- Step 1: create file and write -----
    ofstream fout("student.txt");
    if (!fout) {
        cout << "Error: could not create file.\n";
        return 1;
    }
    string name, branch;
    int roll;
    cout << "Enter name  : ";
    getline(cin, name);
    cout << "Enter roll  : ";
    cin >> roll;
    cout << "Enter branch: ";
    cin >> ws;
    getline(cin, branch);
    fout << "Name: " << name << endl;
    fout << "Roll: " << roll << endl;
    fout << "Branch: " << branch << endl;
    fout.close();                       // ----- Step 2: close -----
    cout << "\nData written to student.txt and file closed.\n";
    // ----- Step 3: open as input and read -----
    ifstream fin("student.txt");
    if (!fin) {
        cout << "Error: could not open file.\n";
        return 1;
    }
    string line;
    cout << "\nReading from file:\n";
    while (getline(fin, line))
    cout << line << endl;
    fin.close();
    return 0;
}
```

## Program 21: Multilevel Inheritance

Source file: `Program_21_Multilevel_Inheritance.cpp`

```cpp
#include <iostream>
#include <string>
using namespace std;
class Student {
    protected:
    int rollno;
    string name;
    public:
    void getStudent() {
        cout << "Enter roll number: ";
        cin >> rollno;
        cout << "Enter name: ";
        cin >> ws;
        getline(cin, name);
    }
};
class Marks : public Student {
    protected:
    float m1, m2, m3;
    public:
    void getMarks() {
        cout << "Enter marks of 3 subjects: ";
        cin >> m1 >> m2 >> m3;
    }
};
class Result : public Marks {
    float total;
    public:
    void display() {
        total = m1 + m2 + m3;
        cout << "\n--- Result ---\n";
        cout << "Roll No : " << rollno << endl;
        cout << "Name    : " << name << endl;
        cout << "Marks   : " << m1 << ", " << m2 << ", " << m3 << endl;
        cout << "Total   : " << total << endl;
    }
};
int main() {
    Result r;
    r.getStudent();
    r.getMarks();
    r.display();
    return 0;
}
```

## Program 22: Single Inheritance

Source file: `Program_22_Single_Inheritance.cpp`

```cpp
#include <iostream>
#include <string>
using namespace std;
class Person {
    protected:
    string name;
    int age;
    public:
    void getPerson() {
        cout << "Enter name: ";
        getline(cin, name);
        cout << "Enter age: ";
        cin >> age;
    }
};
class Student : public Person {
    int rollno;
    public:
    void getStudent() {
        getPerson();
        cout << "Enter roll number: ";
        cin >> rollno;
    }
    void display() {
        cout << "\n--- Student Details ---\n";
        cout << "Name    : " << name << endl;
        cout << "Age     : " << age << endl;
        cout << "Roll No : " << rollno << endl;
    }
};
int main() {
    Student s;
    s.getStudent();
    s.display();
    return 0;
}
```
