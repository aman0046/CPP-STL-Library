# C---STL-Library


# VECTOR IN C++

A **vector** is a dynamic array whose size can be changed automatically when an element is inserted or deleted. Vector elements are stored in contiguous memory locations so that they can be accessed in constant time.

It is defined inside the `<vector>` header file (also available in `<bits/stdc++.h>`).

The complexity (efficiency) of common operations on vectors is as follows:

- Random access - constant 𝓞(1).
- Insertion or removal of elements at the end - amortized constant 𝓞(1).
- Insertion or removal of elements in front or middle of the vector 𝓞(n).

## Ways to declare a vector

### Syntax

- `vector<int> vec;` *Empty*
- `vector<int> vec( size );` *Vector with size 'size'*
- `vector<int> vec( size, value );` *Vector with size 'size' and all elements with value 'value'*
- `vector<int> vec = { value1, value2, value3,...,valueN};` *Vector with N values*

### Examples

```cpp
vector<int> vec; // Declares an empty vector with name as vec ---> []
vector<int> vec(5); // Declares vector of ints with size 5 and the default values assigned are 0s ---> [0,0,0,0,0]
vector<int> vec(5, 10); // Declares vector of ints with size 5 and values assigned are 10s ---> [10,10,10,10,10]
vector<int> vec = {1, 2, 3, 4}; // Declares vector with size 4 and values as ---> [1, 2, 3, 4]
vector<string> vect(5) ; // Declares vector with 5 empty strings ---> ["", "", "", "", ""]
vector<string> vec(5, "Leetcode"); // Declares vector of strings with size 5 and values initialised are "Leetcode" ---> ["Leetcode", "Leetcode", "Leetcode", "Leetcode", "Leetcode"]
vector<vector<int>> vec(5);  // Declares vector of vectors ---> [[], [], [], [], []]
vector<vector<int>> vec(5, vector<int>(2)); // Declares vector of vectors(here inside vector size is 2 and default values assigned are 0's) ---> [[0,0], [0,0], [0,0], [0,0], [0,0]]
vector<vector<int>> vec(5, vector<int>(2, 10)); // Declares vector of vectors(here inside vector size is 2 and default values assigned are 10's) ---> [[10,10], [10,10],[10,10],[10,10],[10,10]]

```


# Ways to Insert Elements into Vector

## Syntax

- `vec.push_back( ele );` Adds an element 'ele' at the end, and size of the vector increases by 1 (TC - 𝓞(1))
- `vec.emplace_back( ele );` Adds an element 'ele' at the end, and size of the vector increases by 1 (TC - 𝓞(1))
- `vec.insert( vec.begin() + i, ele );` Inserting element 'ele' at index i | Use i = 0 for inserting at the front (TC - 𝓞(n))
- `vec.insert( vec.end(), vec2.begin(), vec2.end() );` Inserting the elements of vector 'v2' to the end of vector 'v' (TC - 𝓞(n))

# Ways to Delete Elements from Vector

## Syntax

- `v.pop_back();` Remove element at the end (TC - 𝓞(1))
- `v.erase( v.begin() + i );` Remove element at index i or i = 0 to remove the first element (TC - 𝓞(n))
- `v.erase( v.begin() + i, v.begin() + j );` Remove elements from index i to j-1 (TC - 𝓞(n))
- `v.erase( remove( v.begin(), v.end(), value ), v.end() );` Removes all elements with value 'value' from the vector (TC - 𝓞(n))

# Basic Inbuilt Functions

## Syntax

- `v.size();` Returns the size of vector (TC - 𝓞(1))
- `v.resize( size, val );` If the 'size' is greater than the previous size, then it adds elements with value 'val' at end and if 'size' is less than previous, then it removes from end
- `v.empty();` Returns true if the vector is empty (TC - 𝓞(1))
- `v.front();` or `v[0];` Accessing the first element (TC - 𝓞(1))
- `v.back();` or `v[v.size()-1];` Accessing the last element (TC - 𝓞(1))
- `v[i];` Accessing element at i'th index (0-based) (TC - 𝓞(1))
- `v.at(i);` Accessing element at i'th index (0-based) (TC - 𝓞(1))
- `v.clear();` Clears vector elements by making vector as empty (TC - 𝓞(n))

# Some Algorithmic Based Functions

- `sort(v.begin(), v.end());` Sorts vector elements in ascending order by default (TC - 𝓞(nlogn))
- `sort(v.begin(), v.end(), greater<int>);` Sorts vector elements in descending order (TC - 𝓞(nlogn))
- `reverse(v.begin(), v.end());` Reverses vector elements (TC - 𝓞(n))
- `count(v.begin(), v.end(), x);` Returns the count of x in vector (TC - 𝓞(n))
- `min_element(v.begin(), v.end()) - v.begin();` Returns the minimum element's index (0-based) from the vector (TC - 𝓞(n))
- `max_element(v.begin(), v.end()) - v.begin();` Returns the maximum element's index (0-based) from the vector (TC - 𝓞(n))
- `*min_element(v.begin(), v.end());` Returns the minimum element from the vector (TC - 𝓞(n))
- `*max_element(v.begin(), v.end());` Returns the maximum element from the vector (TC - 𝓞(n))

*Note: The difference between `v[i]` and `v.at(i)` is that 'at' will raise an exception if you try to access an element outside the vector while the `[]` operator won't.*



*Lets undertand by sample program*

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    vector<int> v = {1, 3, 2}; // Create a vector containing integers ---> [1, 3, 2]

    // Insertion
    v.push_back(5); // Adding 5 at the end ---> [1, 3, 2, 5]
    v.emplace_back(4); // Adding 4 at the end ---> [1, 3, 2, 5, 4]
    v.insert(v.begin(), 10); // Inserts 10 at the beginning ---> [10, 1, 3, 2, 5, 4]
    v.insert(v.begin() + 3, 15); // Inserts 15 at 3rd index ---> [10, 1, 3, 15, 2, 5, 4]

    // Deletion
    v.pop_back(); // Removes an element at the end ---> [10, 1, 3, 15, 2, 5]
    v.erase(v.begin()); // Removes an element at the front ---> [1, 3, 15, 2, 5]
    v.erase(v.begin() + 3); // Removes an element at 3rd index ---> [1, 3, 15, 5]

    // Accessing and Updating
    int a = v[3]; // Here the variable a stores the value at 3rd index i.e., 5
    v[1] = 100; // Here the value at index 1 is updated with 100 ---> [1, 100, 15, 5]
    int last_element = v.back(); // i.e., 5
    int first_element = v.front(); // i.e., 1

    sort(v.begin(), v.end()); // Sorts vector elements ---> [1, 5, 15, 100]
    reverse(v.begin(), v.end()); // Reverses vector elements ---> [100, 15, 5, 1]

    // Traversing the vector using a for loop
    for (int i = 0; i < v.size(); i++) {
        cout << v[i] << " "; // After the for loop, Output is: 100 15 5 1
    }
    int length = v.size(); // Here the variable length stores the vector size i.e., 4
    v.clear(); // Vector is cleared ---> []
    bool isVectorEmpty = v.empty(); // Here the variable isVectorEmpty stores 'true' as the vector is empty

    return 0;
}


```


# STACK IN C++

A stack is a linear data structure that follows the principle of Last In First Out (LIFO). This means the last element inserted inside the stack is removed first. It is defined inside `<stack>` header file (also available in `<bits/stdc++.h>`).

## Declaring a Stack

### Syntax
```cpp
stack< data_type > stack_name;
```

## Examples

- `stack<int> stk;` // stack of int's
- `stack<string> stk;` // stack of strings
- `stack<pair<int, int>> stk;` // stack of pairs
- `stack<vector<int>> stck;` // stack of vectors

*Note: Similar syntax for `char`, `long long int`, `float`, `double`, `long double`, and some other data types, including user-defined data types.*

## Important Functions on Stack

- `stk.push(ele);` // pushes an element 'ele' into the stack      TC - 𝓞(1)
- `stk.pop();` // removes the top element      TC - 𝓞(1)
- `stk.top();` // returns the topmost element      TC - 𝓞(1)
- `stk.size();` // returns the size of stack      TC - 𝓞(1)
- `stk.empty();` // returns true if the stack is empty else false      TC - 𝓞(1)

*Note: The time complexity of all above inbuilt functions is constant - 𝓞(1)*

## Accessing Stack Elements

Since it won't provide indexing, we cannot directly access any element except the top element. The below is the way to traverse the stack.
```cpp
while(!stk.empty()){
    cout << stk.top() << " ";
    stk.pop();
}
```

Lets understand by sample program

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
	stack<string> stk;
	
	//pushing data into the stack
	stk.push("Hi");
	stk.push("Hello");
	stk.push("How are you?");
	
	//poping data from top of the stack
	stk.pop(); // the top element i.e "How are you?" is removed;
	
	cout << stk.top() << " "; // prints top element "Hello"
	cout << stk.size() << " "; // prints 2
	cout << stk.empty(); //prints false | 0
	
	return 0;
}
```


# QUEUE IN C++

A queue is a linear data structure that follows the FIFO (First In First Out) principle, i.e., elements that are added first will be removed first. It is defined inside `<queue>` header file (also available in `<bits/stdc++.h>`).


## Declaring a Queue

### Syntax
```cpp
queue< data_type > queue_name;
```

# Examples

- `queue<int> q;` // queue of int's
- `queue<string> q;` // queue of strings
- `queue<pair<int, int>> q;` // queue of pairs
- `queue<vector<int>> q;` // queue of vectors

*Note: Similar syntax for `char`, `long long int`, `float`, `double`, `long double`, and some other data types, including user-defined data types.*

# Important Functions on Queue

- `q.push(ele);` // pushes an element 'ele' into the queue from the end      TC - 𝓞(1)
- `q.pop();` // removes an element from the front of the queue      TC - 𝓞(1)
- `q.front();` // returns the first element      TC - 𝓞(1)
- `q.back();` // returns the last element      TC - 𝓞(1)
- `q.size();` // returns the size of the queue      TC - 𝓞(1)
- `q.empty();` // returns true if the queue is empty else false      TC - 𝓞(1)

*Note: The time complexity of all above inbuilt functions is constant - 𝓞(1)*

# Accessing Queue Elements

Since it won't provide indexing, we cannot directly access any element except the first and last element. The below is the way to traverse the queue.

```cpp
while(!q.empty()){
    cout << q.front() << " ";
    q.pop();
}
```

Let's understand with a sample program

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    
    queue<string> q;
    
    // Pushing data into the queue
    q.push("Hi");
    q.push("Hello");
    q.push("How are you?");
    
    // Popping data from the top of the queue
    q.pop(); // The front element, i.e., "Hi", is removed;
    
    cout << q.front() << " "; // Prints the front element, "Hello"
    cout << q.back() << " "; // Prints the back element, "How are you?"
    cout << q.size() << " "; // Prints 2
    cout << q.empty(); // Prints false | 0
    
    return 0;
}
```

# DEQUE IN C++

Deque is an indexed sequence container that allows fast insertion and deletion at both its beginning and its end.

The complexity (efficiency) of common operations on deques is as follows:
- Random access - constant 𝓞(1)
- Insertion or removal of elements at the end or beginning - constant 𝓞(1)
- Insertion or removal of elements - linear 𝓞(n)

Formally, a deque supports all the functions that a vector supports. The difference between a deque and a vector is that deques do not guarantee that their elements are contiguous in memory, so accessing may not be as efficient.

## Ways to Declare a Deque
### Syntax
```cpp
deque<int> dq; /* Empty */
deque<int> dq( size ); /* Deque with size 'size' */
deque<int> dq( size, value ); /* Deque with size 'size' and all elements with value 'value' */
deque<int> dq = { value1, value2, value3,...,valueN}; /* Deque with N values */
```

*Note: Similar syntax for char, long long int, float, double, long double, and some other data types include user-defined data types.*

## Important Functions

- `dq.push_back( ele );` Adds an element 'ele' at the end, and the size of the deque increases by 1 (TC - 𝓞(1))
- `dq.pop_back();` Removes an element at the end (TC - 𝓞(1))
- `dq.push_front( ele );` Adds an element 'ele' at the front, and the size of the deque increases by 1 (TC - 𝓞(1))
- `dq.pop_front();` Removes an element at the front (TC - 𝓞(1))
- `dq.size();` Returns the size of the deque (TC - 𝓞(1))
- `dq.empty();` Returns true if the deque is empty, else false (TC - 𝓞(1))
- `dq.front();` or `dq[0];` Accesses the first element (TC - 𝓞(1))
- `dq.back();` or `dq[dq.size()-1];` Accesses the last element (TC - 𝓞(1))
- `dq[i];` Accesses the element at the i'th index (0-based) (TC - 𝓞(1))
- `dq.at(i);` Accesses the element at the i'th index (0-based) (TC - 𝓞(1))



# PRIORITY QUEUE IN C++

A priority queue is a special type of queue in which each element is associated with a priority value, and elements are served based on their priority.
It is defined inside the `<queue>` header file (also available in `<bits/stdc++.h>`).
By default, C++ creates a max priority queue. We can change it to a min priority queue by passing additional parameters during declaration.


## Syntax

### Max - Priority Queue
```cpp
priority_queue< data_type > priority_queue_name;
```

### Max - Priority Queue
```cpp
priority_queue< data_type, vector< data_type >, greater< data_type > > priority_queue_name;
```

# Examples

## Max Priority Queue
```cpp
priority_queue<int> q; // max priority_queue of int's
priority_queue<string> q; // max priority_queue of strings
priority_queue<pair<int, int>> q; // max priority_queue of pairs
priority_queue<vector<int>> q; // max priority_queue of vectors
```

## Min Priority Queue
```cpp
priority_queue<int, vector<int>, greater<int>> q; // min priority_queue of int's
priority_queue<string, vector<string>, greater<string>> q; // min priority_queue of strings
priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> q; // min priority_queue of pairs
priority_queue<vector<int>, vector<vector<int>>, greater<vector<int>>> q; // min priority_queue of vectors
```

Note: Similar syntax for char, long long int, float, double, long double, and some other data types include user-defined data types.

## Important functions on priority_queue

### `pq.push(ele);`
- Inserts the element 'ele' into the priority queue.
- Time Complexity: 𝓞(logn)

### `pq.pop();`
- Removes the element with the highest priority.
- Time Complexity: 𝓞(logn)

### `pq.top();`
- Returns the element with the highest priority.
- Time Complexity: 𝓞(1)

### `pq.size();`
- Returns the size of the priority_queue.
- Time Complexity: 𝓞(1)

### `pq.empty();`
- Returns true if the priority_queue is empty, else false.
- Time Complexity: 𝓞(1)

## Accessing priority_queue elements

Since it won't provide indexing, we cannot directly access any element except the top element. The below is the way to traverse the priority_queue.

```cpp
while (!pq.empty()) {
    cout << pq.top() << " ";
    pq.pop();
}
```

Priority Queue Sample Program

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    priority_queue<int> pq;

    // Pushing data into the priority_queue
    pq.push(6);
    pq.push(10);
    pq.push(0);
    pq.push(-40);
    pq.push(8);
    pq.push(-20);
    pq.push(3);

    cout << pq.top() << " "; // Prints the top element, i.e., 10

    // Popping data from the top of the queue
    pq.pop(); // The top element, i.e., 10, is removed;

    cout << pq.top() << " "; // Prints the current top element, i.e., 8
    cout << pq.size() << " "; // Prints 6
    cout << pq.empty(); // Prints false | 0

    return 0;
}
```

