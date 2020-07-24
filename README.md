# How-to-Talk-Queues

August 18, 2019

I appreciate comments. Shoot me an email at noel_s_cruz@yahoo.com!

Hire me!

The Queue ADT

Like stacks, queues are lists. With a queue, however, insertion is done at one
end whereas deletion is performed at the other end.

Queue Model

The basic operations on a queue are enqueue, which inserts an element at the
end of the list (called the rear), and dequeue (and returns) the element at the
start of the list (known as the front). Figure below shows the abstract model 
of a queue.

         4  2  8  1                  <---     Queue     <---
         
         ^        ^                   dequeue            enqueue
         
         l        l
         
         front    back

Array Implementation of Queues

As with stacks, any list implementation is legal for queues. Like stacks, both
the linked list and array implementations give fast O(1) running times for 
every operation. The linked list implementation is straightforward and left as
an exercise. We will now discuss an array implementation of queues.

For each queue data structure, we keep an array, theArray, and the positions
front and back, which represents the ends of the queue. We also keep track of 
the number of elements that are actually in the queue, currentSize.

The operations should be clear. To enqueue an element x, we increment 
currentSize and back, then set theArray[back] = x. To dequeue, we set the 
return value to theArray[front], decrement currentSize, and then increment front.
Other strategies are possible. 

There is one potential problem with this implementation. After 10 enqueues, the
queue appears to be full, since back is now at the last array index, and the 
next enqueue would be in a nonexistent position. However, there might only be a
few elements in the queue, because several elements may have already been 
dequeued. Queues, like stacks, frequently stay small even in the presence of a 
lot of operations.

The simple solution is that whenever front or back gets to the end of the 
array, it is wrapped around to the beginning. This is known as a circular array
implementation.

The extra code required to implement the wraparound is minimal (although it
probably doubles the running time). If incrementing either back or front causes
it to go past the array, the value is reset to the first position in the array.

Some programmers use different ways of representing the front and back of a 
queue. For instance, some do not use an entry to keep track of the size, because
they rely on the base case that when the queue is empty, back = front-1. The 
size is computed implicitly by comparing back and front. This is a very tricky
way to go, because there are some special cases, so be very careful if you need
to modify code written this way. If the currentSize is not maintained as an 
explicit data member, then the queue is full when there are 
theArray.capacity()-1 elements, since only theArray.capacity() sizes can be
differentiated and one of these is 0. Pick any style you like and make sure
that all your routines are consistent. Since there are a few options for
implementation, it is probably worth a comment or two in the code if you don't
use the currentSize data member.

In applications where you are sure that the number of enqueues is not larger
than the capacity of the queue, the wraparound is not necessary. A with stacks,
dequeues are rarely performed unless the calling routines are certain that the
queue is not empty. Thus error checks are frequently skipped for this 
operation, except in critical code. This is generally not justifiable, because
the time savings that you are likely to achieve are minimal.

Applications

There are many algorithms that use queues to give efficient running times.
Several of these are found in graph theory.

Additional uses for queues abound, and as with stacks, it is staggering that 
such a simple data structure can be so important.

End of story and thanks for reading. Hope it helps!

I included some posts for reference.

https://github.com/noey2020/How-to-Talk-Stacks

https://github.com/noey2020/How-to-Talk-Lists-Stacks-and-Queues

https://github.com/noey2020/How-to-Talk-Linear-Regression

https://github.com/noey2020/How-to-Talk-Statistics-Pattern-Recognition-101

https://github.com/noey2020/How-to-Write-SPI-STM32

https://github.com/noey2020/How-to-Write-SysTick-Handler-for-STM32

https://github.com/noey2020/How-to-Write-Subroutines-in-C-Assembly-STM32

https://github.com/noey2020/How-to-Write-Multitasking-STM32

https://github.com/noey2020/How-to-Generate-Triangular-Wave-STM32-DAC

https://github.com/noey2020/How-to-Generate-Sine-Table-LUT

https://github.com/noey2020/How-to-Illustrate-Multiple-Exceptions-

https://github.com/noey2020/How-to-Blink-LED-using-Standard-Peripheral-Library

I appreciate comments. Shoot me an email at noel_s_cruz@yahoo.com!

Hire me!

Have fun and happy coding!
