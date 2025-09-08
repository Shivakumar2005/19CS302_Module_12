# EX 57 C function to perfom push,pop and peek functions in Stack using Linked List.( store float data in stack)
## DATE:
## AIM:
To write a C function to perfom push,pop and peek functions in Stack using Linked List.

## Algorithm
1. Start the program.
2. Define a struct Node with float data and a pointer next.
3. Create a push function to insert float values into the stack.
4. Create a pop function to remove the top element from the stack. 
5. Create a peek function to display the top element without removing it.  

## Program:
#include <stdio.h>
#include <stdlib.h>

// Structure for stack node
struct Node {
    float data;
    struct Node* next;
};

// Push function
void push(struct Node** top, float value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = *top;
    *top = newNode;
    printf("%.2f pushed to stack\n", value);
}

// Pop function
void pop(struct Node** top) {
    if (*top == NULL) {
        printf("Stack Underflow! Cannot pop.\n");
        return;
    }
    struct Node* temp = *top;
    printf("%.2f popped from stack\n", temp->data);
    *top = (*top)->next;
    free(temp);
}

// Peek function
void peek(struct Node* top) {
    if (top == NULL) {
        printf("Stack is empty.\n");
        return;
    }
    printf("Top element is: %.2f\n", top->data);
}

int main() {
    struct Node* top = NULL;

    push(&top, 10.5);
    push(&top, 20.25);
    push(&top, 30.75);

    peek(top);   // Show top element

    pop(&top);   // Remove top element
    peek(top);   // Show new top element

    return 0;
}

## Output:

<img width="1674" height="682" alt="image" src="https://github.com/user-attachments/assets/8bbe3894-5fe4-4f60-9d2a-48e75940eb09" />


## Result:
Thus the program was executed and the output was verified successfully.
