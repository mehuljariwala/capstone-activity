1. Eventual Consistency
   
  - Direct Impact: When data is updated on the write side (command model), those changes are not instantly  visible on the read side (query model). The read model updates only after it consumes the events that represent these changes.
  
  - Example: If a video title is updated, the read model will continue to show the old title until it processes the VideoUpdated event.

2. Performance
  
  - Resource Allocation: Write operations can be resource-intensive, especially if they involve complex validations or multiple data manipulations. This can consume substantial CPU, memory, and I/O resources, potentially slowing down the system, including the parts handling read operations.
  
  - Database Load: If both the read and write models share the same underlying database system (even if they use different schemas or tables), heavy write operations could impact database performance, affecting read operation speed.

3. Data Locking (In Non-CQRS Systems)
  - While this is not typically a concern in a properly implemented CQRS system due to the physical/logical separation of command and query responsibilities, in traditional systems, write operations could lock data records, preventing them from being read until the write operation is complete.

