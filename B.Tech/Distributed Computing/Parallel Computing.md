Parallel computing refers to the process of executing several processors an application or computation simultaneously. 
Generally, it is a kind of computing architecture where the large problems break into independent, smaller, usually similar parts that can be processed in one go.

*parallel computing is the simultaneous use of multiple compute resources to solve a computational problem*

#### Benefits
1. **Save Time and Money**
2. **Solve computationally hard problems**
3. **Concurrency**
4. **Use non local resources**
5. **Make better use of modern/parallel hardware**

### Von Neuman Architecture
known as "stored-program computer" - both program instructions and data are kept in electronic memory. Differs from earlier computers which were programmed through "hard wiring".

Consists of Control Unit, ALU, Memory, I/O

Program instructions are coded data which tell the computer to do something

### Flynn's Classical Taxonomy
distinguishes multi-processor computer architectures along the two independent dimensions of *Instruction Stream and Data Stream*

#### 1. SISD
Single Instruction Single Data.
**Single Instruction:** Only one instruction can be acted from the memory in a clock cycle.
**Single Data:** Only one data stream used as input in a clock cycle

Eg: Most old computer, mainframes, 

#### 2. SIMD
Single Instruction Multiple Data
**Single Instruction:** Only one instruction can be acted by all the processors. 
**Multiple Data:** Multiple data streams as input. Each processing unit can act on different data element.
Best suited when regularity in data such as graphics processing etc.
Eg: GPU, Most modern computers.

#### 3. MISD
Multiple Instruction Single Data
**Multiple Instruction:** Multiple instruction can be acted upon by different processors separately 
**Single Data:** But all of them will act on a single data stream as input.

Eg: multiple cryptography algorithms attempting to crack a single coded message

#### 4. MIMD
Multiple Instruction Multiple Data
**Multiple Instruction:** Every processor may be executing a different instruction stream
**Multiple Data:** Every processor may be working with a different data stream

Eg: Modern supercomputers consists of grids and arrays for this reason


### General Parallel Computing Terms
1. **CPU:** Central Processing Unit. Considered as a distinct execution unit with its own instruction stream. It has multiple cores. Cores are connected with sockets. When multiple sockets, CPU has shared memory
2. **Node:** "Computer in a box", this consist of all the necessary hardware required for a computer to start compute processes such as CPU, Memory, Network cards. Nodes are often pooled together to make supercomputers
3. **Task:** Task are a distinct section of computational work. They are usually programs. A parallel program consists of multiple task running parallely.
4. **Pipelining:** Consists of breaking a task into subtasks are running them parallely. The input stream is processed and piped to stages one after the other and the final result in computed in the final subtask.
5. **Shared Memory:** Memory architecture type where each processor has the same view of the memory. They all see the same address space. This makes it easier to work simultaneously in a parallel program. 
6. **SMP:** Symmetric Multi Processor. Here, shared hardware architecture where all processors have the same access to all resources- network, memory etc.
7. **Distributed Memory:** Tasks only see the memory of the local machine and must communicate with other machines in order to see the task on their machines.
8. **Communications:** Parallel processes need to share data either through shared bus or network.
9. **Synchronization:** When parallel execution takes place, often a task needs to wait for other task to complete to resume execution on their resulting data, which in turn increases the wall clock execution time of the parallel program.
10. **Computational Granularity:** The quantitative/ qualitative measure of the ratio of  computation to communication. 
    - **Fine:** Small computation occur b/w 2 computation events
    - **Coarse:** Large computation occur b/w 2 computation events
11. **Observed Speedup:** Wall clock time of serial computation/wall clock time of parallel computation. It is used to measure the performance of the parallel program at hand.
12. **Parallel Overhead:** Execution time of the parallel program. Effected by factors such as
    - Task startup time
    - Synchronization
    - Data communication
    - Software overhead such as library calls.
    - Termination Time
13. **Massively Parallel:** Refers to hardware consisting of parallel system having many processing elements. They keep increasing from hundreds, thousands to millions.
14. **Embarrassingly Parallel:** Solving many similar, but independent tasks simultaneously; little to no need for coordination between the tasks.
15. **Scalability:** Ability of parallel systems' to increase in processing power as resources are added. Factors include: hardware resources, algorithm, parallel overhead etc.

### Types of Parallelism
1. **Bit level**: It is the form of parallel computing which is based on the increasing processor’s size. It reduces the number of instructions that the system must execute in order to perform a task on large-sized data.
2. **Instruction level**: A processor can only address less than one instruction for each clock cycle phase. These instructions can be reordered and grouped which are later on executed concurrently without affecting the result of the program
3. **Task Level**: Breaking task into subtask and allocating resources for each of them.
4. **Data Level**: Instructions from a single stream operate concurrently on several data – Limited by non-regular data manipulation patterns and by memory bandwidth

### Limitations
1. Communications and synchronization are difficult to achieve.
2. Algorithms must be written in a way that does task parallelly
3. Program should have low coupling and high cohesion
4. Skilled programmers required.

### Scalability
#### Strong Scalability(Amdahl)
Here, problem size is fixed as processor count is increased. Goal is to run the same problem faster. Perfect scaling should be 1/P time

#### Weak Scalability(Gustafson)
Here, with processor count, the problem size is increased proportionally, Goal is to run larger problems in the same time. Perfect scaling means problem Px runs in same time as a single processor run

Hardware also plays factor in scaling: More network bandwidth, more memory available, processor clock speed.

![[Pasted image 20241008215453.png]]

### Parallel Computing Memory Architecture

#### Shared Memory
All processor have the same picture of the memory. They share a global address space in memory. Multiple processor operate independently in the same memory. changes are visible to each processor. 
- **UMA (Unified Memory Access)**
  SMP Machines, identical processors.
  Equal access and access times to memory
  CC-UMA or cache coherent UMA: Means if one processor updates a location in shared memory, the other processors know about the update. Accomplished at hardware level.
- **NUMA (Unified Memory Access)**
  Physically linking 2 or more SMP Machines.
  One SMP can directly access other's memory
   Unequal access and access times to memory
   CC-NUMA- if cache coherency is maintained

