1. In online learning, you train the system incrementally by feeding it data instances sequentially, either individually or in small groups called mini-batches.
2. Each learning step is fast and cheap, so the system can learn about new data on the fly as it arrives.
   ![[Pasted image 20250805184139.png]]
3. Best for devices with limited computing resources.
4. it can also be used to train model on huge datasets that cannot fit in one machine's main memory(this is called out-of-core learning).
   ![[Pasted image 20250805184157.png]]


## Cons
1. If bad data is fed to the system, the system's performance will decline, possibly quickly(depending on the data quality and learning rate).