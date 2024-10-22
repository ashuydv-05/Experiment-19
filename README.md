
# Experiment-19
c plus plus and data structures experiment 19

Aim:-to study and implement queue and its operations

Software used:- VS code

Theory:-
A queue is a linear data structure that follows the First In, First Out (FIFO) principle, meaning the first element added is the first one to be removed. It can be visualized as a line of people waiting for a service where the person at the front gets served first.

Basic Queue Operations:
Enqueue: Adds an element to the rear (end) of the queue.
Dequeue: Removes an element from the front of the queue.
Front (Peek): Retrieves the front element without removing it.
IsEmpty: Checks if the queue is empty.
IsFull: Checks if the queue is full (in case of a bounded queue).

CODE:-
```
//Ashu Yadav
//23070123154

#include <iostream>
using namespace std;

class Queue {
    int front, rear;
    int* arr;  
    int maxSize; 

public:
    Queue(int size) {
        maxSize = size;
        arr = new int[maxSize];  
        front = -1;
        rear = -1;
    }


    bool isFull() {
        return (rear == maxSize - 1);
    }

    bool isEmpty() {
        return (front == -1 || front > rear);
    }


    void push(int value) 
    {
        if (isFull()) 
        {
            cout << "Queue is full. Cannot push more elements.\n";
        } else 
        {
            if (front == -1) front = 0;  
            arr[++rear] = value;
            cout << "Pushed " << value << " into the queue.\n";
        }
    }

    void pop() 
    {
        if (isEmpty()) 
        {
            cout << "Queue is empty. Nothing to pop.\n";
        }
        else 
        {
            cout << "Popped " << arr[front] << " from the queue.\n";
            front++;
        }
    }

    void display()
    {
        if (isEmpty()) 
        {
            cout << "Queue is empty.\n";
        } else 
        {
            cout << "Queue elements are: ";
            for (int i = front; i <= rear; i++) 
            {
                cout << arr[i] << " ";
            }
            cout << endl;
        }
    }

    void peek() 
    {
        if (isEmpty()) 
        {
            cout << "Queue is empty.\n";
        } else 
        {
            cout << "Front element is: " << arr[front] << endl;
        }
    }

    ~Queue() {
        delete[] arr;
    }
};

int main() 
{
    int size, choice, value;

    cout << "Enter the size of the queue: ";
    cin >> size;

    Queue q(size);

    do {
        cout << "\nQueue Operations Menu:\n";
        cout << "1. Push\n";
        cout << "2. Pop\n";
        cout << "3. Display\n";
        cout << "4. Peek\n";
        cout << "5. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) 
        {
        case 1:
            cout << "Enter the value to push: ";
            cin >> value;
            q.push(value);
            break;
        case 2:
            q.pop();
            break;
        case 3:
            q.display();
            break;
        case 4:
            q.peek();
            break;
        case 5:
            cout << "Exiting...\n";
            break;
        default:
            cout << "Invalid choice. Please try again.\n";
        }
    } while (choice != 5);

    return 0;
}
```
![exp19](https://github.com/ashuydv-05/Experiment-19/blob/main/Screenshot%202024-10-22%20072049.png)

Conclusion:- In this experiment we learnt about queue and its operations.

