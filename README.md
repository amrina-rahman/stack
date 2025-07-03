# stack
#include <stdio.h>

#define MAXSIZE 10

int stack[MAXSIZE], top = -1;

void push();
void pop();
void display();

int main() {
    int choice;
    do {
        printf("\n-------- Stack Menu --------\n");
        printf("1. Push\n2. Pop\n3. Display\n4. Exit\n");
        printf("----------------------------\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1: push(); break;
            case 2: pop(); break;
            case 3: display(); break;
            case 4: printf("Exiting program.\n"); break;
            default: printf("Invalid choice\n");
        }
    } while (choice != 4);
    return 0;
}

void push() {
    int n;
    if (top == MAXSIZE - 1) {
        printf("Stack Overflow!\n");
    } else {
        printf("Enter an element to push: ");
        scanf("%d", &n);
        top++;
        stack[top] = n;
    }
}

void pop() {
    int n;
    if (top == -1) {
        printf("Stack Underflow (Empty Stack)\n");
    } else {
        n = stack[top];
        top--;
        printf("Popped Element: %d\n", n);
    }
}

void display() {
    int i;
    if (top == -1) {
        printf("Stack is empty.\n");
    } else {
        printf("Stack elements:\n");
        for (i = top; i >= 0; i--) {
            printf("%d\n", stack[i]);
        }
    }
}
