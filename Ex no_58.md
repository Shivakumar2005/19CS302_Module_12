# EX 58 C Function to display queue elements using Linked List.(use integer data in the queue)
## DATE:
## AIM:
To write a C Function to display queue elements using Linked List.

## Algorithm
1. Start the program.
2. Define a struct Node with int data and next pointer.
3. Implement an enqueue function to insert elements at the rear of the queue.
4. Implement a display function to traverse and display all elements in the queue. 
5. In main(), enqueue a few elements and call display to show them.  

## Program:
/*
C Function to display queue elements using Linked List.(use integer data in the queue)

Developed by: 
RegisterNumber:  
*/

#include <stdio.h>
#include <stdlib.h>

// Structure for queue node
struct Node {
    int data;
    struct Node* next;
};

// Function to enqueue (insert at rear)
void enqueue(struct Node** front, struct Node** rear, int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    if (*rear == NULL) {
        *front = *rear = newNode;
    } else {
        (*rear)->next = newNode;
        *rear = newNode;
    }
}

// Function to display queue elements
void display(struct Node* front) {
    if (front == NULL) {
        printf("Queue is empty\n");
        return;
    }
    printf("Queue elements are: ");
    while (front != NULL) {
        printf("%d ", front->data);
        front = front->next;
    }
    printf("\n");
}

int main() {
    struct Node* front = NULL;
    struct Node* rear = NULL;

    enqueue(&front, &rear, 10);
    enqueue(&front, &rear, 20);
    enqueue(&front, &rear, 30);

    display(front);

    return 0;
}


## Output:

<img width="1703" height="671" alt="image" src="https://github.com/user-attachments/assets/ecb9091b-2a9d-4d72-9a6c-77f7a5ca1cc5" />


## Result:
Thus the program was executed and the output was verified successfully.
