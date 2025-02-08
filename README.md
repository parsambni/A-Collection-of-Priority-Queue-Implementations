# Priority Queue Implementations

## Overview
This project contains five different implementations of a priority queue using C++. Each implementation varies in how elements are inserted, deleted, and managed internally.

## Implementations
1. **PriorityQueue_1**:
   - Insert at the rear.
   - Delete the maximum element by shifting remaining elements.
   - Simple and efficient for small data sizes but has a costly deletion operation.

2. **PriorityQueue_2**:
   - Insert at the first available slot.
   - Delete the maximum element using a deletion marker (-1).
   - Reduces shifting but requires checking for available slots frequently.

3. **PriorityQueue_3**:
   - Insert at the rear.
   - Delete the maximum element with a deletion marker (-1).
   - Compress the array when it reaches full capacity.
   - Balances space efficiency and deletion speed.

4. **PriorityQueue_4**:
   - Insert elements in sorted order.
   - Delete from the rear (largest element).
   - Ensures sorted elements at the cost of shifting on every insertion.

5. **PriorityQueue_5**:
   - Insert at the rear.
   - Delete the maximum element by replacing it with the last element.
   - Reduces shifting but may affect element ordering over time.

## Example Input & Output
### Input:
```cpp
PriorityQueue_1<int, 10> pq1;
pq1.insert(10);
pq1.insert(-3);
pq1.insert(-5);
pq1.insert(-2);
std::cout << "Max deleted from PQ1: " << pq1.maxDelete() << std::endl;
```

### Output:
```
Max deleted from PQ1: 10
```

### Another Example:
```cpp
PriorityQueue_2<int, 10> pq2;
pq2.insert(-5);
pq2.insert(-3);
pq2.insert(20);
pq2.insert(0);
std::cout << "Max deleted from PQ2: " << pq2.maxDelete() << std::endl;
```

### Output:
```
Max deleted from PQ2: 20
```

## Requirements
- C++ compiler (G++ or MSVC)
- Any operating system that supports C++

## License
This project is licensed under the MIT License.

