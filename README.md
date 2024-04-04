# Producer-Consumer Problem 

Example of a solution to the producer-consumer problem using semaphores, shared memory, and threading in C++. 

## General Information

This project was completed for cs33211 (Opearting Systems) at Kent State University on 04/05/24.

For this example of the producer-consumer problem, the producer and consumer communicate via shared memory. This shared memory includes a table that can hold up to two items at a time (implemented as a circular array) and the necessary semaphores. There are three semaphores that keep track of when the table is full, when the table is empty, and when one of the processes or threads is in a critical section (enforcing mutual exclusion). The items produced and consumed by the processes are simply characters from A to Z and are randomized each execution. 

Output is produced to help visualize the execution of the producer and consumer processes. Whenever items are produced or consumed, this is communicated through process output. 

## Usage

To compile the producer and consumer programs, enter the following commands into the terminal.
```bash
g++ producer.cpp -pthread -lrt -o producer
g++ consumer.cpp -pthread -lrt -o consumer
```

To run the programs, enter the following command into the terminal.
```bash
./producer & ./consumer &
```

An example execution of the programs may look like this.
```bash
[user@hornet Project1]$ ./producer & ./consumer &
[1] 2735532
[2] 2735533
Produced Item: a
Consumed item: a
Produced Item: c
Consumed item: c
Produced Item: d
Consumed item: d
Produced Item: b
Consumed item: b
[1]-  Done                    ./producer
[2]+  Done                    ./consumer
[user@hornet Project1]$
```

## Environment Information

All programming was done using C++.<br>
This project was run in Red Hat Enterprise Linux 8.<br>
The programs were compiled with g++ (GCC) version 8.5.0.

