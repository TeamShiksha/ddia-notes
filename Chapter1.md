# Chapter 1:

- This chapter focus on three concerns that are important in most software systems:
  1. **_Reliability_**:
  - System should continue to work correctly even it faces any difficulty.
  - While designing the system we have to sure about some typical expectations, includes:
    - System can tolerate the user making mistakes
    - System should prevent unauthorized access and abuse
    - Performance is good enough under the expected load and data volume
  - System should be _fault-tolerant_
  - _FAULT_ is not same as _FAILURE_. Fault -> when one component stops working, Failure -> when entire system is crashed
  - Type of Faults:
    1. Hardware Faults:
    - Cause: Hard disks crash, RAM becomes faulty, power blackout, etc.
    - Prevention: Add redundancy (RAID Config for Disks, Hot-swappable CPUs, Diesel generators, etc.)
    2. Software Errors:
    - Cause: System errors like Kernel Issue, Memory/CPU starvation, Domino effect where a small fault in one component triggers a fault in another components....
    - Prevention: No such standard methods. Test thoroughly, monitor system in production, constant checks and raise an alert if a discrepancy is found.
    3. Human Errors:
    - Cause is self explanatory
    - Prevention: Test thoroughly at all levels, Quick and easy recovery in case of failure, Telemetry monitoring and good management and training.
  2. **_Scalability_**:
  - Means a system's ability to cope with increased load.
  - Rather understand by definition we can consider questions like "If the system grows in a particular way, what are our options for coping with the growth?"
  - Load:
    - Load can be described by few numbers (bases on your system's architecture):
      1. Requests per second to a web server
      2. Ratio of reads to writes in a DB
      3. No. of simultaneously active users in chat room
      4. Hit rate on cache, etc.
    - More understanding read Twitter example in book
  - Performance:
    - Here we will look into what happens when load increases.
    - Latency vs Response time:
      - Response time => Time taken to display the data to client.
      - Latency => Duration that a request is waiting to be handled.
    - The appropriate metrics to calculate the response time of the system is median of all response time. (No to average response time)
    - Queueing delays are major reason of high response time.
    - Entire system will effect by delay if any one request is taking too much time.
  - **Approach for Coping with Load**:
    - Scaling Approach:
      1. Horizontal Scaling (Scaling Up) => Upgrading to a more powerful machine, useful but limited by costs.
      2. Horizontal Scaling (Scaling Out) => Distributing load across multiple smaller machines (shared-nothing architecture), often cost-effective and scalable.
    - Elastic Systems: Automatically adjust resources with load changes, ideal for unpredictable demand.
    - Manual Scaling: Simpler to manage but requires strategic planning to avoid operational issues.
    - Stateless services are easier to distribute, stateful systems (like databases) introduce complexity and are traditionally kept on single nodes until scaling is necessary.
    - There is no such thing as a generic, one-size-fits-all scalable architecture.
  3. **_Maintainability_**:
  - This is where the most amount of money is spend in maintaining the on-going services
  - We will pay particular attention to 3 design principles:
    1. Operability:
    - Focus on system reliability, scalability, and fault tolerance.
    - Includes monitoring, logging, and self-healing mechanisms to ensure smooth operation.
    - Ensures systems can handle high loads, recover from failure, and adapt to changing conditions.
    2. Simplicity:
    - Prioritize clean design and modular components for easier maintenance.
    - Simplify complexity by breaking down large systems into smaller, manageable parts.
    - Emphasize ease of understanding and modifying the system to reduce errors and improve agility.
    3. Evolvability:
    - Design system to adapt to changing requirements over time.
    - Focus on architectural flexibility and modular design for easy updates.
    - Use abstractions to isolate changes and maintain compatibility between components.
    - Plan for future modifications by anticipating potential changes in requirements or technology
