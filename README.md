Splay Tree Cache Management


This project implements a cache management system using Splay Trees, enabling efficient retrieval, insertion, and eviction of key-value pairs based on the Least Recently Used (LRU) policy.



Features


Fixed Capacity Cache: The cache has a predetermined capacity.


Efficient Retrieval: Quickly retrieve values based on keys.


Insertion of Key-Value Pairs: Add new key-value pairs to the cache.


Eviction Policy: Automatically evict the least recently used entry when the cache reaches full capacity.


Single and Multi-threaded Implementation: Supports both single-threaded and multi-threaded environments.


Problems with First Implementation (Single-threaded Environment)

Concurrency Conflicts: In a multi-threaded scenario, concurrent splaying operations (insertion, retrieval, or deletion) on the same splay tree may lead to conflicts, resulting in an inconsistent tree structure or incorrect results.

Balancing Trade-off: Splay trees rely on frequent reorganization for optimal performance. In a multi-threaded environment, it's crucial to balance sufficient reorganization to maintain efficiency while avoiding excessive reorganization that could impact performance due to synchronization.

Contention: Frequent modifications to the splay tree by multiple threads (e.g., cache updates) can lead to contention for access to the tree's root or other critical nodes, causing slowdowns.

Key Terms
Cache Block: The basic unit for cache storage, which may contain multiple bytes or words of data.

Cache Line: Synonymous with cache block, not to be confused with a "row" of cache.

Cache Set: A "row" in the cache, with the number of blocks per set determined by the cache's layout.

Tag: A unique identifier for a group of data. Tags differentiate between different memory regions mapped into a block.
Dependencies

To build and run this project, the following dependencies are required:

C++ compiler supporting C++11 or higher

Standard Template Library (STL)

ctime library for timestamp management

thread, mutex, chrono, and condition_variable libraries for handling multithreaded environments

Getting Started
Clone the Repository: Clone the repository or download the source code files.

Compile the Source Code: Use a C++ compiler to compile the source code.

Run the Executable: Execute the compiled program.
