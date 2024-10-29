# Dsa
#include <stdio.h>
#include <string.h>
#define NUM_EMPLOYEES 5

typedef struct {
    char name[50];
    char department[50];
    double salary;
} Employee;

void swap(Employee *a, Employee *b) {
    Employee temp = *a;
    *a = *b;
    *b = temp;
}
void sortEmployeesBySalary(Employee employees[], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (employees[j].salary < employees[j + 1].salary) {
                swap(&employees[j], &employees[j + 1]);
            }
        }
    }
}
void displayEmployees(Employee employees[], int n) {
    printf("Employees sorted by salary (high to low):\n");
    printf("Name        Department       Salary\n");
    printf("----------------------------------------\n");
    for (int i = 0; i < n; i++) {
        printf("%-10s\t%-15s\t₱%.2f\n", employees[i].name, employees[i].department, employees[i].salary);
    }
}
int main() {
    Employee employees[NUM_EMPLOYEES] = {
        {"Alvin", "Engineering",75000.00},
        {"Certeza", "Marketing" ,50000.00},
        {"Charlie", "Engineering",82000.00},
        {"Diana", "Human Resources",47000.00},
        {"Eve", "Marketing ", 60000.00}
    };
    sortEmployeesBySalary(employees, NUM_EMPLOYEES);
    displayEmployees(employees, NUM_EMPLOYEES);

  return 0;
}
