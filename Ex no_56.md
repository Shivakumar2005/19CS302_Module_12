# EX 56 C function to display stack elements using Linked List.(store integer data in stack) .
## DATE:08/09/2025
## AIM:
To write a C function to display stack elements using Linked List.

## Algorithm
1. Start the program.
2. Define a struct Node with data and next pointer.
3. Create a push function to insert elements into the stack.
4. Create a display function to traverse and display stack elements. 
5. In main(), push a few elements and call the display function.  

## Program:
#include <stdio.h>
#include <stdlib.h>

// Structure for stack node
struct Node {
    int data;
    struct Node* next;
};

// Function to push an element into the stack
void push(struct Node** top, int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = *top;
    *top = newNode;
}

// Function to display stack elements
void display(struct Node* top) {
    if (top == NULL) {
        printf("Stack is empty\n");
        return;
    }
    printf("Stack elements are: ");
    while (top != NULL) {
        printf("%d ", top->data);
        top = top->next;
    }
    printf("\n");
}

int main() {
    struct Node* top = NULL;

    // Push some elements
    push(&top, 10);
    push(&top, 20);
    push(&top, 30);

    // Display stack
    display(top);

    return 0;
}

## Output:

<img width="1746" height="670" alt="image" src="https://github.com/user-attachments/assets/6bd5b35e-8c8f-4272-a01d-0d1d421c9350" />


## Result:
Thus the program was executed and the output was verified successfully.
