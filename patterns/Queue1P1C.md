## Concurrent 1x1 Queue (1-Producer, 1-Consumer)

Low-latency + high-throughput.

In the case of having only one producer, and regardless of the complexity of the consumer graph, no locks or CAS operations are required. The whole concurrency coordination can be achieved with just memory barriers on the discussed sequences.

- array backed not linked list: if storage can be performed in a uniform chunk, then traversal of that data will be done in a manner that is very friendly to the caching strategies employed by modern processors.
- without any blocking: ```boolean offer(E elem)```, ```E poll()```
- without any memory allocation/gc: ring buffer: ```E[] buffer``` 
- without integer division: ```index = currentHead & mask```, On most processors there is a very high cost for the remainder calculation on the sequence number, which determines the slot in the ring. This cost can be greatly reduced by making the ring size a power of 2. A bit mask of size minus one can be used to perform the remainder operation efficiently.
- head/tail pointers - on different cache lines: ```PaddedAtomicLong```
- lazySet VS volatile write
- ??? PaddedLong
- ??? batch read/write

### Links
- Martin Tompson [sources](https://github.com/mjpt777/examples/tree/master/src/main/java/uk/co/real_logic/queues)
-  Thompson, Farley, Barker, Gee, Stewart, 2011. [Disruptor: High performance alternative to bounded queues for exchanging data between concurrent threads](https://lmax-exchange.github.io/disruptor/files/Disruptor-1.0.pdf)
