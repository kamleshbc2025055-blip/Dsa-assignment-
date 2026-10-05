DSA ASSIGNMENT – STRUCTURES & ALGORITHMS

Q1. STACK USING ARRAY

Program:

#include <stdio.h>
#define MAX 5

int stack[MAX];
int top = -1;

void push(int x) {
    if (top == MAX - 1) {
        printf("Stack Overflow\n");
    } else {
        stack[++top] = x;
        printf("%d pushed into stack\n", x);
    }
}

void pop() {
    if (top == -1) {
        printf("Stack Underflow\n");
    } else {
        printf("%d popped from stack\n", stack[top--]);
    }
}

void peek() {
    if (top == -1) {
        printf("Stack is empty\n");
    } else {
        printf("Top element = %d\n", stack[top]);
    }
}

void display() {
    if (top == -1) {
        printf("Stack is empty\n");
    } else {
        printf("Stack elements: ");
        for (int i = top; i >= 0; i--) {
            printf("%d ", stack[i]);
        }
        printf("\n");
    }
}

int main() {
    push(10);
    push(20);
    push(30);

    display();
    peek();

    pop();
    display();

    return 0;
}


Time Complexity:
- PUSH = O(1)
- POP = O(1)
- PEEK = O(1)
- DISPLAY = O(n)

Space Complexity:
- Stack uses O(n) space.

Stack Overflow:
When the stack is full and we try to insert another element, Stack Overflow occurs.

Stack Underflow:
When the stack is empty and we try to remove an element, Stack Underflow occurs.


--------------------------------------------------

Q2. CIRCULAR QUEUE USING ARRAY

Program:

#include <stdio.h>
#define MAX 5

int queue[MAX];
int front = -1;
int rear = -1;

void enqueue(int x) {
    if ((rear + 1) % MAX == front) {
        printf("Queue is Full\n");
        return;
    }

    if (front == -1) {
        front = 0;
    }

    rear = (rear + 1) % MAX;
    queue[rear] = x;

    printf("%d inserted into queue\n", x);
}

void dequeue() {
    if (front == -1) {
        printf("Queue is Empty\n");
        return;
    }

    printf("%d deleted from queue\n", queue[front]);

    if (front == rear) {
        front = rear = -1;
    } else {
        front = (front + 1) % MAX;
    }
}

void display() {
    if (front == -1) {
        printf("Queue is Empty\n");
        return;
    }

    printf("Queue elements: ");

    int i = front;
    while (1) {
        printf("%d ", queue[i]);

        if (i == rear)
            break;

        i = (i + 1) % MAX;
    }

    printf("\n");
}

void showFront() {
    if (front == -1) {
        printf("Queue is Empty\n");
    } else {
        printf("Front element = %d\n", queue[front]);
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);DSA ASSIGNMENT – STRUCTURES & ALGORITHMS

Q1. STACK USING ARRAY

Program:

#include <stdio.h>
#define MAX 5

int stack[MAX];
int top = -1;

void push(int x) {
    if (top == MAX - 1) {
        printf("Stack Overflow\n");
    } else {
        stack[++top] = x;
        printf("%d pushed into stack\n", x);
    }
}

void pop() {
    if (top == -1) {
        printf("Stack Underflow\n");
    } else {
        printf("%d popped from stack\n", stack[top--]);
    }
}

void peek() {
    if (top == -1) {
        printf("Stack is empty\n");
    } else {
        printf("Top element = %d\n", stack[top]);
    }
}

void display() {
    if (top == -1) {
        printf("Stack is empty\n");
    } else {
        printf("Stack elements: ");
        for (int i = top; i >= 0; i--) {
            printf("%d ", stack[i]);
        }
        printf("\n");
    }
}

int main() {
    push(10);
    push(20);
    push(30);

    display();
    peek();

    pop();
    display();

    return 0;
}


Time Complexity:
- PUSH = O(1)
- POP = O(1)
- PEEK = O(1)
- DISPLAY = O(n)

Space Complexity:
- Stack uses O(n) space.

Stack Overflow:
When the stack is full and we try to insert another element, Stack Overflow occurs.

Stack Underflow:
When the stack is empty and we try to remove an element, Stack Underflow occurs.


--------------------------------------------------

Q2. CIRCULAR QUEUE USING ARRAY

Program:

#include <stdio.h>
#define MAX 5

int queue[MAX];
int front = -1;
int rear = -1;

void enqueue(int x) {
    if ((rear + 1) % MAX == front) {
        printf("Queue is Full\n");
        return;
    }

    if (front == -1) {
        front = 0;
    }

    rear = (rear + 1) % MAX;
    queue[rear] = x;

    printf("%d inserted into queue\n", x);
}

void dequeue() {
    if (front == -1) {
        printf("Queue is Empty\n");
        return;
    }

    printf("%d deleted from queue\n", queue[front]);

    if (front == rear) {
        front = rear = -1;
    } else {
        front = (front + 1) % MAX;
    }
}

void display() {
    if (front == -1) {
        printf("Queue is Empty\n");
        return;
    }

    printf("Queue elements: ");

    int i = front;
    while (1) {
        printf("%d ", queue[i]);

        if (i == rear)
            break;

        i = (i + 1) % MAX;
    }

    printf("\n");
}

void showFront() {
    if (front == -1) {
        printf("Queue is Empty\n");
    } else {
        printf("Front element = %d\n", queue[front]);
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);

    display();
    showFront();

    dequeue();
    dequeue();

    enqueue(50);
    enqueue(60);

    display();

    return 0;
}


Time Complexity:
- ENQUEUE = O(1)
- DEQUEUE = O(1)
- FRONT = O(1)
- DISPLAY = O(n)

Space Complexity:
- Circular Queue uses O(n) space.


COMPARISON WITH LINEAR QUEUE

1. Better Memory Utilization:
Circular Queue reuses the empty positions created after DEQUEUE. Therefore, memory is used efficiently.

2. Time Complexity:
ENQUEUE = O(1)
DEQUEUE = O(1)

3. Space Complexity:
O(n)

4. Problem in Linear Queue:
When REAR reaches the last index, insertion stops even if there are unused positions at the beginning of the queue. This causes memory wastage.

A Circular Queue solves this problem by connecting the last position back to the first position.
    enqueue(40);

    display();
    showFront();

    dequeue();
    dequeue();

    enqueue(50);
    enqueue(60);

    display();

    return 0;
}


Time Complexity:
- ENQUEUE = O(1)
- DEQUEUE = O(1)
- FRONT = O(1)
- DISPLAY = O(n)

Space Complexity:
- Circular Queue uses O(n) space.


COMPARISON WITH LINEAR QUEUE

1. Better Memory Utilization:
Circular Queue reuses the empty positions created after DEQUEUE. Therefore, memory is used efficiently.

2. Time Complexity:
ENQUEUE = O(1)
DEQUEUE = O(1)

3. Space Complexity:
O(n)

4. Problem in Linear Queue:
When REAR reaches the last index, insertion stops even if there are unused positions at the beginning of the queue. This causes memory wastage.

A Circular Queue solves this problem by connecting the last position back to the first position.
