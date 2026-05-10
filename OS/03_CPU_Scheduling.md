
# Introduction

In a multiprogramming operating system, multiple processes remain in memory simultaneously.

Since the CPU can execute only one process at a time, the operating system must decide:

> Which process should get CPU next?

This decision-making process is called CPU Scheduling.

CPU scheduling is one of the most important topics in Operating Systems for:

* Placements
* Technical interviews
* Competitive exams
* System design fundamentals

---

# What is CPU Scheduling?

CPU Scheduling is the process of selecting a process from the ready queue and allocating the CPU to it.

The component responsible for this is called:

> CPU Scheduler

---

# Why CPU Scheduling is Needed

Without scheduling:

* CPU may remain idle
* Processes may wait indefinitely
* System performance becomes poor
* User responsiveness decreases

CPU scheduling helps:

* Maximize CPU utilization
* Reduce waiting time
* Improve response time
* Increase throughput

---

# Basic Scheduling Terminologies

---

# 1. Arrival Time (AT)

The time at which a process enters the ready queue.

---

# 2. Burst Time (BT)

The amount of CPU time required by a process.

Also called:

* Execution Time
* CPU Time

---

# 3. Completion Time (CT)

The time at which process execution completes.

---

# 4. Turnaround Time (TAT)

Total time taken by process from arrival to completion.

Formula:

genui{"math_block_widget_always_prefetch_v2":{"content":"Turnaround\ Time = Completion\ Time - Arrival\ Time"}}

---

# 5. Waiting Time (WT)

Time spent waiting in ready queue.

Formula:

genui{"math_block_widget_always_prefetch_v2":{"content":"Waiting\ Time = Turnaround\ Time - Burst\ Time"}}

---

# 6. Response Time (RT)

Time from arrival until first CPU allocation.

Formula:

genui{"math_block_widget_always_prefetch_v2":{"content":"Response\ Time = First\ CPU\ Allocation - Arrival\ Time"}}

---

# 7. Throughput

Number of processes completed per unit time.

Higher throughput means better performance.

---

# 8. CPU Utilization

Percentage of time CPU remains busy.

Goal:

* Maximize CPU utilization

---

# Scheduling Queues

Processes move through different queues.

---

# 1. Job Queue

Contains all processes in system.

---

# 2. Ready Queue

Contains processes ready for execution.

---

# 3. Device Queue

Contains processes waiting for I/O devices.

---

# Types of CPU Scheduling

There are two major types.

---

# 1. Non-Preemptive Scheduling

Once CPU is allocated, the process keeps CPU until:

* Completion
* Voluntary waiting

The OS cannot forcibly remove CPU.

---

# Advantages of Non-Preemptive Scheduling

* Simple implementation
* Lower overhead
* Fewer context switches
* Stable execution

---

# Disadvantages of Non-Preemptive Scheduling

* Poor response time
* Convoy effect possible
* Long waiting for short processes
* Not suitable for interactive systems

---

# Examples

* FCFS
* Non-preemptive SJF
* Non-preemptive Priority Scheduling

---

# 2. Preemptive Scheduling

The operating system can interrupt a running process and allocate CPU to another process.

---

# Advantages of Preemptive Scheduling

* Better responsiveness
* Suitable for multitasking
* Better average waiting time
* Fair CPU sharing

---

# Disadvantages of Preemptive Scheduling

* More context switching overhead
* More complex implementation
* Synchronization problems possible

---

# Examples

* Round Robin
* SRTF
* Preemptive Priority Scheduling

---

# First Come First Serve (FCFS)

FCFS is the simplest CPU scheduling algorithm.

Processes are executed in order of arrival.

It follows:

> FIFO (First In First Out)

---

# Working of FCFS

1. Process enters ready queue.
2. CPU allocated to earliest arrived process.
3. Process executes until completion.
4. Next process gets CPU.

---

# Example

| Process | Arrival Time | Burst Time |
| ------- | ------------ | ---------- |
| P1      | 0            | 5          |
| P2      | 1            | 3          |
| P3      | 2            | 2          |

---

# Gantt Chart

```text
0 ----- P1 ----- 5 --- P2 --- 8 -- P3 -- 10
```

---

# Calculations

| Process | CT | TAT | WT |
| ------- | -- | --- | -- |
| P1      | 5  | 5   | 0  |
| P2      | 8  | 7   | 4  |
| P3      | 10 | 8   | 6  |

Average Waiting Time:

genui{"math_block_widget_always_prefetch_v2":{"content":"Average\ WT = \frac{0+4+6}{3} = 3.33"}}

---

# Advantages of FCFS

* Very simple
* Easy implementation
* Minimal overhead
* Fair according to arrival order

---

# Disadvantages of FCFS

* Convoy effect
* Poor average waiting time
* Poor response time
* Not suitable for interactive systems

---

# Convoy Effect

Short processes wait behind long processes.

This reduces system performance.

---

# Use Cases of FCFS

* Batch systems
* Simple embedded systems
* Low complexity environments

---

# Shortest Job First (SJF)

SJF selects the process with the smallest burst time.

It can be:

* Preemptive
* Non-preemptive

Usually SJF refers to non-preemptive version.

---

# Working of SJF

1. Select shortest burst time process.
2. Execute until completion.
3. Repeat.

---

# Example

| Process | Arrival Time | Burst Time |
| ------- | ------------ | ---------- |
| P1      | 0            | 6          |
| P2      | 1            | 4          |
| P3      | 2            | 2          |

---

# Gantt Chart

```text
0 ------ P1 ------ 6 -- P3 -- 8 ---- P2 ---- 12
```

---

# Calculations

| Process | CT | TAT | WT |
| ------- | -- | --- | -- |
| P1      | 6  | 6   | 0  |
| P2      | 12 | 11  | 7  |
| P3      | 8  | 6   | 4  |

---

# Advantages of SJF

* Minimum average waiting time
* Better turnaround time
* Efficient for short processes

---

# Disadvantages of SJF

* Starvation possible
* Difficult to predict burst time
* Long processes may wait indefinitely

---

# Use Cases of SJF

* Batch processing systems
* Systems where burst time estimation is possible

---

# Shortest Remaining Time First (SRTF)

SRTF is the preemptive version of SJF.

The process with shortest remaining burst time gets CPU.

If a shorter process arrives, current process is preempted.

---

# Example

| Process | Arrival Time | Burst Time |
| ------- | ------------ | ---------- |
| P1      | 0            | 8          |
| P2      | 1            | 4          |
| P3      | 2            | 2          |

---

# Gantt Chart

```text
0-1 P1 | 1-2 P2 | 2-4 P3 | 4-7 P2 | 7-14 P1
```

---

# Advantages of SRTF

* Very low average waiting time
* Better responsiveness
* Efficient CPU usage

---

# Disadvantages of SRTF

* High context switching
* Starvation possible
* Complex implementation

---

# Use Cases of SRTF

* Interactive systems
* Time-sharing systems
* Systems prioritizing short tasks

---

# Priority Scheduling

Each process is assigned a priority.

Higher priority process gets CPU first.

Priority may be:

* Internal
* External

Can be:

* Preemptive
* Non-preemptive

---

# Example

| Process | Priority | Burst Time |
| ------- | -------- | ---------- |
| P1      | 2        | 4          |
| P2      | 1        | 3          |
| P3      | 3        | 5          |

Smaller number means higher priority.

---

# Gantt Chart

```text
0 --- P2 --- 3 ---- P1 ---- 7 ------ P3 ------ 12
```

---

# Advantages of Priority Scheduling

* Important tasks execute earlier
* Flexible scheduling
* Suitable for real-time systems

---

# Disadvantages of Priority Scheduling

* Starvation possible
* Low priority processes may never execute
* Complex priority management

---

# Starvation

Low priority processes may wait indefinitely.

---

# Aging

Aging gradually increases priority of waiting processes.

Used to prevent starvation.

---

# Use Cases of Priority Scheduling

* Real-time systems
* OS kernel scheduling
* Interrupt handling
* Critical systems

---

# Round Robin (RR)

Round Robin is a preemptive scheduling algorithm.

Each process gets a fixed CPU time called:

> Time Quantum

If process does not finish within quantum, it is preempted.

---

# Working of Round Robin

1. Allocate fixed time quantum.
2. Execute process.
3. If unfinished, move to back of queue.
4. Repeat.

---

# Example

Time Quantum = 2

| Process | Burst Time |
| ------- | ---------- |
| P1      | 5          |
| P2      | 4          |
| P3      | 2          |

---

# Gantt Chart

```text
0-2 P1 | 2-4 P2 | 4-6 P3 | 6-8 P1 | 8-10 P2 | 10-11 P1
```

---

# Advantages of Round Robin

* Fair CPU allocation
* Good response time
* Suitable for time-sharing systems
* Prevents starvation

---

# Disadvantages of Round Robin

* High context switching
* Performance depends on quantum size
* Larger waiting time possible

---

# Effect of Time Quantum

---

## Very Small Quantum

* More context switching
* Higher overhead

---

## Very Large Quantum

* Behaves like FCFS

---

# Use Cases of Round Robin

* Time-sharing systems
* Interactive systems
* Modern operating systems

---

# Multilevel Queue Scheduling (MLQ)

Ready queue is divided into multiple queues.

Each queue has its own scheduling algorithm.

Processes are permanently assigned to queues.

---

# Example Queues

* System processes
* Interactive processes
* Batch processes

---

# Example Scheduling

| Queue             | Algorithm   |
| ----------------- | ----------- |
| System Queue      | Round Robin |
| Interactive Queue | Priority    |
| Batch Queue       | FCFS        |

---

# Advantages of MLQ

* Different treatment for different process types
* Better organization
* Fast response for important tasks

---

# Disadvantages of MLQ

* Inflexible
* Starvation possible
* Complex queue management

---

# Use Cases of MLQ

* Systems with multiple process categories
* Enterprise operating systems

---

# Multilevel Feedback Queue Scheduling (MLFQ)

MLFQ improves MLQ.

Processes can move between queues.

Priority changes dynamically.

---

# Working of MLFQ

* High priority queues get CPU first.
* If process uses too much CPU, move to lower queue.
* Short interactive processes stay in higher queues.

---

# Advantages of MLFQ

* Flexible
* Better responsiveness
* Reduces starvation
* Adapts to process behavior

---

# Disadvantages of MLFQ

* Very complex
* Difficult tuning
* Higher overhead

---

# Use Cases of MLFQ

* Modern operating systems
* Interactive environments
* General purpose computing

---

# Comparison of CPU Scheduling Algorithms

| Algorithm   | Type           | Starvation | Complexity | Response Time |
| ----------- | -------------- | ---------- | ---------- | ------------- |
| FCFS        | Non-preemptive | No         | Simple     | Poor          |
| SJF         | Non-preemptive | Yes        | Medium     | Good          |
| SRTF        | Preemptive     | Yes        | High       | Better        |
| Priority    | Both           | Yes        | Medium     | Good          |
| Round Robin | Preemptive     | No         | Medium     | Very Good     |
| MLQ         | Both           | Possible   | High       | Good          |
| MLFQ        | Preemptive     | Reduced    | Very High  | Excellent     |

---

# Difference Between Preemptive and Non-Preemptive Scheduling

| Feature           | Preemptive                     | Non-Preemptive           |
| ----------------- | ------------------------------ | ------------------------ |
| CPU Removal       | Possible                       | Not possible             |
| Response Time     | Better                         | Poor                     |
| Complexity        | High                           | Low                      |
| Context Switching | More                           | Less                     |
| Performance       | Better for interactive systems | Better for batch systems |

---

# Important Numerical Formulas

---

# Turnaround Time

genui{"math_block_widget_always_prefetch_v2":{"content":"TAT = CT - AT"}}

---

# Waiting Time

genui{"math_block_widget_always_prefetch_v2":{"content":"WT = TAT - BT"}}

---

# Average Waiting Time

genui{"math_block_widget_always_prefetch_v2":{"content":"Average\ WT = \frac{\Sigma WT}{Number\ of\ Processes}"}}

---

# Average Turnaround Time

genui{"math_block_widget_always_prefetch_v2":{"content":"Average\ TAT = \frac{\Sigma TAT}{Number\ of\ Processes}"}}

---

# Important Interview Questions

---

# Basic Questions

1. What is CPU scheduling?
2. Why is CPU scheduling needed?
3. What is throughput?
4. Difference between waiting time and turnaround time?
5. Difference between preemptive and non-preemptive scheduling?

---

# Algorithm Questions

1. Explain FCFS scheduling.
2. What is convoy effect?
3. Why is SJF optimal?
4. Difference between SJF and SRTF?
5. What is starvation?
6. What is aging?
7. Why is Round Robin used in time-sharing systems?
8. Effect of time quantum?
9. Difference between MLQ and MLFQ?

---

# Advanced Questions

1. Which scheduling algorithm is best?
2. Why is burst time prediction difficult?
3. Why does context switching reduce performance?
4. Which scheduling algorithm is used in modern operating systems?
5. Why is Round Robin considered fair?

---

# Quick Revision Notes

* CPU scheduling selects next process for execution.
* FCFS is simplest scheduling algorithm.
* SJF gives minimum average waiting time.
* SRTF is preemptive SJF.
* Priority scheduling may cause starvation.
* Aging prevents starvation.
* Round Robin uses time quantum.
* MLQ uses fixed queues.
* MLFQ allows queue movement.
* Preemptive scheduling improves responsiveness.

---

# Key Terms

| Term | Meaning                       |
| ---- | ----------------------------- |
| AT   | Arrival Time                  |
| BT   | Burst Time                    |
| CT   | Completion Time               |
| WT   | Waiting Time                  |
| TAT  | Turnaround Time               |
| RT   | Response Time                 |
| RR   | Round Robin                   |
| SJF  | Shortest Job First            |
| SRTF | Shortest Remaining Time First |
| MLQ  | Multilevel Queue              |
| MLFQ | Multilevel Feedback Queue     |

---

# Conclusion

CPU scheduling is a core function of an operating system.

Efficient scheduling improves:

* CPU utilization
* Responsiveness
* Throughput
* User experience


