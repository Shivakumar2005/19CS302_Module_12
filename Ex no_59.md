# EX 59 C functions to perform-enqueue, dequeue, peek, display in Queue using Linked List.(use character data in Queue).
## DATE:08/09/2025
## AIM:
To write a C functions to perform-enqueue, dequeue, peek, display in Queue using Linked List.

## Algorithm
1. Start the program.
2. Define a struct Node with char data and a pointer next.
3. Implement enqueue() to insert a character at the rear of the queue.
4. Implement dequeue() to remove a character from the front of the queue. 
5. Call these functions in main() to demonstrate queue operations.  

## Program:
#include <stdio.h>
#include <stdlib.h>

// Structure for queue node
struct Node {
    char data;
    struct Node* next;
};

// Enqueue function
void enqueue(struct Node** front, struct Node** rear, char value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    if (*rear == NULL) {
        *front = *rear = newNode;
    } else {
        (*rear)->next = newNode;
        *rear = newNode;
    }
    printf("%c enqueued to queue\n", value);
}

// Dequeue function
void dequeue(struct Node** front, struct Node** rear) {
    if (*front == NULL) {
        printf("Queue Underflow! Cannot dequeue.\n");
        return;
    }
    struct Node* temp = *front;
    printf("%c dequeued from queue\n", temp->data);
    *front = (*front)->next;
    if (*front == NULL) {
        *rear = NULL;
    }
    free(temp);
}

// Peek function
void peek(struct Node* front) {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }
    printf("Front element is: %c\n", front->data);
}

// Display function
void display(struct Node* front) {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }
    printf("Queue elements are: ");
    while (front != NULL) {
        printf("%c ", front->data);
        front = front->next;
    }
    printf("\n");
}

int main() {
    struct Node* front = NULL;
    struct Node* rear = NULL;

    enqueue(&front, &rear, 'A');
    enqueue(&front, &rear, 'B');
    enqueue(&front, &rear, 'C');

    display(front);
    peek(front);

    dequeue(&front, &rear);
    display(front);
    peek(front);

    return 0;
}

## Output:

<img width="1453" height="676" alt="image" src="https://github.com/user-attachments/assets/ae954aea-eab1-4a65-b624-cc0b21813693" />


## Result:
Thus the program was executed and the output was verified successfully.
