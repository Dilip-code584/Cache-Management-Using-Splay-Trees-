Cache-management-using-splay-trees
Splay Tree Cache Management
This project implements a cache management system using Splay Trees. It allows efficient retrieval, insertion, and eviction of key-value pairs based on the least recently used (LRU) policy.

Features
Cache with a fixed capacity
Efficient retrieval of values based on keys
Insertion of new key-value pairs
Eviction of the least recently used entry when the cache is full
Implementation is provided for both single threaded as well as multithreaded environment
Problems with first implementation (single threaded environment)
 Concurrency Conflicts:
When multiple threads concurrently perform splaying operations (like insertion, retrieval, or deletion) on the same splay tree, they may conflict, leading to inconsistent tree structure or incorrect results.

Balancing Trade-off:
Splay trees rely on frequent reorganization for optimal performance. In a multi-threaded environment, we need to strike a balance between allowing enough reorganization to maintain the tree's efficiency and preventing excessive reorganization that might negatively impact performance due to synchronization.

Contention:
When multiple threads are frequently modifying the splay tree (e.g., due to cache updates), they may contend for access to the tree's root or other critical nodes, leading to contention and slowdowns.

Terms you should comfortable with -
cache block - The basic unit for cache storage. May contain multiple bytes/words of data.
cache line - Same as cache block. Note that this is not the same thing as a “row” of cache.
cache set - A “row” in the cache. The number of blocks per set is determined by the layout of the cache.
tag - A unique identifier for a group of data. Because different regions of memory may be mapped into a block, the tag is used to differentiate between them.
Dependencies
The project requires the following dependencies:

C++ compiler supporting C++11 or higher
Standard Template Library (STL)
ctime library for timestamp management
thread,mutex,crono and condition-variable libraries for providing and handelling multithreaded environment.
Getting Started
Clone the repository or download the source code files.
Compile the source code using a C++ compiler.
Run the compiled executable.
Usage
The program provides a command-line interface for interacting with the cache. It supports the following operations:

Add an entry: Allows you to add a new key-value pair to the cache.
Retrieve an entry: Retrieves the value associated with a given key from the cache.
Remove an entry: Removes a key-value pair from the cache.
Print cache contents: Displays the current contents of the cache.
Exit: Terminates the program. Follow the on-screen instructions to perform these operations.
Single threaded environmenmnt results
Screenshot 2023-08-12 164211

1)Creating Cache of size 3.
2)Added 3 key-value pairs in Cache and Printed them all.
3)Now after adding 4th entry in Cache least recently added/accessed entry got evicted and 4th entry took it's place.
Screenshot 2023-08-12 164429

4)Now if we add new entry in Cache our second added entry should get evicted since it is least recently added/accessed entry.
5)We will access second entry so that it will become recently accessed entry.
6)After accessing it Adding new entry in Cache.
7)Now printing Cache again.
8)least recently accessed entry got evicted and recently accessed entry in still there.
Multithreaded environment results
Without concurrency control
Created 3 threads thread1 is adding 3 elements in cache. thread2 is trying to get elements from cache(print). thread3 is trying to add 1 element in cache.

Result
Inconsistent results in different environments.

image image

Concurrency control using Mutex
Consistent results in different environments.

Screenshot 2023-08-12 165703 image

Contributing
Contributions to the project are welcome! If you find any issues or have suggestions for improvements, please feel free to submit a pull request or open an issue.

