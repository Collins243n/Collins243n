#include <iostream>
#include <string>
using namespace std;

// Base class: Person
class Person {
protected:
    string name;

public:
    void setName(string n) {
        name = n;
    }

    string getName() const {
        return name;
    }
};

// Derived class: Student
class Student : public Person {
private:
    int studentID;

public:
    // Constructor
    Student(string n, int id) {
        setName(n); // Call base class function to set name
        studentID = id;
    }

    int getStudentID() const {
        return studentID;
    }
};

// Derived class: GraduateStudent
class GraduateStudent : public Student {
private:
    string researchTopic;

public:
    // Constructor
    GraduateStudent(string n, int id, string topic) : Student(n, id) {
        researchTopic = topic;
    }

    string getResearchTopic() const {
        return researchTopic;
    }
};

int main() {
    // Create a Student object
    Student student("John", 1001);
    cout << "Student Name: " << student.getName() << endl;
    cout << "Student ID: " << student.getStudentID() << endl;

    // Create a GraduateStudent object
    GraduateStudent gradStudent("Alice", 2001, "Artificial Intelligence");
    cout << "\nGraduate Student Name: " << gradStudent.getName() << endl;
    cout << "Student ID: " << gradStudent.getStudentID() << endl;
    cout << "Research Topic: " << gradStudent.getResearchTopic() << endl;

    return 0;
}

