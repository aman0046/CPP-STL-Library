# C\+\+ STL-Library 📚📚

In C++, the Standard Template Library (STL) provides a set of programming tools to implement algorithms and data structures like vectors, lists, queues, etc. This repository contains entire C++ STL Library which anyone require while doing Competitive Programming, Contest solving or in Online Assessment. 

---

###

#### Join us for all the latest offcampus job updates, webinar, hackathons, resume review and a lot more :heart::heart:

<div align="left">
  <a href="https://www.linkedin.com/in/amanchowdhury046/" target="_blank">
    <img src="https://img.shields.io/static/v1?message=LinkedIn&logo=linkedin&label=&color=0077B5&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="linkedin logo"  />
  </a>
  <a href="https://www.youtube.com/@amanchowdhury046" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Youtube&logo=youtube&label=&color=FF0000&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="youtube logo"  />
  </a>
  <a href="https://telegram.me/offcampus_phodenge" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Telegram&logo=telegram&label=&color=2CA5E0&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="telegram logo"  />
  </a>
  <a href="https://www.instagram.com/aman_chowdhury_046/" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Instagram&logo=instagram&label=&color=E4405F&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="instagram logo"  />
  </a>
  <a href="https://whatsapp.com/channel/0029Va9Q0lkDZ4LYNx6ukw2u" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Whatsapp&logo=Whatsapp&label=&color=25D366&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="whatsapp logo"  />
  </a>
</div>

###

---

## 🚀 Table of Contents

- [Vector In C++](#vector-in-c)
- [Stack In C++](#stack-in-c)
- [Queue In C++](#queue-in-c)
- [Deque In C++](#deque-in-c)
- [Priotity Queue In C++](#priority-queue-in-c)
- [Set In C++](#set-in-c)
- [Unordered Set In C++](#unordered-set-in-c)
- [Multiset In C++](#multiset-in-c)
- [Unordered Multiset In C++](#unordered-multiset-in-c)
- [Map In C++](#maps-in-c)
- [Unordered Map In C++](#unordered-maps-in-c)
- [MultiMap In C++](#multimaps-in-c)
- [Unordered MultiMap In C++](#unordered-multimaps-in-c)

---

<img src="/assets/images/CPPSTL.png" width="400" height="200">

---

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


## Ways to Insert Elements into Vector

### Syntax

- `vec.push_back( ele );` Adds an element 'ele' at the end, and size of the vector increases by 1 (TC - 𝓞(1))
- `vec.emplace_back( ele );` Adds an element 'ele' at the end, and size of the vector increases by 1 (TC - 𝓞(1))
- `vec.insert( vec.begin() + i, ele );` Inserting element 'ele' at index i | Use i = 0 for inserting at the front (TC - 𝓞(n))
- `vec.insert( vec.end(), vec2.begin(), vec2.end() );` Inserting the elements of vector 'v2' to the end of vector 'v' (TC - 𝓞(n))

## Ways to Delete Elements from Vector

### Syntax

- `v.pop_back();` Remove element at the end (TC - 𝓞(1))
- `v.erase( v.begin() + i );` Remove element at index i or i = 0 to remove the first element (TC - 𝓞(n))
- `v.erase( v.begin() + i, v.begin() + j );` Remove elements from index i to j-1 (TC - 𝓞(n))
- `v.erase( remove( v.begin(), v.end(), value ), v.end() );` Removes all elements with value 'value' from the vector (TC - 𝓞(n))

## Basic Inbuilt Functions

### Syntax

- `v.size();` Returns the size of vector (TC - 𝓞(1))
- `v.resize( size, val );` If the 'size' is greater than the previous size, then it adds elements with value 'val' at end and if 'size' is less than previous, then it removes from end
- `v.empty();` Returns true if the vector is empty (TC - 𝓞(1))
- `v.front();` or `v[0];` Accessing the first element (TC - 𝓞(1))
- `v.back();` or `v[v.size()-1];` Accessing the last element (TC - 𝓞(1))
- `v[i];` Accessing element at i'th index (0-based) (TC - 𝓞(1))
- `v.at(i);` Accessing element at i'th index (0-based) (TC - 𝓞(1))
- `v.clear();` Clears vector elements by making vector as empty (TC - 𝓞(n))

## Some Algorithmic Based Functions

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

---

# STACK IN C++

- A stack is a linear data structure that follows the principle of `Last In First Out (LIFO)`. This means the last element inserted inside the stack is removed first.
- It is defined inside `<stack>` header file (also available in `<bits/stdc++.h>`).

## Declaring a Stack

### Syntax
```cpp
stack< data_type > stack_name;
```

### Examples

- `stack<int> stk;` stack of int's
- `stack<string> stk;` stack of strings
- `stack<pair<int, int>> stk;` stack of pairs
- `stack<vector<int>> stck;` stack of vectors

*Note: Similar syntax for `char`, `long long int`, `float`, `double`, `long double`, and some other data types, including user-defined data types.*

## Important Functions on Stack

- `stk.push(ele);` pushes an element 'ele' into the stack      TC - 𝓞(1)
- `stk.pop();` removes the top element      TC - 𝓞(1)
- `stk.top();` returns the topmost element      TC - 𝓞(1)
- `stk.size();` returns the size of stack      TC - 𝓞(1)
- `stk.empty();` returns true if the stack is empty else false      TC - 𝓞(1)

*Note: The time complexity of all above inbuilt functions is constant - 𝓞(1)*

## Accessing Stack Elements

Since it won't provide indexing, *we cannot directly access any element except the top element.* The below is the way to traverse the stack.
```cpp
while(!stk.empty()){
    cout << stk.top() << " ";
    stk.pop();
}
```

*Lets understand by sample program*

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

---

# QUEUE IN C++

- A queue is a linear data structure that follows the `FIFO (First In First Out)` principle, i.e., elements that are added first will be removed first.
- It is defined inside `<queue>` header file (also available in `<bits/stdc++.h>`).


## Declaring a Queue

### Syntax
```cpp
queue< data_type > queue_name;
```

### Examples

- `queue<int> q;` queue of int's
- `queue<string> q;` queue of strings
- `queue<pair<int, int>> q;` queue of pairs
- `queue<vector<int>> q;` queue of vectors

*Note: Similar syntax for `char`, `long long int`, `float`, `double`, `long double`, and some other data types, including user-defined data types.*

## Important Functions on Queue

- `q.push(ele);` pushes an element 'ele' into the queue from the end      TC - 𝓞(1)
- `q.pop();` removes an element from the front of the queue      TC - 𝓞(1)
- `q.front();` returns the first element      TC - 𝓞(1)
- `q.back();` returns the last element      TC - 𝓞(1)
- `q.size();` returns the size of the queue      TC - 𝓞(1)
- `q.empty();` returns true if the queue is empty else false      TC - 𝓞(1)

*Note: The time complexity of all above inbuilt functions is constant - 𝓞(1)*

## Accessing Queue Elements

Since it won't provide indexing, we cannot directly access any element except the first and last element. The below is the way to traverse the queue.

```cpp
while(!q.empty()){
    cout << q.front() << " ";
    q.pop();
}
```

*Let's understand with a sample program*

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

---

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
deque< data_type > deque_name;
```

### Examples
- `deque<int> dq;` Deque of int (Empty) 
- `deque<int> dq( size );`  Deque with size 'size' 
- `deque<int> dq( size, value );`  Deque with size 'size' and all elements with value 'value' 
- `deque<int> dq = { value1, value2, value3,...,valueN};` Deque with N values 


*Note: Similar syntax for `char`, `long long int`, `float`, `double`, `long double`, and some other data types, including user-defined data types.*

## Important Functions

- `dq.push_back( ele );` Adds an element 'ele' at the end (TC - 𝓞(1))
- `dq.pop_back();` Removes an element at the end (TC - 𝓞(1))
- `dq.push_front( ele );` Adds an element 'ele' at the front (TC - 𝓞(1))
- `dq.pop_front();` Removes an element at the front (TC - 𝓞(1))
- `dq.size();` Returns the size of the deque (TC - 𝓞(1))
- `dq.empty();` Returns true if the deque is empty, else false (TC - 𝓞(1))
- `dq.front();` or `dq[0];` Accesses the first element (TC - 𝓞(1))
- `dq.back();` or `dq[dq.size()-1];` Accesses the last element (TC - 𝓞(1))
- `dq[i];` Accesses the element at the i'th index (0-based) (TC - 𝓞(1))
- `dq.at(i);` Accesses the element at the i'th index (0-based) (TC - 𝓞(1))


---

# PRIORITY QUEUE IN C++

- A priority queue is a special type of queue in which each element is associated with a priority value, and elements are served based on their priority.
- It is defined inside the `<queue>` header file (also available in `<bits/stdc++.h>`).
- By default, C++ creates a max priority queue. We can change it to a min priority queue by passing additional parameters during declaration.


## Syntax

### Max - Priority Queue
```cpp
priority_queue< data_type > priority_queue_name;
```

### Max - Priority Queue
```cpp
priority_queue< data_type, vector< data_type >, greater< data_type > > priority_queue_name;
```

## Examples

### Max Priority Queue
```cpp
priority_queue<int> q; // max priority_queue of int's
priority_queue<string> q; // max priority_queue of strings
priority_queue<pair<int, int>> q; // max priority_queue of pairs
priority_queue<vector<int>> q; // max priority_queue of vectors
```

### Min Priority Queue
```cpp
priority_queue<int, vector<int>, greater<int>> q; // min priority_queue of int's
priority_queue<string, vector<string>, greater<string>> q; // min priority_queue of strings
priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> q; // min priority_queue of pairs
priority_queue<vector<int>, vector<vector<int>>, greater<vector<int>>> q; // min priority_queue of vectors
```

*Note: Similar syntax for `char`, `long long int`, `float`, `double`, `long double`, and some other data types, including user-defined data types.*

## Important functions on priority_queue

- `pq.push(ele);` Inserts the element 'ele' into the priority queue. [Time Complexity: 𝓞(logn)]
- `pq.pop();` Removes the element with the highest priority. [Time Complexity: 𝓞(logn)]
- `pq.top();` Returns the element with the highest priority. [Time Complexity: 𝓞(1)]
- `pq.size();` Returns the size of the priority_queue. [Time Complexity: 𝓞(1)]
- `pq.empty();` Returns true if the priority_queue is empty, else false. [Time Complexity: 𝓞(1)]

## Accessing priority_queue elements

Since it won't provide indexing, we cannot directly access any element except the top element. The below is the way to traverse the priority_queue.

```cpp
while (!pq.empty()) {
    cout << pq.top() << " ";
    pq.pop();
}
```

*Lets understand by sample program*

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

---

# SET IN C++

- A set data structure `won't allow duplicate keys`.
- Keys are sorted in ascending order by default. We can also change the order by passing extra arguments during its declaration.
- Implemented using `Binary search tree` (Red-Black trees).

## Declaring set

### Syntax
```cpp
set< data_type > st; stores keys in ascending order
set< data_type, greater< data_type > > st; stores keys in descending order
```

### Examples

- `set<int> st;` set of int's
- `set<string> st;` set of strings
- `set<pair<int, int>> st;` set of pairs
- `set<vector<int>> st;` set of vectors


*Note: Similar syntax for `char`, `long long int`, `float`, `double`, `long double`, and some other data types, including user-defined data types.*

## Important functions on set

- `st.insert( key );` Inserts the element into the set (if not present). TC - 𝓞(logn)
- `st.erase( key );` Removes the specified key if present. TC - 𝓞(logn)
- `st.find( key );` Returns an iterator pointing to the key; if the key is not present, returns st.end(). TC - 𝓞(logn)
- `st.size();` Returns the size of the set. TC - 𝓞(1)
- `st.empty();` Returns true if the set is empty, else false. TC - 𝓞(1)
- `st.clear();` Removes all set elements. TC - 𝓞(n)

## Accessing set elements

Since it won't provide indexing, we cannot directly access any element. The below is the way to traverse the set.

```cpp
for (auto x : st) {
    cout << x << " ";  // Prints each key in ascending order
}
```

*Lets understand by sample program*

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    set<int> st;

    // Inserting data into the set
    st.insert(1);    // Inserts 1 into the set
    st.insert(1);    // Since 1 is already present, it won't insert 1 again into the set
    st.insert(5);    // Inserts 5 into the set
    st.insert(10);   // Inserts 10 into the set
    st.insert(15);   // Inserts 15 into the set
    st.insert(5);     // Since 5 is already present, it won't insert 5 again into the set

    if (st.find(100) != st.end()) {
        cout << "Key is present ";
    } else {
        cout << "Key is not present "; // Prints "Key is not present"
    }

    if (st.find(1) != st.end()) {
        cout << "Key is present "; // Prints "Key is present" since 1 is present in the set
    } else {
        cout << "Key is not present ";
    }

    st.erase(1); // Removes 1 from the set

    cout << st.size() << " "; // Prints 3
    cout << st.empty(); // Prints false | 0
    st.clear(); // Removes all elements.

    return 0;
}
```

---

# Unordered Set in C++

- An `unordered_set` is similar to the set data structure and won't allow duplicate keys.
- The keys are `not sorted` in any order (No order), and hence the ordering of elements cannot be expected.
- It is implemented using `Hash Tables`.
- Faster in insertion / removal / find than set in average case i.e TC - O(1). ( worst case TC - O(n))

## Declaring unordered_set

### Syntax
```cpp
unordered_set< data_type > st;
```

### Examples

- `unordered_set<int> st;`  unordered_set of int's
- `unordered_set<string> st;`  unordered_set of strings
- `unordered_set<pair<int, int>> st;`  unordered_set of pairs
- `unordered_set<vector<int>> st;`  unordered_set of vectors


*Note: Similar syntax for `char`, `long long int`, `float`, `double`, `long double`, and some other data types, including user-defined data types.*

## Important functions on unordered_set

- `st.insert(key);`
  - Inserts the element 'key' into the set (if not present).
  - **Average Time Complexity:** 𝓞(1)
  - **Worst Time Complexity:** O(n)

- `st.erase(key);`
  - Removes the specified key if present.
  - **Average Time Complexity:** 𝓞(1)
  - **Worst Time Complexity:** O(n)

- `st.find(key);`
  - Returns an iterator pointing to the key. If the key is not present, returns `st.end()`.
  - **Average Time Complexity:** 𝓞(1)
  - **Worst Time Complexity:** O(n)

- `st.size();`
  - Returns the size of the set.
  - **Time Complexity:** 𝓞(1)

- `st.empty();`
  - Returns true if the set is empty, else false.
  - **Time Complexity:** 𝓞(1)

- `st.clear();`
  - Removes all set elements.
  - **Time Complexity:** O(n)

## Accessing unordered_set elements

Since it won't provide indexing, we cannot directly access any element. The below is the way to traverse the unordered_set.

```cpp
for (auto x : st) {
    cout << x << " ";  // prints each key in ascending order
}
```

*Lets understand by sample program*

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    
    unordered_set<int> st;
    
    // Inserting data into the set
    st.insert(1);    // Inserts 1 into set
    st.insert(1);    // Since 1 is already present, it won't insert 1 again into set
    st.insert(5);    // Inserts 5 into set
    st.insert(10);   // Inserts 10 into set
    st.insert(15);   // Inserts 15 into set
    st.insert(5);     // Since 5 is already present, it won't insert 5 again into set
    
    if (st.find(100) != st.end()) {
        cout << " Key is present ";
    } else {
        cout << " Key is not present "; // Prints "Key is not present"
    }
    
    if (st.find(1) != st.end()) {
        cout << " Key is present "; // Prints "Key is present" since 1 is present in set
    } else {
        cout << " Key is not present "; 
    }
    
    st.erase(1); // 1 removed from set

    cout << st.size() << " "; // Prints 3
    cout << st.empty(); // Prints false | 0
    st.clear(); // Removes all elements.
    
    return 0;
}
```

---

# MULTISET IN C++

- A multiset data structure `allows multiple keys with the same values`.
- Keys are sorted in ascending order by default. We can also change the order by passing extra arguments during its declaration.
- Implemented using `Binary search tree` (Red-black trees).

## Declaring multiset

### Syntax

```cpp
multiset< data_type > st; Stores keys in ascending order
multiset< data_type, greater< data_type > > st; Stores keys in descending order
```

### Examples

- `multiset<int> st;` Multiset of int's
- `multiset<string> st;` Multiset of strings
- `multiset<pair<int, int>> st;` Multiset of pairs
- `multiset<vector<int>> st;` Multiset of vectors


Note: Similar syntax for `char`, `long long int`, `float`, `double`, `long double`, and some other data types, including user-defined data types.

## Important Functions on Multiset

- `st.insert( key );` Inserts the element into the multiset. TC - 𝓞(logn)
- `st.erase( key );` Removes all occurrences of the specified key if present. TC - 𝓞(logn)
- `st.erase( st.find( key ) );` Removes only one occurrence of the specified key if present. TC - 𝓞(logn)
- `st.find( key );` Returns an iterator pointing to the key; if the key is not present, returns `st.end()`. TC - 𝓞(logn)
- `st.count( key );` Returns the frequency of the specified key. TC - 𝓞(logn)
- `st.size();` Returns the size of the multiset. TC - 𝓞(1)
- `st.empty();` Returns true if the multiset is empty; else, false. TC - 𝓞(1)
- `st.clear();` Removes all multiset elements. TC - O(n)

## Accessing Multiset Elements
Since it won't provide indexing, we cannot directly access any element. The below is the way to traverse the multiset.

```cpp
for( auto x : st ){
    cout << x << " ";  // Prints each key in ascending order
}
```

*Lets understand by sample program*

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    
    multiset<int> st;
    
    // Inserting data into the multiset
    st.insert(1);    // Inserts 1 into the multiset
    st.insert(1);    // Inserts 1 into the multiset
    st.insert(1);    // Inserts 1 into the multiset
    st.insert(5);    // Inserts 5 into the multiset
    st.insert(10);   // Inserts 10 into the multiset
    st.insert(15);   // Inserts 15 into the multiset
    st.insert(5);     // Inserts 5 into the multiset
    
    if( st.find(100) != st.end()){
        cout << " Key is present " << " ";
    }
    else {
        cout << " Key is not present "; // Prints key is not present
    }
    
    if( st.find(1) != st.end()){
        cout << " Key is present " << ; // Prints key is present since 1 is present in the multiset
    }
    else {
        cout << " Key is not present "; 
    }
    
    cout << st.count( 1 ) ; // Prints 3
    
    st.erase( st.find(1) ); // Removes one occurrence of 1
    
    cout << st.count(1) ; // Prints 2
    
    st.erase( 1 ); // Removes all occurrences of 1
    
    cout << st.count(1) ; // Prints 0
    
    cout << st.size() << " "; // Prints 4
    cout << st.empty(); // Prints false | 0
    st.clear(); // Removes all elements.
    
    return 0;
}
```

---

# Unordered Multiset in C++

- An `unordered_multiset` data structure allows multiple keys with the same values.
- Keys are `not sorted`, i.e., there is no particular order.
- Implemented using `Hash Tables`.

## Declaring Multiset

### Syntax

```cpp
unordered_multiset< data_type > st;
```

### Examples

- `unordered_multiset<int> st;`   unordered_multiset of int's
- `unordered_multiset<string> st;`    unordered_multiset of strings
- `unordered_multiset<pair<int, int>> st;`  unordered_multiset of pairs
- `unordered_multiset<vector<int>> st;`  unordered_multiset of vectors


Note: Similar syntax for `char`, `long long int`, `float`, `double`, `long double`, and some other data types, including user-defined data types.

## Important functions on unordered_multiset

- `st.insert( key );` 
  - Inserts the element into the multiset.
  - Average Time Complexity: 𝓞(1)
  - Worst Time Complexity: 𝓞(n)
  
- `st.erase( key );`
  - Removes all occurrences of the specified key if present.
  - Average Time Complexity: 𝓞(1)
  - Worst Time Complexity: 𝓞(n)

- `st.erase( st.find( key ) );`
  - Removes only one occurrence of the specified key if present.
  - Average Time Complexity: 𝓞(1)
  - Worst Time Complexity: 𝓞(n)

- `st.find( key );`
  - Returns an iterator pointing to the key. If the key is not present, returns `st.end()`.
  - Average Time Complexity: 𝓞(1)
  - Worst Time Complexity: 𝓞(n)

- `st.count( key ) ;`
  - Returns the frequency of the specified key.
  - Average Time Complexity: 𝓞(1)
  - Worst Time Complexity: 𝓞(n)

- `st.size();`
  - Returns the size of the multiset.
  - Time Complexity: 𝓞(1)

- `st.empty();`
  - Returns true if the multiset is empty, else false.
  - Time Complexity: 𝓞(1)

- `st.clear();`
  - Removes all multiset elements.
  - Time Complexity: 𝓞(n)

## Accessing multiset elements
Since it doesn't provide indexing, we cannot directly access any element. You can traverse the multiset using the following loop:

```cpp
for (auto x : st) {
    cout << x << " ";  // prints each key in ascending order
}
```

*Lets understand by sample program*

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    unordered_multiset<int> st;
    
    // Inserting data into the multiset
    st.insert(1);    // inserts 1 into multiset
    st.insert(1);    // inserts 1 into multiset
    st.insert(1);    // inserts 1 into multiset
    st.insert(5);    // inserts 5 into multiset
    st.insert(10);   // inserts 10 into multiset
    st.insert(15);   // inserts 15 into multiset
    st.insert(5);     // inserts 5 into multiset
    
    // Checking if 100 is present in the multiset
    if (st.find(100) != st.end()) {
        cout << "Key is present ";
    } else {
        cout << "Key is not present "; // prints key is not present
    }
    
    // Checking if 1 is present in the multiset
    if (st.find(1) != st.end()) {
        cout << "Key is present ";
    } else {
        cout << "Key is not present ";
    }
    
    // Counting occurrences of 1 in the multiset
    cout << st.count(1); // prints 3
    
    // Removing one occurrence of 1 from the multiset
    st.erase(st.find(1));
    
    // Counting occurrences of 1 in the multiset after removal
    cout << st.count(1); // prints 2
    
    // Removing all occurrences of 1 from the multiset
    st.erase(1);
    
    // Counting occurrences of 1 in the multiset after removal
    cout << st.count(1); // prints 0
    
    // Printing the size of the multiset
    cout << st.size() << " "; // prints 4
    
    // Printing whether the multiset is empty or not
    cout << st.empty(); // prints false | 0
    
    // Removing all elements from the multiset
    st.clear(); // removes all elements.
    
    return 0;
}
```

---

# MAPS IN C++

- A map is a data structure that stores elements in a mapped fashion. Each element has a key value and a mapped value, effectively storing `key-value pairs`.
- Keys are unique and sorted in ascending order by default.
- Implemented using `Binary Search Trees` (Red-Black Trees).

## Declaring a Map

### Syntax

```cpp
map<key_data_type, value_data_type> mp; keys are unique and sorted in ASC
```

### Examples

- `map<int, int> mp;` map of int as key and int as value
- `map<int, string> mp;`   map of int as key and String as value
- `map<int, vector<int>> mp;`  map of int as key and vector<int> as value
- `map<string, vector<int>> mp;`  map of String as key and vector<int> as value


Note: Similar syntax for `char`, `long long int`, `float`, `double`, `long double`, and some other data types, including user-defined data types.


## Important functions

- `mp[key] = value;`  
  Inserts key-value pair if not present. If present, updates the key with the current value.  
  TC - O(logn)

- `int a = mp[key];`  
  Returns the value at the specified key. If key is not present, it returns the default value and adds key->default_value into the map.  
  TC - O(logn)

- `mp.insert({key, value});`  
  Inserts a new key-value pair if the key is not present. If present, it won't add this key-value pair and won't update.  

- `mp.insert(make_pair(key, value));`  
  Inserts a new key-value pair if the key is not present. If present, it won't add this key-value pair and won't update.

- `mp.insert(pair<int, int>(5, 7));`  
  Inserts a new key-value pair if the key is not present. If present, it won't add this key-value pair and won't update.

- `mp.erase(key);`  
  Removes the specified entry with the specified key if present.  
  TC - O(logn)

- `mp.count(key);`  
  Returns the frequency of the key (0 or 1).  
  TC - O(logn)

- `mp.find(key);`  
  Returns the iterator pointing to the key if present, else returns mp.end().  
  TC - O(logn)

- `mp.clear();`  
  Removes all entries from the map.  
  TC - O(n)

- `mp.size();`  
  Returns the size of the map.  
  TC - O(1)

- `mp.empty();`  
  Returns true if the map is empty, else false.  
  TC - O(1)

## Traversing through map

### First way
```cpp
for(auto ele : mp){
    cout << ele.first << " " << ele.second << "\n";
}
```
### Second way
```cpp
for(auto it = mp.begin() ; it != mp.end() ; it++){
    cout << it->first <<  " " << it->second << "\n";
}
```
### Third way
```cpp
for(auto it = mp.rbegin() ; it != mp.rend() ; it++){
    cout << it->first << " " << it->second << "\n";
}
```

*Lets understand by sample program*

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // your code goes here
    map<int, int> mp; // creates an empty map ---> []
    mp[5] = 10;    // since key = 5 is not present, adds the entry with key as 5 and value as 10 ---> [5->10]
    mp[5] = 9; // key = 5 is present hence it updates with current value ---> [5->9]
    mp.insert(pair<int, int>(3, 7)); // since key = 3 is not present, adds the entry 3->7 ----> [3->7, 5->9]
    mp.insert(pair<int, int>(5, 8)); // since key = 5 is present, it won't add and update the entry. ---> [3->7, 5->9]
    mp.insert(make_pair(8, 1)); // since key = 8 is not present, adds the entry 8->1 ----> [3->7, 5->9, 8->1]
    mp.insert(make_pair(8, 2)); // since key = 8 is present, it won't add and update the entry. ---> [3->7, 5->9, 8->1]
    mp.insert({6, 11}); // since key = 6 is not present, adds the entry 6->11 ----> [3->7, 5->9, 6->11, 8->1]
    mp.insert({6, 99}); // since key = 6 is present, it won't add and update the entry. ---> [3->7, 5->9, 6->11, 8->1]
    cout << "size is " << mp.size() << "\n"; // prints 4
    mp.erase(5); // removes entry whose key = 5 i.e 5->9. ---> [3->7, 6->11, 8->1]
    mp.erase(100); // removes entry whose key = 100, but there is no entry matching this. So nothing will happen. ---> [3->7, 6->11, 8->1]
    cout << "value at key = 8 is " << mp[8] << "\n"; // prints the value at key = 8 i.e 1 
    cout << "value at key = 99 is " << mp[99] << "\n"; // since there is no key = 99 it adds entry 99->0 (0 is the default value) and prints 0. ---> [3->7, 6->11, 8->1, 99->0]
    cout << "Frequency of entry whose key = 3 is " << mp.count(3) << "\n";

    if (mp.find(12) != mp.end())
        cout << "Key = 12 is present \n";
    else
        cout << "key = 12 is not present\n";

    if (mp.find(99) != mp.end())
        cout << "Key = 99 is present \n";
    else
        cout << "key = 99 is not present\n";

    // printing map
    cout << "map entries are: \n";
    for (auto it = mp.begin(); it != mp.end(); it++) {
        cout << it->first << "->" << it->second << "\n";
    }
    return 0;
}
```

---

# UNORDERED MAPS IN C++

- An `unordered_map` is a data structure that stores elements in a mapped fashion. Each element has a key value and a mapped value. Essentially, it stores key-value pairs.
- Keys are unique and do not have a particular order.
- Implemented using `Hash tables`.

## Declaring map

### Syntax
```cpp
unordered_map<key_data_type, value_data_type> mp; // keys are unique and not have a particular order
```

### Examples

- `unordered_map<int, int> mp;`  unordered_map of int as key and int as value
- `unordered_map<int, string> mp;`   unordered_map of int as key and String as value
- `unordered_map<int, vector<int>> mp;`  unordered_map of int as key and vector<int> as value
- `unordered_map<string, vector<int>> mp;`   unordered_map of String as key and vector<int> as value

Note: Similar syntax for `char`, `long long int`, `float`, `double`, `long double`, and some other data types, including user-defined data types.


## Important Functions

- `mp[key] = value;`  
  Inserts key->value pair if not present. If present, updates the key with the current value.
  - Average TC: O(1)
  - Worst TC: O(n)

- `int a = mp[key];`  
  Returns the value at the specified key. If the key is not present, it returns the default value and adds key->default_value into the map.
  - Average TC: O(1)
  - Worst TC: O(n)

- `mp.insert(make_pair(key, value));`  
  Inserts a new key-value pair if the key is not present. If present, it won't add this key-value pair and won't update.
  - Average TC: O(1)
  - Worst TC: O(n)

- `mp.insert({key, value});`  
  Inserts a new key-value pair if the key is not present. If present, it won't add this key-value pair and won't update.
  - Average TC: O(1)
  - Worst TC: O(n)

- `mp.insert(pair<int, int>(5, 7));`  
  Inserts a new key-value pair if the key is not present. If present, it won't add this key-value pair and won't update.
  - Average TC: O(1)
  - Worst TC: O(n)

- `mp.erase(key);`  
  Removes the specified entry with the specified key if present.
  - Average TC: O(1)
  - Worst TC: O(n)

- `mp.count(key);`  
  Returns the frequency of the key (0 or 1).
  - Average TC: O(1)
  - Worst TC: O(n)

- `mp.find(key);`  
  Returns the position of the key if present, else returns `mp.end()`.
  - Average TC: O(1)
  - Worst TC: O(n)

- `mp.clear();`  
  Removes all entries from the map.
  - TC: O(n)

- `mp.size();`  
  Returns the size of the map.
  - TC: O(1)

- `mp.empty();`  
  Returns true if the map is empty, else false.
  - TC: 𝓞(1)

## Traversing through Map

### First Way
```cpp
for(auto ele : mp){
    cout << ele.first << " " << ele.second << "\n";
}
```
### Second way
```cpp
for(auto it = mp.begin() ; it != mp.end() ; it++){
    cout << it->first <<  " " << it->second << "\n";
}
```
### Third way
```cpp
for(auto it = mp.rbegin() ; it != mp.rend() ; it++){
    cout << it->first << " " << it->second << "\n";
}
```

*Lets understand by sample program*

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    unordered_map<int, int> mp; // creates an empty map ---> []
    mp[5] = 10;    // since key = 5 is not present, adds the entry with key as 5 and value as 10 ---> [5->10]
    mp[5] = 9; // key = 5 is present hence it updates with the current value ---> [5->9]
    mp.insert(pair<int, int>(3, 7)); // since k = 3 is not present adds the entry 3->7 ----> [5->9, 3->7] (Note: order is not guaranteed)
    mp.insert(pair<int, int>(5, 8)); // since key = 5 is present it won't add and update the entry. ---> [3->7, 5->9] (Note: order is not guaranteed)
    mp.insert(make_pair(8, 1)); // since key = 8 is not present adds the entry 8->1 ----> [3->7, 5->9, 8->1] (Note: order is not guaranteed)
    mp.insert(make_pair(8, 2)); // since key = 8 is present it won't add and update the entry. ---> [3->7, 5->9, 8->1] (Note: order is not guaranteed)
    mp.insert({6, 11}); // since key = 6 is not present adds the entry 6->11 ----> [3->7, 5->9, 6->11, 8->1] (Note: order is not guaranteed)
    mp.insert({6, 99}); // since key = 6 is present it won't add and update the entry. ---> [6->11, 8->1, 5->9, 3->7] (Note: order is not guaranteed)
    cout << "size is " << mp.size() << "\n"; // prints 4
    mp.erase(5); // removes entry whose key = 5 i.e 5->9. ---> [3->7, 8->1, 6->11] (Note: order is not guaranteed)
    mp.erase(100); // removes entry whose key = 100, but there is no entry matching this. So nothing will happen. ---> [3->7, 6->11, 8->1] (Note: order is not guaranteed)
    cout << "value at key = 8 is " << mp[8] << "\n"; // prints the value at key = 8 i.e 1 
    cout << "value at key = 99 is " << mp[99] << "\n"; // since there is no key = 99 it adds entry 99->0 (0 is the default value) and prints 0. ---> [3->7, 6->11, 8->1, 99->0] (Note: order is not guaranteed)
    cout << "Frequency of entry whose key = 3 is " << mp.count(3) << "\n";

    if(mp.find(12) != mp.end()) cout << "Key = 12 is present \n";
    else cout << "key = 12 is not present\n";

    if(mp.find(99) != mp.end()) cout << "Key = 99 is present \n";
    else cout << "key = 99 is not present\n";

    // printing map
    cout << "map entries are: \n" ;
    for(auto it = mp.begin() ; it != mp.end() ; it++){
        cout << it->first << "->" << it->second << "\n";
    }
    return 0;
}
```
---


# Multimaps in C++

- A `multimap` is a data structure that stores elements in a mapped fashion. Each element has a key value and a mapped value, essentially storing key-value pairs.
- The multimap is similar to a map, with the addition that multiple elements can have the same keys.
- Keys are sorted in ascending order by default.
- Implemented using `Binary Search Trees` (Red-Black Trees).

## Declaring Multimap

### Syntax:

```cpp
multimap<key_data_type, value_data_type> mp; // keys are sorted in ascending order
```

### Examples

- `multimap<int, int> mp;`  multimap of int's
- `multimap<int, string> mp;`   multimap of strings
- `multimap<int, vector<int>> mp;`  multimap of vectors
- `multimap<string, vector<int>> mp;` multimap of vectors


Note: Similar syntax for `char`, `long long int`, `float`, `double`, `long double`, and some other data types, including user-defined data types.

## Important functions

```cpp
mp.insert(make_pair(key, value));        // inserts new key-value pair      TC - O(logn)
mp.insert({key, value});                 // inserts new key-value pair       TC - O(logn)
mp.insert(pair<int, int>(5, 7));          // inserts new key-value pair       TC - O(logn)
mp.erase(key);                            // removes all occurrences of entries with specified key if present.      TC - O(logn)
mp.erase(mp.find(key));                   // removes one occurrence of entry with specified key if present.      TC - O(logn)
mp.count(key);                            // returns frequency of key      TC - O(logn)
mp.find(key);                             // returns pos of key if present. else return mp.end()      TC - O(logn)
mp.clear();                               // removes all entries from the map      TC - O(n)
mp.size();                                // returns the size of map      TC - O(1)
mp.empty();                               // returns true if map is empty else false    TC - 𝓞(1)
```

## Traversing through map

### First way
```cpp
for(auto ele : mp){
    cout << ele.first << " " << ele.second << "\n";
}
```

### Second way
```cpp
for(auto it = mp.begin(); it != mp.end(); it++){
    cout << it->first << " " << it->second << "\n";
}
```

### Third way
```cpp
for(auto it = mp.rbegin(); it != mp.rend(); it++){
    cout << it->first << " " << it->second << "\n";
}
```

*Lets understand by sample program*

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // your code goes here
    multimap<int, int> mp; // creates an empty map ---> []

    mp.insert(pair<int, int>(3, 7));   // adds the entry 3->7 ----> [3->7]
    mp.insert(pair<int, int>(5, 8));   // adds the entry 5->8---> [3->7, 5->8]
    mp.insert(make_pair(8, 1));        // adds the entry 8->1.---> [3->7, 5->8, 8->1]
    mp.insert(make_pair(8, 2));        // adds the entry 8->2.---> [3->7, 5->8, 8->1, 8->2]
    mp.insert({6, 11});                // adds the entry 6->11.---> [3->7, 5->8, 6->11, 8->1, 8->2]
    mp.insert({6, 99});                // adds the entry 6->11.---> [3->7, 5->8, 6->11, 6->99, 8->1, 8->2]
    mp.insert({6, 15});                // adds the entry 6->15.---> [3->7, 5->8, 6->11, 6->99, 6->15, 8->1, 8->2]
    cout << "size is " << mp.size() << "\n"; // prints 7
    cout << "Frequency of entry whose key = 6 is " << mp.count(6) << "\n";
    auto it = mp.begin();
    while(it != mp.end()){
        if(it->first == 6 && it->second == 11) break;
        it++;
    }
    mp.erase(it); // removes entry that 'it' points i.e 6->11. ---> [3->7, 5->8, 6->99, 6->15, 8->1, 8->2]
    cout << "Frequency of entry whose key = 6 after removing one occurrence is " << mp.count(6) << "\n";
    mp.erase(6);  // removes all occurrences of entry's whose keys = 6 ---> [3->7, 5->8, 8->1, 8->2]
    cout << "Frequency of entry whose key = 6 after removing all occurrences is " << mp.count(6) << "\n";
    mp.erase(100); // since there is no key = 100, nothing will be removed ---> [3->7, 5->8, 8->1, 8->2]

    if(mp.find(12) != mp.end()) cout << "Key = 12 is present \n";
    else cout << "key = 12 is not present\n";

    if(mp.find(8) != mp.end()) cout << "Key = 8 is present \n";
    else cout << "key = 99 is not present\n";

    // printing map
    cout << "map entry's are: \n" ;
    for(auto it = mp.begin() ; it != mp.end() ; it++){
        cout << it->first << "->" << it->second << "\n";
    }
    return 0;
}
```

# UNORDERED MULTIMAPS IN C++

- An `unordered_multimap` is a data structure that stores elements in a mapped fashion. Each element has a key value and mapped value, essentially storing key-value pairs.
- Multimap is similar to a map with the addition that `multiple elements can have the same keys`.
- Keys in an `unordered_multimap` are not sorted, meaning there is no particular order.
- Implemented using `Hash Tables`.

## Declaring multimap

### Syntax

```cpp
unordered_multimap<key_data_type, value_data_type> mp; // keys are not sorted i.e no particular order
```

### Examples

- `unordered_multimap<int, int> mp;`  unordered_multimap of int as key and int as value
- `unordered_multimap<int, string> mp;`   unordered_multimap of int as key and String as value
- `unordered_multimap<int, vector<int>> mp;`   unordered_multimap of int as key and vector<int> as value
- `unordered_multimap<string, vector<int>> mp;`   unordered_multimap of String as key and vector<int> as value


Note: Similar syntax for `char`, `long long int`, `float`, `double`, `long double`, and some other data types, including user-defined data types.


## Important Functions

- `mp.insert(make_pair(key, value));`  
  Inserts a new key-value pair.  
  - Average Time Complexity: O(1)  
  - Worst Time Complexity: O(n)

- `mp.insert({key, value});`  
  Inserts a new key-value pair.  
  - Average Time Complexity: O(1)  
  - Worst Time Complexity: O(n)

- `mp.insert(pair<int, int>(5, 7));`  
  Inserts a new key-value pair.  
  - Average Time Complexity: O(1)  
  - Worst Time Complexity: O(n)

- `mp.erase(key);`  
  Removes all occurrences of entries with the specified key if present.  
  - Average Time Complexity: O(1)  
  - Worst Time Complexity: O(n)

- `mp.erase(mp.find(key));`  
  Removes one occurrence of the entry with the specified key if present.  
  - Average Time Complexity: O(1)  
  - Worst Time Complexity: O(n)

- `mp.count(key);`  
  Returns the frequency of the key.  
  - Average Time Complexity: O(1)  
  - Worst Time Complexity: O(n)

- `mp.find(key);`  
  Returns the position of the key if present, otherwise returns `mp.end()`.  
  - Average Time Complexity: O(1)  
  - Worst Time Complexity: O(n)

- `mp.clear();`  
  Removes all entries from the map.  
  - Time Complexity: O(n)

- `mp.size();`  
  Returns the size of the map.  
  - Time Complexity: O(1)

- `mp.empty();`  
  Returns true if the map is empty; otherwise, false.  
  - Time Complexity: 𝓞(1)

## Traversing through unordered_multimap

### First Way
```cpp
for(auto ele : mp){
    cout << ele.first << " " << ele.second << "\n";
}
```

### Second way
```cpp
for(auto it = mp.begin() ; it != mp.end() ; it++){
    cout << it->first <<  " " << it->second << "\n";
}
```

### Third way
```cpp
for(auto it = mp.rbegin() ; it != mp.rend() ; it++){
    cout << it->first << " " << it->second << "\n";
}
```

*Lets understand by sample program*

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // your code goes here
    unordered_multimap<int, int> mp; // creates an empty map ---> []

    mp.insert(pair<int, int>(3, 7)); // adds the entry 3->7 ----> [3->7] (Note: Order of elements is not expected)
    mp.insert(pair<int, int>(5, 8)); // adds the entry 5->8---> [3->7, 5->8] (Note: Order of elements is not expected)
    mp.insert(make_pair(8, 1)); // adds the entry 8->1.---> [3->7, 5->8, 8->1] (Note: Order of elements is not expected)
    mp.insert(make_pair(8, 2)); // adds the entry 8->2.---> [3->7, 5->8, 8->1, 8->2] (Note: Order of elements is not expected)
    mp.insert({6, 11}); // adds the entry 6->11.---> [3->7, 5->8, 6->11, 8->1, 8->2] (Note: Order of elements is not expected)
    mp.insert({6, 99}); // adds the entry 6->11.---> [3->7, 5->8, 6->11, 6->99, 8->1, 8->2] (Note: Order of elements is not expected)
    mp.insert({6, 15}); // adds the entry 6->15.---> [3->7, 5->8, 6->11, 6->99, 6->15, 8->1, 8->2] (Note: Order of elements is not expected)
    cout << "size is " << mp.size() << "\n"; // prints 7
    cout << "Frequency of entry whose key = 6 is " << mp.count(6) << "\n";
    auto it = mp.begin();
    while(it != mp.end()){
        if(it->second == 11) break;
        it++;
    }
    mp.erase(it); // removes the entry that 'it' points i.e 6->11. ---> [3->7, 5->8, 6->99, 6->15, 8->1, 8->2]
    cout << "Frequency of entry whose key = 6 after removing one occurrence is " << mp.count(6) << "\n";
    mp.erase(6); // removes all occurrences of entries whose keys = 6 ---> [3->7, 5->8, 8->1, 8->2]
    cout << "Frequency of entry whose key = 6 after removing all occurrences is " << mp.count(6) << "\n";
    mp.erase(100); // since there is no key = 100, nothing will be removed ---> [3->7, 5->8, 8->1, 8->2]

    if(mp.find(12) != mp.end()) cout << "Key = 12 is present \n";
    else cout << "key = 12 is not present\n";

    if(mp.find(8) != mp.end()) cout << "Key = 8 is present \n";
    else cout << "key = 99 is not present\n";

    // printing map
    cout << "map entry's are: \n" ;
    for(auto it = mp.begin() ; it != mp.end() ; it++){
        cout << it->first << "->" << it->second << "\n";
    }
    return 0;
}
```


---

### Thanks for Reading 

<img src="/assets/images/save.png" width="600" height="200">

---

###

#### Join us for all the latest offcampus job updates, webinar, hackathons, resume review and a lot more :heart::heart:

<div align="left">
  <a href="https://www.linkedin.com/in/amanchowdhury046/" target="_blank">
    <img src="https://img.shields.io/static/v1?message=LinkedIn&logo=linkedin&label=&color=0077B5&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="linkedin logo"  />
  </a>
  <a href="https://www.youtube.com/@amanchowdhury046" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Youtube&logo=youtube&label=&color=FF0000&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="youtube logo"  />
  </a>
  <a href="https://telegram.me/offcampus_phodenge" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Telegram&logo=telegram&label=&color=2CA5E0&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="telegram logo"  />
  </a>
  <a href="https://www.instagram.com/aman_chowdhury_046/" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Instagram&logo=instagram&label=&color=E4405F&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="instagram logo"  />
  </a>
  <a href="https://whatsapp.com/channel/0029Va9Q0lkDZ4LYNx6ukw2u" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Whatsapp&logo=Whatsapp&label=&color=25D366&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="whatsapp logo"  />
  </a>
</div>

###

---
