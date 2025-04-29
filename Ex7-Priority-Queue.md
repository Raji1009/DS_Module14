# EXERCISE 7: Priority Queue

## DATE:
*29-04-2025*

## AIM:
To formulate the C code to **display the elements** of the **priority queue** after **insertion and deletion** operations.

---

## Algorithm:
1. Start the program.
2. Create a structure or a 2D array to store elements along with their priority.
3. For **insertion**:
   - Add the element and its priority.
   - Reorder the queue based on priority (lower number = higher priority).
4. For **deletion**:
   - Remove the element with the **highest priority** (lowest number).
5. Display the current state of the queue after every operation.
6. End the program.

---

## Program:
```c
/*
Program to display the elements of the priority queue after insertion and deletion operation
Developed by: Rajalakshmi R
RegisterNumber: 212223110037
*/

#include <stdio.h>
#define SIZE 10

struct PriorityQueue {
    int data;
    int priority;
};

struct PriorityQueue pq[SIZE];
int count = 0;

// Function to insert element
void insert(int data, int priority) {
    if(count == SIZE) {
        printf("Queue is full!\n");
        return;
    }
    int i = count - 1;

    // Sort based on priority (lower value = higher priority)
    while(i >= 0 && pq[i].priority > priority) {
        pq[i + 1] = pq[i];
        i--;
    }
    pq[i + 1].data = data;
    pq[i + 1].priority = priority;
    count++;

    printf("Inserted: %d with priority %d\n", data, priority);
}

// Function to delete element with highest priority
void deleteHighestPriority() {
    if(count == 0) {
        printf("Queue is empty!\n");
        return;
    }
    printf("Deleted: %d with priority %d\n", pq[0].data, pq[0].priority);
    for(int i = 1; i < count; i++) {
        pq[i - 1] = pq[i];
    }
    count--;
}

// Function to display the queue
void display() {
    if(count == 0) {
        printf("Queue is empty!\n");
        return;
    }
    printf("Priority Queue:\n");
    for(int i = 0; i < count; i++) {
        printf("Element: %d, Priority: %d\n", pq[i].data, pq[i].priority);
    }
}

int main() {
    insert(10, 2);
    insert(5, 1);
    insert(20, 3);
    insert(15, 2);

    printf("\nAfter Insertions:\n");
    display();

    printf("\nPerforming Deletion...\n");
    deleteHighestPriority();
    deleteHighestPriority();

    printf("\nAfter Deletions:\n");
    display();

    return 0;
}
```

## Output:

![image](https://github.com/user-attachments/assets/38486a9a-d71a-4678-b9d3-89d6c23add01)


## Result:
Thus, the C program to display the elements of the priority queue after insertion and deletion operation is implemented successfully
