# EX 60 C function to find the peek element of the queue using linked list.
## DATE:08/09/2025
## AIM:
To write a C function to find the peek element of the queue using linked list.

## Algorithm
1. Start the program.
2. Define a struct Node with int data and a pointer next.
3. Implement an enqueue() function to insert elements at the rear of the queue.
4. Implement a peek() function to return/display the front element of the queue. 
5. Implement a peek() function to return/display the front element of the queue.  

## Program:
#include <stdio.h>
#include <stdlib.h>

// Structure for queue node
struct Node {
    int data;
    struct Node* next;
};

// Enqueue function
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

// Peek function
void peek(struct Node* front) {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }
    printf("Peek element is: %d\n", front->data);
}

int main() {
    struct Node* front = NULL;
    struct Node* rear = NULL;

    enqueue(&front, &rear, 10);
    enqueue(&front, &rear, 20);
    enqueue(&front, &rear, 30);

    peek(front);

    return 0;
}

## Output:

<img width="1662" height="685" alt="image" src="https://github.com/user-attachments/assets/1be75501-a9f5-4045-b670-a984a25c3794" />


## Result:
Thus the program was executed and the output was verified successfully.
