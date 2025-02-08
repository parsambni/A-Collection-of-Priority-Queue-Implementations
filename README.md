
# A Collection of Priority Queue Implementations

## Overview
This project demonstrates five distinct approaches to implementing a priority queue in C++ using fixed-size arrays. Each implementation varies in how elements are inserted, deleted, and managed internally. This collection is designed to illustrate various trade-offs between simplicity, efficiency, and space management, making it an excellent resource for understanding different algorithmic strategies.

## Implementations

1. **PriorityQueue_1**  
   - **Insertion:** Elements are inserted at the rear.
   - **Deletion:** The maximum element is identified by scanning the array, then removed by shifting subsequent elements left.
   - **Trade-Offs:** Simple and straightforward, but the shifting operation during deletion can be inefficient for large queues.

2. **PriorityQueue_2**  
   - **Insertion:** Elements are inserted into the first available slot, using a deletion marker (`-1`) to indicate removed elements.
   - **Deletion:** The maximum element is found among the non-deleted entries.
   - **Trade-Offs:** Reduces the need for shifting elements, though it requires scanning the array to locate empty slots and non-deleted elements.

3. **PriorityQueue_3**  
   - **Insertion:** Elements are inserted at the rear.
   - **Deletion:** The maximum element is marked as deleted (`-1`). When the array reaches full capacity, a compression routine is triggered to remove deleted elements and reclaim space.
   - **Trade-Offs:** Balances space management and deletion speed by periodically compressing the array, but adds extra complexity to the implementation.

4. **PriorityQueue_4**  
   - **Insertion:** Elements are inserted in sorted order, ensuring that the array remains ordered.
   - **Deletion:** The maximum element is always at the rear and can be removed immediately.
   - **Trade-Offs:** Deletion is very efficient, but insertion is slower because it requires shifting elements to maintain the sorted order.

5. **PriorityQueue_5**  
   - **Insertion:** Elements are inserted at the rear.
   - **Deletion:** The maximum element is identified and then replaced with the element at the rear, reducing the need for shifting.
   - **Trade-Offs:** Offers a compromise between speed and maintaining order, though the order of elements may be disturbed over time.

## Example Input & Output

The `main()` function in the code includes tests for each implementation. Here are some sample scenarios:

### Example 1: PriorityQueue_1
```cpp
PriorityQueue_1<int, 10> pq1;
pq1.insert(10);
pq1.insert(-3);
pq1.insert(-5);
pq1.insert(-2);
cout << "Max deleted from PQ1: " << pq1.maxDelete() << endl;
```
**Output:**
```
Max deleted from PQ1: 10
```

### Example 2: PriorityQueue_2
```cpp
PriorityQueue_2<int, 10> pq2;
pq2.insert(-5);
pq2.insert(-3);
pq2.insert(20);
pq2.insert(0);
cout << "Max deleted from PQ2: " << pq2.maxDelete() << endl;
```
**Output:**
```
Max deleted from PQ2: 20
```

### Example 3: PriorityQueue_3
```cpp
PriorityQueue_3<int, 10> pq3;
pq3.insert(5);
pq3.insert(3);
pq3.insert(30);
pq3.insert(2);
cout << "Max deleted from PQ3: " << pq3.maxDelete() << endl;
```
**Output:**
```
Max deleted from PQ3: 30
```

### Example 4: PriorityQueue_4
```cpp
PriorityQueue_4<int, 10> pq4;
pq4.insert(5);
pq4.insert(3);
pq4.insert(40);
pq4.insert(2);
cout << "Max deleted from PQ4: " << pq4.maxDelete() << endl;
```
**Output:**
```
Max deleted from PQ4: 40
```

### Example 5: PriorityQueue_5
```cpp
PriorityQueue_5<int, 10> pq5;
pq5.insert(5);
pq5.insert(3);
pq5.insert(50);
pq5.insert(2);
cout << "Max deleted from PQ5: " << pq5.maxDelete() << endl;
```
**Output:**
```
Max deleted from PQ5: 50
```

## Getting Started

### Prerequisites
- A C++ compiler that supports C++11 or later (e.g., GCC or MSVC).
- Standard C++ libraries (`<iostream>`, `<cstdlib>`) available on your system.

## Why This Project?
This collection of priority queue implementations serves as an educational tool to explore various techniques for implementing priority queues. By comparing these algorithms, you can understand:
- The trade-offs between simplicity and efficiency.
- How different approaches to insertion and deletion impact performance.
- Practical applications of array manipulation and algorithm design in C++.

## Contributions and Feedback
Your feedback is valuable! If you have suggestions for improvements or would like to contribute new features, please fork the repository and submit a pull request. Contributions are highly appreciated!

## License
This project is licensed under the MIT License.
