## Concurrent 1x1 Queue (1-Producer, 1-Consumer)

Low-latency + high-throughput.

- without any blocking: ```boolean offer(E elem)```, ```E poll()```
- without any memory allocation/gc: ring buffer: ```E[] buffer```
- without integer division: ```index = currentHead & mask```
- head/tail pointers - on different cache lines: ```PaddedAtomicLong```
- lazySet VS volatile write
- ??? PaddedLong

### Links
- Martin Tompson [sources](https://github.com/mjpt777/examples/tree/master/src/main/java/uk/co/real_logic/queues)
-  Thompson, Farley, Barker, Gee, Stewart, 2011. [Disruptor: High performance alternative to bounded queues for exchanging data between concurrent threads](https://lmax-exchange.github.io/disruptor/files/Disruptor-1.0.pdf)
