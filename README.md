# c-practical-questions
# Question
Create a Student class with attributes: name, roll number, and marks.
Add member functions to input and display student details.
Create at least 3 objects and display their data.
```cpp

#include <iostream>
#include <string>
using namespace std;

class Student {
private:
    string name;
    int rollNumber;
    float marks;

public:
    void input() {
        cout << "Enter Name: ";
        getline(cin, name);

        cout << "Enter Roll Number: ";
        cin >> rollNumber;

        cout << "Enter Marks: ";
        cin >> marks;

        cin.ignore();
    }

    void display() {
        cout << "\nStudent Details:" << endl;
        cout << "Name: " << name << endl;
        cout << "Roll Number: " << rollNumber << endl;
        cout << "Marks: " << marks << endl;
    }
};

int main() {
    Student s1, s2, s3;   // Creating 3 objects

    cout << "Enter details for Student 1\n";
    s1.input();

    cout << "\nEnter details for Student 2\n";
    s2.input();

    cout << "\nEnter details for Student 3\n";
    s3.input();

    cout << "\n----- Displaying Student Data -----\n";
    s1.display();
    s2.display();
    s3.display();

    return 0;
}
```
# Question
Create a BankAccount class. Initialize account number and balance using a constructor. Display a message when the destructor is called. Create objects inside a function to observe destructor behavior.
```cpp
#include <iostream>
using namespace std;

class BankAccount {
private:
    int accountNumber;
    double balance;

public:
    BankAccount(int accNo, double bal) {
        accountNumber = accNo;
        balance = bal;
        cout << "Constructor called for Account No: " 
             << accountNumber << endl;
    }

    ~BankAccount() {
        cout << "Destructor called for Account No: " 
             << accountNumber << endl;
    }

    void display() {
        cout << "Account Number: " << accountNumber 
             << ", Balance: " << balance << endl;
    }
};

void createAccounts() {
    BankAccount acc1(101, 5000.0);
    BankAccount acc2(102, 8000.0);

    acc1.display();
    acc2.display();
}  

int main() {
    cout << "Inside main function\n";

    createAccounts();

    cout << "Back in main function\n";

    return 0;
}
```
# Question 
create an Employee class. Make salary private.Provide getter and setter functions.Add validation: salary cannot be negative. 
```cpp
#include <iostream>
using namespace std;

class Employee {
private:
    double salary;  
public:
    void setSalary(double s) {
        if (s >= 0) {
            salary = s;
        } else {
            cout << "Error: Salary cannot be negative!" << endl;
        }
    }

    // Getter function
    double getSalary() {
        return salary;
    }
};

int main() {
    Employee emp;

    emp.setSalary(50000);      // Valid salary
    cout << "Salary: " << emp.getSalary() << endl;

    emp.setSalary(-1000);      // Invalid salary
    cout << "Salary: " << emp.getSalary() << endl;

    return 0;
}
