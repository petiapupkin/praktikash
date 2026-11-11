
#include <iostream>
#include <cstdlib>

using namespace std;

// Стек
struct Stack {
    int* data;
    int size;
};

void push(Stack& stack, int value) {
    int* newData = new int[stack.size + 1];

    for (int i = 0; i < stack.size; i++)
        newData[i] = stack.data[i];

    newData[stack.size] = value;

    delete[] stack.data;
    stack.data = newData;
    stack.size++;
}

int pop(Stack& stack) {
    if (stack.size == 0)
        return 1;

    int* newData = new int[stack.size - 1];

    for (int i = 0; i < stack.size - 1; i++)
        newData[i] = stack.data[i];

    delete[] stack.data;
    stack.data = newData;
    stack.size--;

    return 0;
}

int peekStack(Stack& stack, int& value) {
    if (stack.size == 0)
        return 1;

    value = stack.data[stack.size - 1];
    return 0;
}

// Очередь
struct Queue {
    int* data;
    int size;
};

void enqueue(Queue& queue, int value) {
    int* newData = new int[queue.size + 1];

    for (int i = 0; i < queue.size; i++)
        newData[i] = queue.data[i];

    newData[queue.size] = value;

    delete[] queue.data;
    queue.data = newData;
    queue.size++;
}

int dequeue(Queue& queue) {
    if (queue.size == 0)
        return 1;

    int* newData = new int[queue.size - 1];

    for (int i = 0; i < queue.size - 1; i++)
        newData[i] = queue.data[i + 1];

    delete[] queue.data;
    queue.data = newData;
    queue.size--;

    return 0;
}

int peekQueue(Queue& queue, int& value) {
    if (queue.size == 0)
        return 1;

    value = queue.data[0];
    return 0;
}

int main(int argc, char* argv[]) {
    Stack stack = { nullptr, 0 };
    Queue queue = { nullptr, 0 };

    if (argc < 2) {
        cout << "No arguments!" << endl;
        return 1;
    }

    for (int i = 1; i < argc; i++) {
        int value = atoi(argv[i]);

        push(stack, value);
        enqueue(queue, value);
    }

    cout << "Direct order: ";

    while (queue.size > 0) {
        int value;
        peekQueue(queue, value);
        cout << value << " ";
        dequeue(queue);
    }

    cout << endl;

    cout << "Reverse order: ";

    while (stack.size > 0) {
        int value;
        peekStack(stack, value);
        cout << value << " ";
        pop(stack);
    }

    cout << endl;

    delete[] stack.data;
    delete[] queue.data;

    return 0;
}
