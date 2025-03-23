# BinaryMinHeap Header File Documentation

## Overview
This header file defines the `BinaryMinHeap` class, which implements a binary min-heap data structure. The class provides various methods to manipulate the heap, including insertion, extraction, and updating elements.

## Class Methods

### Constructors and Destructor
- **BinaryMinHeap()**: Default constructor.
- **~BinaryMinHeap()**: Destructor.
- **BinaryMinHeap(const BinaryMinHeap& other)**: Copy constructor.
- **BinaryMinHeap& operator=(const BinaryMinHeap& other)**: Assignment operator.

### Operators
- **BinaryMinHeap& operator!()**: Clears the heap.
- **BinaryMinHeap& operator+=(int value)**: Inserts an element into the heap.

### Public Methods
- **void insert(int value)**: Inserts an element into the heap.
- **int extractMin()**: Removes and returns the minimum element from the heap.
- **int getMin() const**: Returns the minimum element without removing it.
- **void remove(int pos)**: Removes the element at the specified position.
- **void update(int pos, int value)**: Updates the element at the specified position with a new value.
- **void clear()**: Clears all elements from the heap.
- **bool isEmpty()**: Checks if the heap is empty.
- **std::string toString()**: Returns a string representation of the heap elements.
- **static int getObjCount()**: Returns the count of created `BinaryMinHeap` objects.

## Usage
To use the `BinaryMinHeap` class, include the header file in your project and create an instance of the class. You can then use the provided methods to manipulate the heap as needed.
