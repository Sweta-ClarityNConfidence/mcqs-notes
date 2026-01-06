📘 MCQs – Understanding Load, Traffic & System Design
Batch 1: Current Load, Load Parameters & Why They Matter

1️⃣ Why Understanding Current Load Matters
Q1. Why must you understand the current load before scaling a system?
 A. To reduce code complexity
 B. To predict future bugs
 C. To know how the system behaves today under traffic
 D. To increase server count immediately
✅ Answer: C

Q2. Scaling decisions without knowing current load usually lead to:
 A. Optimal design
 B. Over-engineering or under-engineering
 C. Faster deployment
 D. Better UX
✅ Answer: B

Q3. Current load helps answer which question FIRST?
 A. How to rewrite the system
 B. Whether caching is needed
 C. How the system behaves today
 D. How many engineers are required
✅ Answer: C

2️⃣ Load Parameters – Core Concept
Q4. Load parameters are BEST described as:
 A. Hardware limits
 B. Code metrics
 C. Numerical values describing system traffic
 D. Database schemas
✅ Answer: C

Q5. The choice of load parameters depends mainly on:
 A. Programming language
 B. Company size
 C. System architecture
 D. Cloud provider
✅ Answer: C

Q6. Which statement is TRUE?
 A. Same load parameters work for all systems
 B. Load parameters are independent of architecture
 C. Different architectures need different load parameters
 D. Load parameters are optional
✅ Answer: C

3️⃣ Requests Per Second (RPS)
Q7. “Requests per second” measures:
 A. How many users are online
 B. How many DB queries run
 C. How many requests hit the server each second
 D. How fast CPU executes
✅ Answer: C

Q8. Which of the following is a request in Twitter?
 A. Server reboot
 B. App open / timeline refresh / tweet post
 C. Cache eviction
 D. Log rotation
✅ Answer: B

Q9. Requests per second is MOST relevant for:
 A. Static websites
 B. Web servers handling user actions
 C. Offline batch jobs
 D. Backup systems
✅ Answer: B

4️⃣ Read vs Write Traffic
Q10. In databases, which are write operations?
 A. SELECT
 B. INSERT / UPDATE / DELETE
 C. JOIN
 D. INDEX
✅ Answer: B

Q11. Read-to-write ratio is an important load parameter when:
 A. No database is used
 B. System is compute-only
 C. Database is involved
 D. System is static
✅ Answer: C

Q12. Why is read traffic often more problematic than write traffic?
 A. Reads are slower than writes
 B. Reads scale poorly with users
 C. Reads usually dominate total traffic
 D. Writes are cached
✅ Answer: C

5️⃣ Active Users as Load Parameter
Q13. “Simultaneously active users” is MOST important for:
 A. Batch processing systems
 B. Messaging / chat applications
 C. Static blogs
 D. Cron jobs
✅ Answer: B

Q14. Why are active users a load parameter?
 A. They generate concurrent requests
 B. They consume disk space
 C. They reduce throughput
 D. They simplify scaling
✅ Answer: A

6️⃣ Cache Load Parameters
Q15. Cache request rate means:
 A. Only cache hits per second
 B. Cache misses per second
 C. Total requests reaching cache
 D. Only DB fallbacks
✅ Answer: C

Q16. Cache hit rate is calculated as:
 A. Cache requests / DB requests
 B. Cache hits / total cache requests
 C. Cache misses / cache hits
 D. Cache hits / total users
✅ Answer: B

Q17. Which statement is TRUE about cache request rate?
 A. Only hits are counted
 B. Misses are ignored
 C. Hit or miss both count
 D. Only DB queries count
✅ Answer: C

7️⃣ Average vs Peak Load (VERY IMPORTANT)
Q18. Why is average load alone NOT sufficient for system design?
 A. Average is hard to compute
 B. Peak traffic dominates failures
 C. Average traffic never occurs
 D. Monitoring tools hide averages
✅ Answer: B

Q19. Which scenario best represents peak load?
 A. Normal daytime usage
 B. Midnight traffic drop
 C. New Year / festival traffic spike
 D. Daily cron job
✅ Answer: C

Q20. Systems usually fail during:
 A. Average load
 B. Low traffic
 C. Extreme peak moments
 D. Maintenance windows
✅ Answer: C

🔥 Conceptual Check (Exam-Style)
Q21. Before scaling a system, the MOST correct order is:
 A. Add servers → analyze traffic → redesign
 B. Analyze current load → identify dominant parameters → design for peak
 C. Rewrite code → add cache → measure load
 D. Optimize database → ignore peaks
✅ Answer: B
📘 MCQs – Load Analysis Using Twitter Case Study
Batch 2: Read vs Write Traffic, Peak Load & Real Numbers

8️⃣ Twitter Operations – Basics
Q22. Twitter has two primary user-facing operations:
 A. Login and logout
 B. Tweet posting and Home timeline reading
 C. Search and analytics
 D. Notifications and ads
✅ Answer: B

Q23. Posting a tweet is considered a:
 A. Read operation
 B. Cache hit
 C. Write operation
 D. Background job
✅ Answer: C

Q24. Opening the Home timeline is considered a:
 A. Write operation
 B. Read operation
 C. Maintenance task
 D. Cache eviction
✅ Answer: B

9️⃣ Twitter Traffic Numbers (2012)
Q25. Twitter reported an average tweet creation rate of approximately:
 A. 460 tweets/sec
 B. 4,600 tweets/sec
 C. 46,000 tweets/sec
 D. 460,000 tweets/sec
✅ Answer: B

Q26. During peak events, tweet creation rate reached around:
 A. 6,000 tweets/sec
 B. 8,000 tweets/sec
 C. 12,000 tweets/sec
 D. 50,000 tweets/sec
✅ Answer: C

Q27. Which events typically cause peak traffic spikes?
 A. Server restarts
 B. Daily cron jobs
 C. Festivals, breaking news, accidents
 D. Database backups
✅ Answer: C

🔟 Read Traffic Dominance
Q28. Twitter’s average Home timeline read traffic was approximately:
 A. 30K requests/sec
 B. 100K requests/sec
 C. 300K requests/sec
 D. 1M requests/sec
✅ Answer: C

Q29. Compared to write traffic, read traffic on Twitter is:
 A. Lower
 B. Equal
 C. Much higher
 D. Irrelevant
✅ Answer: C

Q30. Why is read traffic much higher than write traffic?
 A. Writes are cached
 B. One tweet is read by many followers
 C. Reads are slower
 D. Writes are rejected
✅ Answer: B

1️⃣1️⃣ Followers & Multiplication Effect
Q31. If a user has 50 followers, one tweet results in approximately:
 A. 1 read
 B. 10 reads
 C. 50 reads
 D. 500 reads
✅ Answer: C

Q32. This multiplication effect means that:
 A. Writes scale linearly
 B. Reads scale with followers
 C. Reads are constant
 D. Writes dominate load
✅ Answer: B

1️⃣2️⃣ Why Writes Look Easy but Aren’t
Q33. Why is handling 12K tweet writes/sec relatively easier?
 A. Tweets are small
 B. Write = single insert
 C. Writes bypass DB
 D. Writes are asynchronous
✅ Answer: B

Q34. The real challenge is not tweet creation, but:
 A. Storing tweets
 B. Deleting tweets
 C. Serving tweets to followers
 D. Counting likes
✅ Answer: C

1️⃣3️⃣ Read Becomes Write (CRITICAL INSIGHT)
Q35. From a system-design perspective, delivering a tweet to a follower’s timeline is:
 A. A pure read
 B. A cache eviction
 C. A write-like operation
 D. A log entry
✅ Answer: C

Q36. Why does a read become a write internally?
 A. Because of logging
 B. Because timeline data must be inserted/updated
 C. Because reads are slower
 D. Because of retries
✅ Answer: B

1️⃣4️⃣ Peak Load Estimation
Q37. If average read traffic is 300K/sec and peak is 5×, peak read load is about:
 A. 600K/sec
 B. 900K/sec
 C. 1.5M/sec
 D. 3M/sec
✅ Answer: C

Q38. Which traffic should dominate system design decisions?
 A. Average write traffic
 B. Average read traffic
 C. Peak read traffic
 D. Minimum traffic
✅ Answer: C

🔥 Exam-Style Concept Check
Q39. Why does Twitter’s system design focus more on reads than writes?
 A. Writes are unreliable
 B. Reads dominate volume and latency impact
 C. Writes are expensive
 D. Users don’t write often
✅ Answer: B

Q40. A correct takeaway from Twitter traffic analysis is:
 A. Optimize writes first
 B. Ignore read traffic
 C. Design primarily for dominant traffic
 D. Design only for average load
✅ Answer: C
📘 MCQs – Home Timeline Design & Read-Time Explosion
Batch 3: Why Simple Designs Fail

1️⃣5️⃣ Home Timeline – What It Really Is
Q41. A user’s home timeline is BEST described as:
 A. All tweets ever written
 B. Tweets written only by the user
 C. Tweets written by people the user follows
 D. Tweets sorted randomly
✅ Answer: C

Q42. When a user opens the home timeline, the system must:
 A. Insert new tweets
 B. Fetch tweets from followed users
 C. Delete old tweets
 D. Update follower count
✅ Answer: B

1️⃣6️⃣ Naïve (Pull-Based) Design
Q43. A naïve timeline implementation does which operation at read time?
 A. Reads precomputed timeline
 B. Queries tweets + followers + ordering
 C. Reads only cache
 D. Reads one row
✅ Answer: B

Q44. Why does this naïve design work at small scale?
 A. Databases are infinite
 B. Users follow few people
 C. Traffic is low
 D. All of the above
✅ Answer: D

1️⃣7️⃣ Why JOINs Break at Scale
Q45. A timeline query with JOINs becomes slow mainly because:
 A. SQL is inefficient
 B. JOINs increase with follower count
 C. CPUs are slow
 D. Indexes don’t exist
✅ Answer: B

Q46. If a user follows 1,000 people, the timeline query must:
 A. Read 1,000 rows
 B. Join tweets from 1,000 users
 C. Write 1,000 rows
 D. Cache 1,000 items
✅ Answer: B

1️⃣8️⃣ Latency Multiplication at Read Time
Q47. Why does read-time fan-out hurt latency?
 A. Reads are slower than writes
 B. Latency adds up across services
 C. CPUs slow down
 D. Cache disables
✅ Answer: B

Q48. The final response time of a fan-out read equals:
 A. Average latency
 B. Fastest response
 C. Slowest response
 D. Median response
✅ Answer: C

1️⃣9️⃣ Read-Time Cost vs Write-Time Cost
Q49. Which is more dangerous in user-facing systems?
 A. Heavy write-time computation
 B. Heavy read-time computation
 C. Background jobs
 D. Batch processing
✅ Answer: B

Q50. Why is read-time latency more visible to users?
 A. Users wait for it
 B. Writes happen more often
 C. Reads are slower
 D. Monitoring hides writes
✅ Answer: A

2️⃣0️⃣ Scaling Implications
Q51. As users grow, naïve timeline design scales:
 A. Linearly
 B. Logarithmically
 C. Worse than linearly
 D. Constantly
✅ Answer: C

Q52. The biggest problem with naïve pull-based timelines is:
 A. Storage cost
 B. High read-time fan-out
 C. Write amplification
 D. Code complexity
✅ Answer: B

🔥 Exam-Style Scenario
Q53. A system is fast for users with 10 followers but slow for users with 5,000 followers. What is the likely cause?
 A. Cache miss
 B. Write bottleneck
 C. Read-time JOIN explosion
 D. Network failure
✅ Answer: C

2️⃣1️⃣ Key Insight (Very Important)
Q54. Which statement BEST explains why “fast databases” still feel slow?
 A. Databases are badly tuned
 B. JOINs are expensive
 C. Too much work is done at read time
 D. Indexes are missing
✅ Answer: C
📘 MCQs – Push-Based Design & Timeline Precomputation
Batch 4: Fan-out-on-Write (The Real Solution)

2️⃣2️⃣ Push vs Pull – Core Difference
Q55. Pull-based timeline means:
 A. Tweets are pushed to followers immediately
 B. Timeline is computed when user opens the app
 C. Tweets are cached forever
 D. Followers are preloaded
✅ Answer: B

Q56. Push-based timeline means:
 A. Timeline is computed at read time
 B. Tweets are delivered to followers at write time
 C. Tweets are fetched using JOINs
 D. Users pull tweets manually
✅ Answer: B

2️⃣3️⃣ Fan-out-on-Write Explained
Q57. Fan-out-on-write refers to:
 A. Sending read requests to many services
 B. Writing one tweet into many user timelines
 C. Reading many tweets at once
 D. Writing only to database
✅ Answer: B

Q58. The primary benefit of fan-out-on-write is:
 A. Reduced storage
 B. Reduced read latency
 C. Faster writes
 D. Less cache
✅ Answer: B

2️⃣4️⃣ Read Complexity Comparison
Q59. Read complexity in pull-based design is closest to:
 A. O(1)
 B. O(log n)
 C. O(number of followed users)
 D. O(number of tweets)
✅ Answer: C

Q60. Read complexity in push-based design is closest to:
 A. O(n)
 B. O(log n)
 C. O(1)
 D. O(followers)
✅ Answer: C

2️⃣5️⃣ Why Push-Based Feels Fast
Q61. Users experience faster timelines in push-based systems because:
 A. Writes are faster
 B. Heavy work is done before user requests
 C. CPU is faster
 D. JOINs are optimized
✅ Answer: B

Q62. In push-based design, the read path usually does:
 A. Complex JOINs
 B. Aggregation across services
 C. Simple key-based lookup
 D. Multiple DB scans
✅ Answer: C

2️⃣6️⃣ Cost of Push-Based Design
Q63. The biggest cost of fan-out-on-write is:
 A. Read latency
 B. Write amplification
 C. Network latency
 D. Cache misses
✅ Answer: B

Q64. Write amplification means:
 A. One write triggers multiple internal writes
 B. Writes become slower
 C. Writes fail more often
 D. Writes are cached
✅ Answer: A

2️⃣7️⃣ Storage vs Latency Trade-off
Q65. Push-based design trades:
 A. CPU for memory
 B. Storage for read latency
 C. Availability for consistency
 D. Writes for reads
✅ Answer: B

Q66. Which trade-off is acceptable in social feeds?
 A. Slow reads
 B. Extra storage
 C. JOIN-heavy reads
 D. High tail latency
✅ Answer: B

2️⃣8️⃣ Failure Modes
Q67. If a fan-out job fails for some followers, what should happen?
 A. System crashes
 B. Tweet is lost forever
 C. Retry asynchronously
 D. Block the user
✅ Answer: C

Q68. Fan-out-on-write is usually implemented using:
 A. Synchronous HTTP calls
 B. Background workers / queues
 C. User-facing threads
 D. SQL JOINs
✅ Answer: B

🔥 Exam-Style Scenario
Q69. A system has fast writes but slow reads. Best architectural fix?
 A. Add more DB indexes
 B. Increase read replicas
 C. Precompute timelines at write time
 D. Increase thread pool
✅ Answer: C

2️⃣9️⃣ Key Insight (Very Important)
Q70. Which statement BEST explains why push-based systems scale better for feeds?
 A. They reduce total traffic
 B. They reduce read-time dependency fan-out
 C. They eliminate writes
 D. They avoid databases
✅ Answer: B
📘 MCQs – Celebrity Problem & Hybrid Timeline Design
Batch 5 (FINAL): When Push Breaks & How Real Systems Survive

3️⃣0️⃣ Celebrity Problem – Core Understanding
Q71. The celebrity problem occurs when:
 A. A user posts too frequently
 B. A user has extremely many followers
 C. A database becomes slow
 D. Cache size is small
✅ Answer: B

Q72. Why is fan-out-on-write dangerous for celebrities?
 A. Writes are slow
 B. Too many timelines must be updated
 C. Reads become expensive
 D. Cache misses increase
✅ Answer: B

Q73. If a celebrity has 50 million followers, one tweet implies:
 A. 50 million reads
 B. 50 million writes
 C. One DB insert
 D. One cache hit
✅ Answer: B

3️⃣1️⃣ Why Push-Based Design Breaks
Q74. Fan-out-on-write fails at celebrity scale mainly due to:
 A. Network latency
 B. Storage cost
 C. Write amplification explosion
 D. Read complexity
✅ Answer: C

Q75. Which system suffers first for celebrity tweets?
 A. Read path
 B. Cache
 C. Write path
 D. CDN
✅ Answer: C

3️⃣2️⃣ Hybrid Design – The Real Solution
Q76. Hybrid timeline design means:
 A. Only pull-based
 B. Only push-based
 C. Push for normal users, pull for celebrities
 D. Pull for everyone
✅ Answer: C

Q77. In hybrid design, celebrity tweets are usually:
 A. Pushed to all followers
 B. Ignored
 C. Fetched on demand
 D. Deleted after write
✅ Answer: C

3️⃣3️⃣ Read-Time Handling of Celebrity Tweets
Q78. When a user opens timeline, celebrity tweets are typically:
 A. Already in cache
 B. Dynamically merged at read time
 C. Written synchronously
 D. Ignored
✅ Answer: B

Q79. Why is merging few celebrity tweets acceptable?
 A. Celebrities tweet rarely
 B. Number of celebrities is small
 C. Celebrities have few followers
 D. Reads are cached
✅ Answer: B

3️⃣4️⃣ Complexity Comparison (EXAM FAVORITE)
Q80. Hybrid design minimizes which cost?
 A. Read complexity only
 B. Write complexity only
 C. Both read and write extremes
 D. Storage cost only
✅ Answer: C

Q81. Hybrid approach is an example of:
 A. Premature optimization
 B. One-size-fits-all design
 C. Traffic-aware architecture
 D. Over-engineering
✅ Answer: C

3️⃣5️⃣ SLA-Driven Decision Making
Q82. Timeline design is ultimately driven by:
 A. Developer preference
 B. Hardware limits
 C. SLA and user experience
 D. Database choice
✅ Answer: C

Q83. For timeline reads, which SLA is most critical?
 A. Write latency
 B. Storage durability
 C. Read latency (p99)
 D. Backup time
✅ Answer: C

3️⃣6️⃣ Real-World Judgment Questions
Q84. If storage is cheap but latency is expensive, you should prefer:
 A. Pull-based design
 B. Push-based design
 C. Hybrid design
 D. No caching
✅ Answer: B

Q85. If write throughput is limited but reads must be fast, best choice is:
 A. Push-based only
 B. Pull-based only
 C. Hybrid
 D. Batch system
✅ Answer: C

🔥 FINAL SYSTEM DESIGN SCENARIO
Q86. Your system handles normal users well but crashes when a celebrity posts. What’s missing?
 A. Read replicas
 B. More CPU
 C. Hybrid timeline logic
 D. More cache
✅ Answer: C

3️⃣7️⃣ Ultimate Takeaway Questions
Q87. Why don’t real systems use a single timeline strategy?
 A. Simplicity
 B. Cost
 C. Traffic patterns differ across users
 D. Databases don’t support it
✅ Answer: C

Q88. Which sentence BEST summarizes feed system evolution?
 A. Optimize everything
 B. Reads always dominate
 C. Move work off the critical path and handle outliers separately
 D. Push is always better
✅ Answer: C