📘 MCQs – Performance Analysis, Latency, Threads, Queues & Percentiles
Batch 1: Foundations + Threading + Queues

1️⃣ Performance Analysis – Core Understanding
Q1. Performance analysis of a system primarily tries to understand:
 A. How much hardware cost can be reduced
 B. How system behaves when load changes
 C. How code quality improves
 D. How many bugs exist
✅ Answer: B

Q2. Which of the following BEST describes performance analysis?
 A. Measuring code complexity
 B. Observing system behavior under different loads
 C. Counting number of users
 D. Measuring only CPU usage
✅ Answer: B

2️⃣ Fixed Resources vs Fixed Performance
Q3. In fixed resources, increasing load, what remains constant?
 A. Response time
 B. Throughput
 C. Hardware resources
 D. Number of users
✅ Answer: C

Q4. If load increases but resources stay the same, what is MOST likely to happen first?
 A. System crashes immediately
 B. Response time increases
 C. Throughput becomes infinite
 D. CPU usage drops
✅ Answer: B

Q5. In fixed performance, increasing load, the system aims to:
 A. Reduce response time
 B. Keep response time constant
 C. Reduce number of servers
 D. Ignore latency
✅ Answer: B

Q6. To keep performance constant under higher load, what usually must be increased?
 A. Code comments
 B. Hardware/resources
 C. Request size
 D. Queue length
✅ Answer: B

3️⃣ Throughput vs Response Time
Q7. Throughput measures:
 A. Time taken by one request
 B. Number of requests processed per unit time
 C. Network delay
 D. CPU idle time
✅ Answer: B

Q8. Which statement is TRUE?
 A. High throughput always means low latency
 B. High throughput means system does more work
 C. Throughput and response time are identical
 D. Throughput measures waiting time
✅ Answer: B

Q9. A batch job completes in 5 minutes. This is an example of:
 A. Latency
 B. Response time
 C. Throughput
 D. Queueing delay
✅ Answer: C

4️⃣ Response Time Components
Q10. Response time visible to a user includes:
 A. Only processing time
 B. Only network delay
 C. Processing + network + queueing
 D. Only CPU execution
✅ Answer: C

Q11. A request waiting in line before execution contributes to:
 A. Throughput
 B. Latency
 C. Network bandwidth
 D. CPU cache
✅ Answer: B

Q12. Which component happens before actual processing starts?
 A. Network delay
 B. Queueing delay
 C. Service time
 D. Serialization
✅ Answer: B

5️⃣ Thread Pool & Queue Behavior
Q13. A server has 8 worker threads. 100 requests arrive at once. What happens?
 A. All 100 run in parallel
 B. 8 execute, 92 wait
 C. 100 go to CPU immediately
 D. System rejects all
✅ Answer: B

Q14. The waiting 92 requests are stored in:
 A. CPU cache
 B. Disk
 C. Request queue
 D. Network buffer
✅ Answer: C

Q15. Which resource actually limits true parallel execution?
 A. Number of threads
 B. Queue size
 C. CPU cores
 D. RAM size
✅ Answer: C

6️⃣ Concurrency vs Parallelism
Q16. True parallelism depends on:
 A. Thread count
 B. CPU cores
 C. Context switching
 D. Queue size
✅ Answer: B

Q17. A single CPU core running 4 threads uses:
 A. Parallelism
 B. Multiprocessing
 C. Time slicing
 D. Load balancing
✅ Answer: C

Q18. Why does too many threads hurt performance?
 A. Threads consume no memory
 B. Context switching cost increases
 C. CPU becomes faster
 D. Cache becomes infinite
✅ Answer: B

7️⃣ Context Switching & CPU Cache
Q19. Context switching causes performance degradation because:
 A. CPU executes faster
 B. CPU cache is invalidated
 C. Network bandwidth increases
 D. Threads disappear
✅ Answer: B

Q20. Which is a REAL consequence of excessive threads?
 A. Lower latency
 B. More parallelism than cores
 C. Higher queueing and latency
 D. Zero waiting time
✅ Answer: C

8️⃣ Real-Life Mapping (Exam Favorite)
Q21. In the bank analogy:
 Clerks ≈ ?
 A. Threads
 B. Customers
 C. CPU cores
 D. Queue
✅ Answer: C

Q22. Customers waiting in bank line represent:
 A. Network delay
 B. Queueing delay
 C. Throughput
 D. Cache miss
✅ Answer: B

Q23. “Threads give concurrency, CPU cores give parallelism” means:
 A. Threads control hardware
 B. Cores execute truly in parallel
 C. Threads always run simultaneously
 D. Queue is unnecessary
✅ Answer: B

🔥 Concept Check (Tricky)
Q24. A fast request arrives behind a slow request in queue. What happens?
 A. Fast request jumps queue
 B. Fast request waits
 C. Slow request is cancelled
 D. CPU reorders automatically
✅ Answer: B
👉 This explains why queues increase latency even for fast operations.

📌 Batch-1 Coverage Check
✅ Performance analysis
 ✅ Fixed load vs fixed performance
 ✅ Throughput vs response time
 ✅ Thread pools & queues
 ✅ CPU cores vs threads
 ✅ Concurrency vs parallelism
 ✅ Context switching
 ✅ Real-world analogy

👉 Should I continue?
If yes, next batches will cover:
Batch-2:
Latency vs Response Time (deep traps)


Average vs Median


Percentiles (p50, p90, p99)


Batch-3:
p99 vs p99.99


Large sample size logic


Monitoring time windows


Batch-4:
Amazon case study


Cost vs benefit trade-offs


Exam-style scenario questions


👉 Just reply “Continue” and I’ll keep going until every real-world concept is drilled 💯
Continue
Perfect 👍
 Continuing exactly where we left off.

📘 MCQs – Performance Analysis & Latency
Batch 2: Latency vs Response Time, Averages, Median, Percentiles (Core Exam Traps)

9️⃣ Latency vs Response Time (VERY IMPORTANT)
Q25. Latency refers to:
 A. Total time user waits for response
 B. Time request spends waiting before processing
 C. Only network delay
 D. Only processing time
✅ Answer: B

Q26. Response time includes:
 A. Only latency
 B. Only service time
 C. Latency + processing + network delay
 D. Queueing delay only
✅ Answer: C

Q27. Which statement is CORRECT?
 A. Latency = Response Time
 B. Latency is part of response time
 C. Response time is part of latency
 D. Latency is always zero
✅ Answer: B

Q28. A request is waiting for CPU while another thread is executing. This waiting time is:
 A. Network delay
 B. Throughput
 C. Latency
 D. Service time
✅ Answer: C

Q29. From a user’s perspective, which metric matters MOST?
 A. Latency
 B. CPU utilization
 C. Response time
 D. Thread count
✅ Answer: C

🔟 Average Response Time – Why It Misleads
Q30. Average response time is calculated as:
 A. Fastest request
 B. Slowest request
 C. Sum of response times ÷ number of requests
 D. Median request time
✅ Answer: C

Q31. Why is average response time misleading?
 A. It ignores slow requests
 B. It hides distribution of delays
 C. It always shows worst case
 D. It ignores fast requests
✅ Answer: B

Q32. If 99 requests take 100 ms and 1 request takes 10 seconds, average response time will be:
 A. Close to 100 ms
 B. Close to 10 seconds
 C. Somewhere in between, hiding the spike
 D. Exactly median
✅ Answer: C

Q33. Which metric best represents typical user experience?
 A. Average
 B. Maximum
 C. Median (p50)
 D. Minimum
✅ Answer: C

1️⃣1️⃣ Median (p50) – Concept Clarity
Q34. Median response time means:
 A. All users get this response time
 B. 50% requests faster, 50% slower
 C. Slowest request
 D. Average of fastest and slowest
✅ Answer: B

Q35. Median is also called:
 A. p90
 B. p99
 C. p50
 D. p100
✅ Answer: C

Q36. Median is preferred over average because:
 A. It is easier to compute
 B. It ignores extreme outliers
 C. It shows worst case
 D. It shows only slow requests
✅ Answer: B

1️⃣2️⃣ Percentiles – Foundation
Q37. Percentile means:
 A. Percentage of slow requests
 B. Fastest request time
 C. Boundary below which a percentage of requests fall
 D. Average latency
✅ Answer: C

Q38. 99th percentile means:
 A. Slowest request
 B. Fastest request
 C. 99% requests are faster than this value
 D. Exactly 99 requests
✅ Answer: C

Q39. Which statement is TRUE?
 A. p99 is the slowest request
 B. p99 ignores the slowest requests beyond it
 C. p99 represents average latency
 D. p99 is always unacceptable
✅ Answer: B

1️⃣3️⃣ Percentile Table Reasoning (Classic Exam Trap)
Q40. You have 100 requests sorted by response time.
 p99 corresponds to which request?
 A. 100th
 B. 99th
 C. 1st
 D. Average
✅ Answer: B

Q41. If p99 = 1 second, what does it mean?
 A. All requests take 1 second
 B. Slowest request takes 1 second
 C. 99% requests are faster than 1 second
 D. 1% requests are faster than 1 second
✅ Answer: C

Q42. One request takes 5 seconds. p99 is 1 second. Which is correct?
 A. That request is p99
 B. That request is above p99
 C. p99 is wrong
 D. Median is wrong
✅ Answer: B

1️⃣4️⃣ Large Sample Size Logic
Q43. Percentiles are meaningful only when:
 A. Request count is very small
 B. Sample size is large
 C. CPU usage is low
 D. Threads are few
✅ Answer: B

Q44. Why is calculating p99 on just 100 requests unstable?
 A. Sorting is slow
 B. One slow request distorts results
 C. Median disappears
 D. CPU cache clears
✅ Answer: B

Q45. In real systems, p99 is usually calculated over:
 A. 10 requests
 B. 100 requests
 C. Thousands or millions of requests
 D. Only failed requests
✅ Answer: C

🔥 Conceptual Scenario (Very Important)
Q46. Monitoring shows:
p50 = 200 ms


p99 = 1.2 s


Which conclusion is CORRECT?
 A. System is totally broken
 B. Majority users are slow
 C. Most users are fast, few are slow
 D. All users see 1.2 s
✅ Answer: C
Batch 3: p99 vs p99.99, Boundaries, Large-Scale Reality

1️⃣5️⃣ p99 vs “Slow Request” (BIGGEST CONFUSION)
Q47. p99 represents:
 A. The slowest request
 B. The fastest request
 C. The boundary after which 1% requests are slower
 D. The average of slow requests
✅ Answer: C

Q48. Which statement is FALSE?
 A. p99 is a boundary
 B. p99 represents slowest request
 C. p99 ignores requests slower than it
 D. p99 needs large sample size
✅ Answer: B

Q49. If p99 = 800 ms, how many requests are slower than this in 10,000 requests?
 A. 1
 B. 10
 C. 100
 D. 1,000
✅ Answer: C

1️⃣6️⃣ p99 in Large Traffic Systems
Q50. In a system processing 1,000,000 requests per minute, p99 affects approximately:
 A. 1 request
 B. 10 requests
 C. 1,000 requests
 D. 10,000 requests
✅ Answer: C

Q51. Why is p99 important in high-traffic systems?
 A. It affects rare users only
 B. It affects a meaningful number of users
 C. It measures only CPU performance
 D. It ignores queues
✅ Answer: B

1️⃣7️⃣ p99.99 – Extreme Tail Latency
Q52. p99.99 means:
 A. 99.99 requests
 B. Slowest request
 C. Boundary below which 99.99% requests fall
 D. Median response time
✅ Answer: C

Q53. In 10,000 requests, p99.99 ignores:
 A. 100 requests
 B. 10 requests
 C. 1 request
 D. 0 requests
✅ Answer: C

Q54. Which is TRUE about p99.99?
 A. Happens frequently
 B. Represents common user experience
 C. Represents extremely rare slow cases
 D. Should always be optimized first
✅ Answer: C

1️⃣8️⃣ Comparing p99 vs p99.99
Q55. Improving p99 latency will benefit:
 A. Almost no users
 B. Only test users
 C. A large group of users
 D. Only monitoring dashboards
✅ Answer: C

Q56. Improving p99.99 latency usually:
 A. Has huge ROI
 B. Is cheap
 C. Is expensive with little benefit
 D. Fixes average latency
✅ Answer: C

Q57. Which percentile should MOST businesses focus on first?
 A. p100
 B. p99.99
 C. p50 / p90 / p99
 D. Maximum latency
✅ Answer: C

1️⃣9️⃣ Boundary Logic (Exam Favorite)
Q58. p99 is called “slowest 1 out of 100” because:
 A. It is the slowest request
 B. It defines where top 1% begin
 C. It ignores 99 requests
 D. It measures slow requests only
✅ Answer: B

Q59. Which analogy best explains percentiles?
 A. Average salary
 B. Exam ranks
 C. CPU cache
 D. Disk I/O
✅ Answer: B

Q60. If a student is in the 99th percentile in an exam, it means:
 A. They are last
 B. They are average
 C. Only 1% students scored higher
 D. They scored full marks
✅ Answer: C

2️⃣0️⃣ Stability & Sample Size
Q61. Why monitoring tools aggregate data over time windows?
 A. To reduce storage
 B. To hide problems
 C. To stabilize percentile calculations
 D. To slow dashboards
✅ Answer: C

Q62. Which window gives BEST real-time alerting?
 A. 1 hour
 B. 30 minutes
 C. 1 minute
 D. 1 day
✅ Answer: C

Q63. Which window is BEST for trend analysis?
 A. 1 second
 B. 1 minute
 C. 5 minutes
 D. Per request
✅ Answer: C

🔥 Scenario Question (Very Important)
Q64. Dashboard shows:
Last 1 min p99 = 300 ms


Last 5 min p99 = 500 ms


What does this indicate?
 A. System improved
 B. Temporary spike resolved
 C. Latency trending worse
 D. Monitoring bug
✅ Answer: C
Batch 4: Aggregation, Dashboards, Alerts, Real-Life Reasoning

2️⃣1️⃣ Why Time Windows Exist
Q65. Monitoring systems use time windows mainly to:
 A. Reduce CPU usage
 B. Hide individual request details
 C. Aggregate data for stability
 D. Slow down alerting
✅ Answer: C

Q66. Which is the BIGGEST problem with per-request monitoring?
 A. Too accurate
 B. Very noisy and misleading
 C. Uses too much disk
 D. Hard to compute percentiles
✅ Answer: B

Q67. Which window size is MOST useful for real-time incident detection?
 A. 1 second
 B. 1 minute
 C. 1 hour
 D. 1 day
✅ Answer: B

2️⃣2️⃣ Noise vs Signal (Critical Thinking)
Q68. A single slow request causes a spike in a graph. This is called:
 A. Trend
 B. Signal
 C. Noise
 D. Failure
✅ Answer: C

Q69. Time-window aggregation helps by:
 A. Eliminating all slow requests
 B. Highlighting meaningful patterns
 C. Increasing latency
 D. Hiding real failures
✅ Answer: B

Q70. Which situation MOST likely indicates a real problem?
 A. One-second spike in p99
 B. Gradual p99 increase over 5–10 minutes
 C. One slow request
 D. Random fluctuation
✅ Answer: B

2️⃣3️⃣ Multi-Window Reasoning (Exam Favorite)
Q71. Monitoring shows:
1 min p99 = 600 ms


5 min p99 = 300 ms


What does this mean?
 A. System permanently degraded
 B. A temporary spike occurred
 C. System is failing
 D. CPU is overloaded
✅ Answer: B

Q72. Monitoring shows:
1 min p99 = 300 ms


5 min p99 = 500 ms


What should an engineer suspect?
 A. Metrics bug
 B. Recovering system
 C. Increasing load
 D. Network fixed
✅ Answer: C

2️⃣4️⃣ Alerting Logic
Q73. Best alert condition for latency issues is:
 A. Single request failure
 B. p99 spike over 5 minutes
 C. Average latency increase for 1 second
 D. CPU usage spike for 1 ms
✅ Answer: B

Q74. Why should alerts NOT be triggered on averages?
 A. Averages are hard to compute
 B. Averages hide tail latency
 C. Averages show only worst case
 D. Averages ignore throughput
✅ Answer: B

Q75. Which metric is MOST suitable for SLOs?
 A. Maximum latency
 B. Average latency
 C. p50 / p90 / p99
 D. CPU utilization
✅ Answer: C

2️⃣5️⃣ Real-World Dashboard Interpretation
Q76. Dashboard shows:
p50 = 100 ms


p90 = 140 ms


p99 = 900 ms


What is the CORRECT interpretation?
 A. All users are slow
 B. Most users are fast, few suffer
 C. System is idle
 D. Network is down
✅ Answer: B

Q77. If p50 suddenly degrades but p99 remains stable, what is likely happening?
 A. Rare edge cases
 B. System-wide slowdown
 C. One slow request
 D. Cache miss
✅ Answer: B

2️⃣6️⃣ Real-Life Analogy (Stock Market)
Q78. Per-request monitoring is similar to:
 A. Yearly stock average
 B. Monthly stock trend
 C. Tick-by-tick stock price
 D. Market cap
✅ Answer: C

Q79. Time-window percentiles are similar to:
 A. Random noise
 B. Daily/weekly stock trends
 C. CPU interrupts
 D. Context switching
✅ Answer: B

🔥 Scenario (Very Important)
Q80. Monitoring shows stable p99 for 1 hour, but frequent short spikes in 1-minute windows. What should be done?
 A. Scale immediately
 B. Ignore entirely
 C. Observe trend, avoid panic
 D. Rewrite code
✅ Answer: C
2️⃣7️⃣ Amazon Percentile Case Study (Core Understanding)
Q81. Amazon latency metrics:
p50 = 100 ms


p90 = 150 ms


p99 = 300 ms


p99.99 = 5 seconds


Which percentile affects MOST users?
 A. p99.99
 B. p99
 C. p90 / p50
 D. Maximum latency
✅ Answer: C

Q82. p99.99 = 5 seconds means:
 A. All users wait 5 seconds
 B. Most users wait 5 seconds
 C. 0.01% users wait ~5 seconds
 D. System is broken
✅ Answer: C

2️⃣8️⃣ Cost vs Benefit (REAL Engineering Decision)
Q83. Improving p99.99 latency usually requires:
 A. Minor code change
 B. No cost
 C. Significant infra + engineering cost
 D. Only monitoring
✅ Answer: C

Q84. Why is improving p99.99 often NOT worth it?
 A. Easy to fix later
 B. Affects very few users
 C. Improves revenue drastically
 D. No engineering effort required
✅ Answer: B

Q85. Amazon serves 10 million requests/day.
 p99.99 affects approximately how many users/day?
 A. 10
 B. 100
 C. 1,000
 D. 100,000
✅ Answer: C

2️⃣9️⃣ ROI-Based Optimization
Q86. Improving p90 latency will benefit:
 A. Almost no users
 B. Majority of users
 C. Only edge cases
 D. Only dashboards
✅ Answer: B

Q87. Which optimization gives MAXIMUM ROI?
 A. p99.99 → p99.9
 B. p99 → p50
 C. p50 / p90 improvements
 D. Maximum latency
✅ Answer: C

Q88. Which graph best represents optimization ROI?
 A. Linear increase
 B. Exponential benefit
 C. Diminishing returns
 D. Constant benefit
✅ Answer: C

3️⃣0️⃣ Real Causes of Extreme Tail Latency
Q89. Which is a COMMON cause of p99.99 latency spikes?
 A. Syntax error
 B. Network hiccup
 C. Compilation error
 D. Missing semicolon
✅ Answer: B

Q90. JVM “Stop-the-world” GC pause contributes to:
 A. Throughput increase
 B. Tail latency
 C. CPU parallelism
 D. Queue elimination
✅ Answer: B

Q91. Why are p99.99 issues hard to permanently fix?
 A. They happen frequently
 B. They are deterministic
 C. They are rare & hard to reproduce
 D. They affect all users
✅ Answer: C

3️⃣1️⃣ Smart Engineering Rule (INTERVIEW GOLD)
Q92. “Stop where cost > benefit” means:
 A. Never optimize
 B. Always optimize everything
 C. Optimize until ROI makes sense
 D. Ignore performance
✅ Answer: C

Q93. Which is the BEST engineering focus order?
 A. p99.99 → p99 → p50
 B. p50 → p90 → p99
 C. Maximum → average
 D. CPU → memory → disk
✅ Answer: B

3️⃣2️⃣ Decision-Making Scenarios (Very Important)
Q94. p50 suddenly increases by 100 ms. What happens to business metrics?
 A. Almost no impact
 B. Minor impact
 C. Significant impact
 D. No users affected
✅ Answer: C

Q95. p99.99 improves from 5s to 4s. What happens?
 A. Huge revenue gain
 B. All users happier
 C. Very small impact
 D. System becomes faster
✅ Answer: C

Q96. If budget is limited, where should effort go FIRST?
 A. Extreme tail latency
 B. Rare edge cases
 C. Common path optimization
 D. Monitoring visuals
✅ Answer: C

3️⃣3️⃣ Ultimate Reality Check
Q97. Why do big companies publish p99 SLAs instead of p99.99?
 A. Marketing trick
 B. Easier to calculate
 C. Better cost–benefit balance
 D. p99.99 is impossible
✅ Answer: C

Q98. Which statement best defines “smart performance engineering”?
 A. Optimize everything
 B. Optimize nothing
 C. Optimize where it matters
 D. Chase worst case always
✅ Answer: C

🔥 FINAL MASTER QUESTION
Q99. Your system has:
Excellent p50


Acceptable p99


Rare p99.99 spikes


What should you do?
 A. Panic and redesign
 B. Ignore monitoring
 C. Focus on p99/p50, monitor tail
 D. Rewrite system
✅ Answer: C
Chapter 5 part 2 

📘 MCQs – SLA, Tail Latency & Distributed Systems
Batch 1: SLA Fundamentals + Business Thinking

1️⃣ SLA Basics (Foundation)
Q1. SLA (Service Level Agreement) is BEST described as:
 A. Internal engineering document
 B. Marketing slogan
 C. A contract defining minimum guarantees
 D. A debugging tool
✅ Answer: C

Q2. SLA primarily defines guarantees related to:
 A. Code quality
 B. Developer productivity
 C. User-visible performance & reliability
 D. Deployment speed
✅ Answer: C

Q3. SLA answers which core question?
 A. How fast is the CPU?
 B. How many threads exist?
 C. What minimum experience user is guaranteed?
 D. How much traffic system can handle?
✅ Answer: C

2️⃣ SLA Metrics (Very Important)
Q4. Which of the following is NOT typically part of an SLA?
 A. Response time
 B. Availability
 C. Error rate
 D. Code complexity
✅ Answer: D

Q5. Availability SLA of 99.9% means:
 A. Service is always up
 B. Service can be down ~0.1% of time
 C. Service is slow 0.1% of time
 D. Errors are allowed 0.1%
✅ Answer: B

Q6. Why do companies avoid extremely strict SLAs?
 A. Users don’t care
 B. Engineering cost explodes
 C. Monitoring becomes hard
 D. CPUs become slower
✅ Answer: B

3️⃣ SLA = Balance (Business + Engineering)
Q7. SLA is a balance between:
 A. Speed and correctness
 B. User expectations and engineering cost
 C. Throughput and latency
 D. Hardware and software
✅ Answer: B

Q8. What happens if SLA is too loose?
 A. System cost reduces
 B. User experience degrades
 C. Engineering becomes easy
 D. Tail latency disappears
✅ Answer: B

Q9. What happens if SLA is too strict?
 A. Better UX at low cost
 B. No impact
 C. Over-engineering & high cost
 D. Less monitoring needed
✅ Answer: C

4️⃣ Percentiles Inside SLA (Critical)
Q10. Amazon-style SLA usually guarantees:
 A. Max latency
 B. Average latency
 C. Median + p99
 D. p99.99 only
✅ Answer: C

Q11. Why don’t companies usually guarantee p99.99?
 A. Hard to calculate
 B. Affects too many users
 C. Extremely expensive to meet
 D. Users demand it
✅ Answer: C

Q12. If SLA guarantees only 99% of requests, then slowest 1%:
 A. Violates SLA
 B. Is acceptable by contract
 C. Causes penalty
 D. Must be optimized
✅ Answer: B

5️⃣ Distributed Request Reality
Q13. In modern systems, a single user request usually:
 A. Hits only one service
 B. Hits one database
 C. Fans out to multiple services
 D. Is processed synchronously only
✅ Answer: C

Q14. Final end-user response time depends MOST on:
 A. Fastest service
 B. Average service latency
 C. Slowest component
 D. Network bandwidth
✅ Answer: C

Q15. Even if 9 services are fast and 1 is slow, the user sees:
 A. Fast response
 B. Partial response
 C. Slow response
 D. Cached response
✅ Answer: C

6️⃣ Tail Latency Amplification (Core Concept)
Q16. If three services each have p99 = 100 ms, overall system p99 will be:
 A. Still ~100 ms
 B. Slightly better
 C. Worse than individual services
 D. Zero
✅ Answer: C

Q17. Why does tail latency amplify in fan-out systems?
 A. CPU gets faster
 B. Probabilities multiply
 C. Threads disappear
 D. Cache grows
✅ Answer: B

Q18. If a request fans out to 10 services with p99 = 99%, overall success rate is closest to:
 A. 99%
 B. 95%
 C. 90%
 D. 50%
✅ Answer: C

🔥 Key Insight Question
Q19. Even if every service is “healthy”, the system can still feel slow because:
 A. Monitoring bug
 B. Network is down
 C. Tail latency amplification
 D. SLA is wrong
✅ Answer: C
Batch 2: Queueing Delay, Thread Pools & Hidden Latency

7️⃣ Queueing Delay – Core Understanding
Q20. Queueing delay means:
 A. Time taken to execute code
 B. Time request waits before processing starts
 C. Network transmission time
 D. Disk read time
✅ Answer: B

Q21. Queueing delay usually happens when:
 A. CPU is idle
 B. Resources are immediately available
 C. Requests arrive faster than they are processed
 D. Network latency is zero
✅ Answer: C

Q22. Which component MOST commonly creates queueing delay in web apps?
 A. Database disk
 B. Thread pool
 C. Cache
 D. Load balancer DNS
✅ Answer: B

8️⃣ Thread Pool Reality (Very Important)
Q23. A server has 8 worker threads. 100 requests arrive together. What happens?
 A. All requests execute immediately
 B. 8 execute, 92 wait in queue
 C. All requests fail
 D. CPU spawns more cores
✅ Answer: B

Q24. Even if processing time is only 50 ms, response time can be seconds because of:
 A. Slow CPU
 B. Queueing delay
 C. Garbage code
 D. Network congestion only
✅ Answer: B

Q25. Which statement is TRUE?
 A. Fast processing guarantees fast response
 B. Queueing delay does not affect latency
 C. Queueing delay adds directly to response time
 D. Queueing happens only in Kafka
✅ Answer: C

9️⃣ Internal vs External Queues
Q26. Which is an example of an internal queue?
 A. Kafka topic
 B. RabbitMQ queue
 C. ExecutorService queue
 D. SQS
✅ Answer: C

Q27. Which queue is usually intentional in system design?
 A. Thread pool queue
 B. CPU run queue
 C. Kafka / messaging queue
 D. JVM lock queue
✅ Answer: C

Q28. Why is internal queueing more dangerous than external queueing?
 A. Uses more memory
 B. Blocks user-facing threads
 C. Is slower
 D. Is visible in logs
✅ Answer: B

🔟 Queue Growth → Latency Explosion
Q29. A server can handle 100 req/sec. Suddenly 300 req/sec arrive. What happens?
 A. CPU speeds up
 B. All requests process in parallel
 C. Queue grows rapidly
 D. Requests auto-drop
✅ Answer: C

Q30. 200 queued requests × 50 ms processing time means waiting ≈
 A. 1 second
 B. 2 seconds
 C. 5 seconds
 D. 10 seconds
✅ Answer: D

Q31. User perceives the system as slow mainly because of:
 A. Processing time
 B. Queueing delay
 C. Cache hit
 D. Thread creation
✅ Answer: B

1️⃣1️⃣ Latency Amplification via Queueing (CRITICAL)
Q32. What happens when a few slow requests occupy worker threads?
 A. Nothing
 B. Queue shrinks
 C. Fast requests also wait
 D. CPU adds cores
✅ Answer: C

Q33. This effect is called:
 A. Load shedding
 B. Latency amplification
 C. Throughput scaling
 D. Parallelism
✅ Answer: B

Q34. Which percentiles are MOST affected by queueing delay?
 A. p50
 B. p90
 C. p95 / p99
 D. Minimum latency
✅ Answer: C

1️⃣2️⃣ Failure Feedback Loop (Exam Favorite)
Q35. Correct sequence during overload is:
 A. Fast requests → slow requests → queues shrink
 B. Slow requests → thread blocking → queue growth → latency spike
 C. Queue growth → CPU idle → recovery
 D. Cache hit → latency spike
✅ Answer: B

Q36. Why do “fast” requests appear slow during overload?
 A. Code becomes slower
 B. CPU cache clears
 C. They wait behind slow ones
 D. Network reroutes
✅ Answer: C

🔥 Analogy Question (Bank)
Q37. One customer taking long time at counter causes:
 A. Only that customer delayed
 B. Clerk duplication
 C. Queue delay for everyone
 D. Faster service later
✅ Answer: C

1️⃣3️⃣ SLA Impact of Queueing
Q38. Queueing delay primarily hurts which SLA metric?
 A. Availability
 B. Error rate
 C. Latency / response time
 D. Throughput definition
✅ Answer: C

Q39. Which SLA is MOST likely to be violated first under overload?
 A. Availability
 B. p50 latency
 C. p99 latency
 D. Error rate
✅ Answer: C

🔥 Scenario (Real-World Thinking)
Q40. System meets p50 SLA but violates p99. What is MOST likely happening?
 A. CPU idle
 B. Rare slow requests + queueing
 C. Monitoring bug
 D. Network outage
✅ Answer: B
Batch 3: Microservices Reality + Probability Traps

1️⃣4️⃣ Fan-out – Core Meaning
Q41. Fan-out in distributed systems means:
 A. Scaling CPU cores
 B. Sending one request to many downstream services
 C. Increasing thread pool size
 D. Caching responses
✅ Answer: B

Q42. Fan-out usually happens when:
 A. Request is cached
 B. System is monolithic
 C. Request aggregates data from multiple services
 D. CPU is idle
✅ Answer: C

Q43. Which architecture is MOST prone to fan-out latency issues?
 A. Single monolith
 B. Batch system
 C. Microservices
 D. Static website
✅ Answer: C

1️⃣5️⃣ Slowest Component Rule (VERY IMPORTANT)
Q44. Final response time of a fan-out request is decided by:
 A. Average latency
 B. Fastest service
 C. Slowest service
 D. Median service
✅ Answer: C

Q45. If 9 services respond in 50 ms and 1 responds in 800 ms, user sees:
 A. ~50 ms
 B. ~100 ms
 C. ~800 ms
 D. Average
✅ Answer: C

1️⃣6️⃣ Probability Trap (EXAM FAVORITE)
Q46. Three services each meet p99 SLA. Overall success probability is closest to:
 A. 99%
 B. 98%
 C. 97%
 D. 95%
✅ Answer: C

Q47. Why does 0.99 × 0.99 × 0.99 ≠ 0.99?
 A. Threads block
 B. CPU cache invalidates
 C. Probabilities multiply
 D. Monitoring error
✅ Answer: C

Q48. What is this effect called?
 A. Queueing collapse
 B. Tail latency amplification
 C. Load shedding
 D. Retry storm
✅ Answer: B

1️⃣7️⃣ More Services = Worse Tail
Q49. A request fans out to 10 services (each p99 = 99%). Overall success ≈
 A. 99%
 B. 95%
 C. 90%
 D. 80%
✅ Answer: C

Q50. Even if no service is broken, system can still feel slow because:
 A. CPU is slow
 B. Network always fails
 C. Tail latency multiplies
 D. Cache is disabled
✅ Answer: C

1️⃣8️⃣ SLA Illusion
Q51. “All services meet SLA” but users complain. Why?
 A. SLA is fake
 B. SLA is per-service, not end-to-end
 C. Monitoring is wrong
 D. Users exaggerate
✅ Answer: B

Q52. End-to-end SLA is usually:
 A. Better than individual SLAs
 B. Same as individual SLAs
 C. Worse than individual SLAs
 D. Independent
✅ Answer: C

1️⃣9️⃣ Microservices Reality Check
Q53. Which statement is TRUE?
 A. Microservices always improve latency
 B. More services = more reliability
 C. More services increase tail latency risk
 D. Fan-out has no cost
✅ Answer: C

Q54. Which type of request is MOST dangerous?
 A. Single DB lookup
 B. Cached read
 C. Large parallel fan-out read
 D. Static file read
✅ Answer: C

🔥 Scenario (Very Important)
Q55. Your request fans out to 20 services. Each meets p99 SLA.
 Yet p99 of system is terrible. Best explanation?
 A. Monitoring bug
 B. Network failure
 C. Probability + fan-out amplification
 D. Garbage collection
✅ Answer: C
Batch 4: The REAL Fix for Tail Latency

2️⃣0️⃣ Limiting Fan-out – What It REALLY Means
Q56. “Limiting fan-out” primarily means:
 A. Blocking requests after N services
 B. Showing fewer results to the user
 C. Designing requests to depend on fewer downstream services
 D. Increasing thread pool size
✅ Answer: C

Q57. Which interpretation of Top-K is WRONG?
 A. Fetch only most relevant data
 B. Avoid calling unnecessary services
 C. Call all services but display only top 50 results
 D. Reduce dependency graph at read time
✅ Answer: C

Q58. Why does “call all services but show top-50” NOT reduce latency?
 A. Sorting is expensive
 B. UI is slow
 C. Fan-out still happens
 D. Cache is missing
✅ Answer: C

2️⃣1️⃣ Read-Time Dependency vs Precomputation
Q59. The MOST dangerous time to do heavy fan-out is:
 A. Background processing
 B. Batch jobs
 C. User read-time
 D. Cache warm-up
✅ Answer: C

Q60. Precomputation reduces tail latency because it:
 A. Uses faster CPUs
 B. Eliminates queues
 C. Moves heavy work off the critical path
 D. Removes databases
✅ Answer: C

Q61. Which is TRUE about precomputation?
 A. It blocks user threads
 B. It is synchronous
 C. It runs asynchronously
 D. It increases fan-out at read time
✅ Answer: C

2️⃣2️⃣ Twitter Home Timeline (Design Logic)
Q62. Why doesn’t Twitter fetch all follower tweets at read time?
 A. Followers are offline
 B. Databases are slow
 C. Fan-out would explode latency
 D. UI limitation
✅ Answer: C

Q63. Twitter’s home feed read request typically depends on:
 A. All follower services
 B. Cached precomputed timeline
 C. Every tweet ever posted
 D. Live joins across services
✅ Answer: B

Q64. Heavy work in Twitter timeline is done:
 A. During read request
 B. During write / background processing
 C. During UI rendering
 D. During scroll
✅ Answer: B

2️⃣3️⃣ Async vs Sync (Critical Difference)
Q65. Why is async fan-out safer than sync fan-out?
 A. Async is faster
 B. Async blocks fewer threads
 C. Async has no queues
 D. Async avoids databases
✅ Answer: B

Q66. Which operation BLOCKS user response?
 A. Background worker
 B. Precomputation
 C. Synchronous downstream call
 D. Cache refresh
✅ Answer: C

2️⃣4️⃣ Amazon “Buy Now” Mental Model
Q67. When you click “Buy Now”, Amazon MOSTLY does:
 A. Search all warehouses
 B. Query all services live
 C. Lookup pre-indexed data
 D. Run batch jobs
✅ Answer: C

Q68. Why does Amazon pre-index inventory & routes?
 A. To reduce storage
 B. To avoid runtime fan-out
 C. To increase complexity
 D. To slow reads
✅ Answer: B

2️⃣5️⃣ Infinite Scroll & Partial Fetch
Q69. Infinite scroll reduces latency because:
 A. User waits longer
 B. Data is fetched in chunks
 C. All data is fetched at once
 D. UI hides latency
✅ Answer: B

Q70. Next-page data is usually fetched:
 A. Synchronously at scroll end
 B. Before user reaches the end
 C. After user closes app
 D. Only on refresh
✅ Answer: B

🔥 Key Insight Question (VERY IMPORTANT)
Q71. Which design MOST effectively reduces tail latency?
 A. More threads
 B. Faster CPU
 C. Less read-time dependency
 D. Bigger queues
✅ Answer: C
Batch 5 (FINAL): Graceful Degradation, Timeouts, Hedging & Resilience

2️⃣6️⃣ Graceful Degradation (VERY IMPORTANT)
Q72. Graceful degradation means:
 A. System completely fails on error
 B. System slows down but shows error
 C. System continues with reduced features
 D. System retries forever
✅ Answer: C

Q73. Why is graceful degradation powerful?
 A. It hides bugs
 B. It reduces infrastructure cost
 C. It prevents tail latency from becoming user-visible failure
 D. It removes queues
✅ Answer: C

Q74. If “Recommendations” are slow on Amazon, best action is to:
 A. Block checkout
 B. Retry recommendations forever
 C. Hide recommendations, allow purchase
 D. Fail entire page
✅ Answer: C

2️⃣7️⃣ Graceful Degradation – Real Impact
Q75. Graceful degradation primarily protects which SLA?
 A. Throughput
 B. Availability
 C. Error rate
 D. Code quality
✅ Answer: B

Q76. Which feature is MOST suitable for graceful degradation?
 A. Payment
 B. Authentication
 C. Recommendations / likes count
 D. Order confirmation
✅ Answer: C

2️⃣8️⃣ Timeouts (ABSOLUTELY CRITICAL)
Q77. Why are timeouts essential in distributed systems?
 A. To increase latency
 B. To stop waiting on slow dependencies
 C. To reduce CPU usage
 D. To improve caching
✅ Answer: B

Q78. What happens if timeouts are NOT set?
 A. Faster responses
 B. Threads can block indefinitely
 C. SLA improves
 D. Queue shrinks
✅ Answer: B

Q79. Timeouts primarily protect against:
 A. Fast services
 B. Tail latency amplification
 C. CPU parallelism
 D. Cache hits
✅ Answer: B

2️⃣9️⃣ Hedged Requests (Advanced but Important)
Q80. Hedged requests mean:
 A. Retry only after failure
 B. Send request to multiple replicas and take fastest
 C. Increase timeout
 D. Disable retries
✅ Answer: B

Q81. Hedged requests help reduce:
 A. Average latency
 B. Median latency
 C. Tail latency
 D. Throughput
✅ Answer: C

Q82. Hedged requests are MOST useful when:
 A. All replicas are slow
 B. Occasional replicas are slow
 C. System is idle
 D. Cache is disabled
✅ Answer: B

3️⃣0️⃣ Circuit Breakers
Q83. Circuit breaker pattern is used to:
 A. Retry endlessly
 B. Protect slow or failing services
 C. Increase fan-out
 D. Improve CPU cache
✅ Answer: B

Q84. When a circuit breaker is OPEN:
 A. Requests flow normally
 B. Requests are blocked or short-circuited
 C. Queue grows
 D. Threads multiply
✅ Answer: B

Q85. Circuit breakers help prevent:
 A. Slow code
 B. Retry storms and cascading failures
 C. Cache misses
 D. Load balancing
✅ Answer: B

3️⃣1️⃣ Bulkheads (Isolation Principle)
Q86. Bulkhead pattern means:
 A. Shared resources for all
 B. Isolating resources between components
 C. Increasing thread pool size
 D. Removing queues
✅ Answer: B

Q87. Why are bulkheads important?
 A. Faster CPU
 B. Prevent one slow component from taking down others
 C. Reduce network hops
 D. Increase throughput
✅ Answer: B

3️⃣2️⃣ Caching & Async Processing
Q88. Caching helps tail latency because it:
 A. Increases fan-out
 B. Avoids repeated heavy work
 C. Increases memory pressure
 D. Adds queueing
✅ Answer: B

Q89. Async processing is preferred because it:
 A. Blocks user threads
 B. Improves readability
 C. Keeps user-facing path short
 D. Always faster
✅ Answer: C

3️⃣3️⃣ Ultimate Trade-off Questions (INTERVIEW GOLD)
Q90. Which fix gives the BIGGEST real-world benefit?
 A. Increase threads
 B. Improve p99.99
 C. Reduce read-time fan-out
 D. Rewrite everything
✅ Answer: C

Q91. Which is the MOST dangerous situation?
 A. One slow request
 B. No cache
 C. Unbounded queues + no timeouts
 D. Limited CPU
✅ Answer: C

🔥 FINAL SYSTEM DESIGN SCENARIO
Q92. Your system shows:
p50 good


p99 bad


No errors


What is MOST likely happening?
 A. CPU failure
 B. Queueing + tail amplification
 C. Monitoring bug
 D. Network down
✅ Answer: B

Q93. BEST response as a senior engineer?
 A. Add more threads
 B. Increase timeouts
 C. Reduce fan-out + add timeouts
 D. Ignore tail latency
✅ Answer: C

🧠 FINAL MASTER QUESTION
Q94. Which statement BEST summarizes real-world performance engineering?
 A. Optimize worst case first
 B. Averages matter most
 C. Control tail latency on critical path
 D. Faster hardware solves everything
✅ Answer: C

