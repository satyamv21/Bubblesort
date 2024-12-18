# Bubblesort
#include <iostream>
#include <string.h>
const int SIZE = 5; // Renamed constant
using namespace std;

struct student {
    int rollno;
    char name[20];
    float SGPA;
};

void accept(struct student list[SIZE]);
void display(struct student list[SIZE]);
void bubblesort(struct student list[SIZE]);

int main() {
    struct student list[SIZE];

    accept(list);
    cout << "\nBefore Sorting:";
    display(list);

    bubblesort(list);
    cout << "\nAfter Sorting:";
    display(list);

    return 0;
}

void accept(struct student list[SIZE]) {
    for (int i = 0; i < SIZE; i++) {
        cout << "Enter roll no., name, and SGPA: ";
        cin >> list[i].rollno >> list[i].name >> list[i].SGPA;
    }
}

void display(struct student list[SIZE]) {
    cout << "\nRoll No.\tName\t\tSGPA\n";
    for (int i = 0; i < SIZE; i++) {
        cout << list[i].rollno << "\t\t" << list[i].name << "\t\t" << list[i].SGPA << "\n";
    }
}

void bubblesort(struct student list[SIZE]) {
    struct student temp;
    for (int i = 0; i < SIZE - 1; i++) {
        for (int j = 0; j < SIZE - 1 - i; j++) {
            if (list[j].rollno > list[j + 1].rollno) {
                temp = list[j];
                list[j] = list[j + 1];
                list[j + 1] = temp;
            }
        }
    }
}
