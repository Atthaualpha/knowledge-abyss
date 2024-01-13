# Serial GC

*[:arrow_left: Go back to Garbage Collection](../GARBAGE_COLLECTION.md)*

Serial GC is the simplest of the all algorithms. This algorithm works using a single thread to process garbage through the heap.

Single GC has two main operations: it collects the young generation, and it collects the old generation.

These two operations are stop the world events, this means that every GC will stop the application. Due to this algorithm uses a single thread the time to run a GC cycle means a longer pauses, for that reason the usage of this algorithm is recommended to applications that tolerate this long pauses.

Internally of both operations, the GC runs a mark and sweep processes. Mark process identifies objects that are no longer in used, and sweep remove those objects. After this two processes there is a compacting process that puts objects together to avoid fragmentation.

The following figure illustrates the process of GC using serial algorithm. 

![serial_gc](../img/serial_gc.png)