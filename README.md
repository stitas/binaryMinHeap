markdown
Copy code
# BinaryMinHeap Header File

A header file that defines the `BinaryMinHeap` class for implementing a **binary min-heap** data structure, which is useful for efficient retrieval and removal of the smallest element.

This class provides various functionalities such as inserting elements, extracting the minimum, and removing specific elements from the heap.

## Table of Contents

- [Overview](#overview)
- [Class Declaration](#class-declaration)
- [Constructors](#constructors)
- [Operators](#operators)
- [Heap Methods](#heap-methods)
- [Exception Handling](#exception-handling)
- [Static Methods](#static-methods)
- [Example Usage](#example-usage)

## Overview

A **binary min-heap** is a complete binary tree where each parent node is smaller than its child nodes. This property ensures that the smallest element can always be accessed in constant time, making it ideal for applications like priority queues.

This class encapsulates the heap operations with a private implementation to provide a clean and manageable interface.

---

## Class Declaration

The `BinaryMinHeap` class is defined inside the `heap` namespace and is composed of the following methods:

### Constructors

- `BinaryMinHeap()`  
  Default constructor for initializing the heap.

- `BinaryMinHeap(const BinaryMinHeap& other)`  
  Copy constructor for copying an existing heap.

- `BinaryMinHeap& operator=(const BinaryMinHeap& other)`  
  Assignment operator for copying data from another heap.

- `~BinaryMinHeap()`  
  Destructor to properly release any allocated resources.

### Operators

- `BinaryMinHeap& operator!()`  
  Clears the heap by removing all elements.

- `int operator[](int value)`  
  Returns the count of occurrences of a given value in the heap.

- `BinaryMinHeap& operator+=(int value)`  
  Inserts an element into the heap.

- `BinaryMinHeap& operator-=(int value)`  
  Removes the first occurrence of a given element from the heap.

### Heap Methods

- `void insert(int value)`  
  Inserts an element into the heap while maintaining the heap property.

- `int extractMin()`  
  Extracts and returns the smallest element from the heap.

- `int getMin() const`  
  Returns the smallest element without removing it.

- `bool remove(int value)`  
  Removes the first occurrence of a specified value from the heap.

- `void removeAll(int value)`  
  Removes all occurrences of a specified value from the heap.

- `void clear()`  
  Clears all elements in the heap.

- `bool isEmpty()`  
  Checks if the heap is empty.

- `std::string toString()`  
  Returns a string representation of the heap elements.

### Static Methods

- `static int getObjCount()`  
  Returns the number of `BinaryMinHeap` objects that have been created.

### Exception Handling

- `class HeapException`  
  Custom exception class for throwing errors related to heap operations.

  - `HeapException(const std::string& msg)`  
    Constructor that accepts a message for the exception.

  - `const char* what() const noexcept override`  
    Provides the exception message when caught.

---

## Example Usage

```cpp
#include "binary_min_heap.h"
#include <iostream>

int main() {
	try {
		// Create heap via default constructor
		heap::BinaryMinHeap* bmh1 = new heap::BinaryMinHeap();
		
		// Create heap via copy constructor
		heap::BinaryMinHeap* bmh2 = new heap::BinaryMinHeap(*bmh1);

		// Create heap equal sign constructor
		heap::BinaryMinHeap bmh3;
		bmh3 = *bmh2;

		// Insert value to the heap
		bmh1->insert(9);
		bmh1->insert(8);
		bmh1->insert(7);
		bmh1->insert(6);
		bmh1->insert(5);

		// Insert value to the heap
		*bmh2 += 1;
		*bmh2 += 2;
		*bmh2 += 3;
		*bmh2 += 4;

		// Insert value to the heap
		bmh3 += 100;
		bmh3 += 200;
		bmh3.insert(300);
		bmh3.insert(400);

		// Get the min value and remove from heap
		int extractedMin = bmh1->extractMin();

		// Get the min value (value does not get removed)
		int gottenMin = bmh1->getMin();

		// Remove element from heap with value 2 and 7
		bmh1->remove(2);
		*bmh1 -= 7;

		// Clear the heap.
		bmh1->clear();
		
		// Clear the heap
		!(*bmh2);

		// Check if heap is empty
		bmh1->isEmpty();
		bmh2->isEmpty();

		// Get current object count
		heap::BinaryMinHeap::getObjCount();

		delete bmh1;
		delete bmh2;
	}
	catch (const heap::BinaryMinHeap::HeapException& e){
		std::cout << e.what();
	}

	return 0;
}