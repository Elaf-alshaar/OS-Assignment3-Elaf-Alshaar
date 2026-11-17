# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | [Elaf mohammed alshaar] |
| **Student ID** | [446052680] |
| **University Email** | 446052680@std.psau.edu.sa |
| **GitHub Username** | [Elaf-alshaar] |
| **Repository Link** | [https://github.com/Elaf-alshaar/OS-Assignment3-Elaf-Alshaar] |
 
---

## 🎥 Video Link

**Video Link**: [https://youtu.be/RxzKeQmKcgc]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - [ November 6, 2026, 4:30 PM ]
**What I did**: Forked the repository, renamed it, set my student ID, and ran the starter code

**Details**:
- Forked the starter repository.
- Renamed the repository to OS-Assignment3-Elaf-Alshaar.
- Set my student ID in SchedulerSimulationSync.java.
- Ran the original program to observe the synchronization problems.
- Saved the console output for later comparison.
- Created the initial commit with my student ID.
  
**Challenges**: I was not sure how the synchronization bugs were related to each other

**Solution**: I read the README carefully and learned that Feature 1 must be completed before Feature 2 because   queue errors can hide other problems.

**Time spent**: 1 hour

---

### Entry 2 - [ November 6, 2026, 7:00 PM]
**What I did**: Implemented Feature 1 using ReentrantLock in ReadyQueue

**Details**:
- Added a ReentrantLock named queueLock.
- Protected add(), poll(), processOf(), and snapshot().
- Used lock() with try/finally in every protected section.
- Added comments explaining the synchronization changes.
- Created the seconed commit

**Challenges**: I was unsure whether snapshot() also needed protection because it only reads data.

**Solution**: After reading the instructions again I realized that iterating over the queue without synchronization could cause a ConcurrentModificationException, so I protected it as well

**Time spent**: 1 hour

---

### Entry 3 - [November 6, 2026, 10:00 PM]
**What I did**: implemented Feature 2 to protect shared statistics

**Details**:
- Added one ReentrantLock for the shared statistics.
- Protected:
- incrementContextSwitch()
- incrementCompletedProcess()
- addServiceTime()
- Protected all getter methods.
- Tested the program multiple times after the changes.
- Created the thierd commit.
  
**Challenges**: I had to decide whether to use one lock for all counters or a separate lock for each counter

**Solution**: i choose one lock because the shared statistics are simple counters and using a single lock made the implementation easier and easier to maintain.

**Time spent**: 50 minutes 

---

### Entry 4 - [November 14, 2026, 6:00 PM]
**What I did**:  Implemented Feature 3 by replacing busy waiting with a counting semaphore.

**Details**:
- Added a Semaphore to ReadyQueue.
- Initialized the semaphore with value 0.
- Added semaphore.release() in add().
- Added semaphore.acquire() before removing a process from the queue.
- Removed the busy-waiting behavior.
  
**Challenges**: i was initially confused about the correct initial value of the semaphore and how CPUs would terminate when all processes finished

**Solution**: I reviewed the assignment instructions and determined that the semaphore should start at 0 because the queue is initially empty  I also implemented the shutdown signal using release(SharedStats.totalCPUs)

**Time spent**:  2 hours

---

### Entry 5 - [November 15, 2026, 10:00 PM]
**What I did**: committed Feature 3, tested the final solution

**Details**:
- Finished implementing the counting semaphore solution.
- Verified that CPUs wait using acquire() instead of busy waiting.
- Added the shutdown signal using release(SharedStats.totalCPUs).
- Ran the program several times to verify the synchronization behavior.
- Confirmed that Busy-waiting polls = 0.
- Created and pushed the commit: Feature 3: Replaced busy waiting with a counting semaphore.

**Challenges**: I wanted to make sure that all CPU threads terminated correctly when the last process finished and that no thread remained blocked on the semaphore. 

**Solution**:  I carefully tested the shutdown logic and checked the verification block after each run. The program terminated normally and all verification checks passed. 

**Time spent**:  1 hour

---

### Entry 6 - [Optional -November 16, 2026, 6:30 PM]
**What I did**: Completed the project documentation and reviewed the final solution.

**Details**:
- Read the assignment instructions again to ensure all requirements were satisfied.
- Reviewed the implementation of Features 1, 2, and 3.
- Completed the answers in MY_WORK.md.
- Reviewed commit history to make sure each feature had its own meaningful commit.
- Compared the starter output with the final output.
  
**Challenges**:I needed to clearly explain the synchronization decisions and justify my design choices in the documentation.

**Solution**: I reviewed my code and the assignment requirements, then documented the reasoning behind the use of ReentrantLock and Semaphore in a clear and organized way. 

**Time spent**: 1 hour 25 minutes

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [6.25 hours]

**Most challenging part**: Implementing Feature 3 with the counting semaphore. I initially found it difficult to determine the correct initial semaphore value and to ensure that all CPU threads terminated correctly when the last process finished without causing deadlock or leaving threads blocked forever.

**Most interesting learning**: Understanding how race conditions occur in concurrent programs and how synchronization tools such as ReentrantLock and Semaphore can be used to protect shared resources and coordinate multiple threads safely. It was also interesting to observe how small synchronization mistakes can lead to incorrect results, lost updates, or program hangs.

**What I would do differently next time**: I would test every small change immediately after implementing it instead of waiting until a whole feature was completed. This would make it easier to identify the source of bugs and reduce debugging time 

---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

[I learned how race conditions occur when multiple threads access the same shared data without proper synchronization. I saw examples of read-modify-write problems in both the ready queue and the shared statistics counters. I learned that critical sections must be protected using mutual exclusion, and I used ReentrantLock with try/finally to ensure that locks are always released. I also learned that protecting only write operations is not enough because reads can also occur while updates are in progress. Another important lesson was the difference between mutual exclusion and coordination, since the semaphore was used to coordinate CPU threads rather than protect data. I was surprised by how a small timing window created by RaceWindow.pause() could cause major failures such as duplicated processes or incorrect counter values.]

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

[The most challenging part of this assignment was preparing and recording the video presentation. I wanted to make sure that I fully understood every feature before explaining it, especially the synchronization mechanisms used in the solution. It was not enough to have working code because I also needed to clearly describe how the locks and semaphore solved the problems in the starter program. I spent time reviewing the code, the assignment instructions, and the program output to ensure that I could confidently explain my implementation decisions. Another challenge was organizing the explanation in a logical order while keeping the video concise and clear. After several reviews and practice runs, I became more comfortable explaining the synchronization concepts and demonstrating the final working solution.]

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

[overcame this challenge by reviewing the assignment requirements and the implementation of each feature before recording the video. I carefully read the code again and made sure that I understood how the ReentrantLock and Semaphore worked in my solution. I also ran the program several times and checked the verification block to confirm that the results were correct and consistent. Before recording, I organized the main points that I wanted to explain so that the presentation would follow a clear sequence. Practicing the explanation helped me become more confident and reduced mistakes while recording. As a result, I was able to explain both the synchronization concepts and my implementation decisions more clearly.]

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

[Synchronization concepts are used in many real-world systems where multiple users or threads access shared resources at the same time. For example, in an online banking system, synchronization is needed to prevent incorrect account balances when multiple transactions occur simultaneously. In airline or cinema booking systems, synchronization ensures that the same seat cannot be reserved by two customers at the same time. Database management systems also use synchronization to protect shared data from inconsistent updates. Print servers use queues and synchronization mechanisms to coordinate access to printers from many users. The assignment helped me understand that the same ideas used to protect the ready queue and shared statistics can also be applied to real applications that depend on correctness and data consistency.]

### Optional: What would you like to learn more about?

[Any topics related to synchronization or operating systems that you're curious about?]

### Optional: How confident do you feel about synchronization concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

### Optional: Feedback on the assignment

[Any comments? Was it helpful? Too easy or hard? Suggestions?]

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

[in my original starter run, a race condition occurred in the shared ready queue and caused a NullPointerException inside ReadyQueue.snapshot(). The program failed before the processes could execute correctly, so the verification block showed expected 39 observed 0 for context switches, expected 20 observed 0 for completed processes, and expected 58657 observed 0 for total service time. A lost update could also occur on shared counters such as contextSwitchCount when two CPUs read the same value before either one writes back the updated value. For example, CPU-1 and CPU-2 may both read the value 12, then after RaceWindow.pause() both write 13, causing one increment to be lost. The same type of bug can happen on a real machine because thread scheduling is unpredictable, and it is difficult to detect because it depends on rare timing conditions.]

Verification block of the **original starter**:
```
[Exception in thread "CPU-1" Exception in thread "CPU-4" Exception in thread "CPU-3" Exception in thread "CPU-2"
java.lang.NullPointerException: Cannot read field "next" because "this.next" is null
at java.base/java.util.LinkedList$ListItr.next(Unknown Source)
at ReadyQueue.snapshot(SchedulerSimulationSync.java:151)
at CpuWorker.run(SchedulerSimulationSync.java:280)

Context switches (quanta executed) expected 39 observed 0 ✘ MISMATCH
Completed processes expected 20 observed 0 ✘ MISMATCH
Total service time (ms) expected 58657 observed 0 ✘ MISMATCH
Busy-waiting polls (must be 0) expected 0 observed 0
✘ At least one check failed (see the ✘ lines above): a race condition or busy waiting is still present]
```

Verification block of **my final version**:
```
[Context switches (quanta executed) expected 39 observed 39 ✔
Completed processes expected 20 observed 20 ✔
Total service time (ms) expected 58657 observed 58657 ✔
Busy-waiting polls (must be 0) expected 0 observed 0 ✔
✔ All shared values are consistent.]
```

**Explanation of the timeline:**
[CPU-1 reads contextSwitchCount = 12.
RaceWindow.pause() occurs before CPU-1 writes the new value.
CPU-2 reads contextSwitchCount = 12.
CPU-1 writes 13.
CPU-2 writes 13.
The correct value should be 14, but one increment is lost because both CPUs updated the same old value.]

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

[I used two different ReentrantLock objects in my solution: queueLock to protect the ready queue and statsLock to protect the shared statistics. For the statistics, I chose one lock for all three variables (contextSwitchCount, completedProcessCount, and totalServiceTime) because it simplified the implementation and ensured mutual exclusion during updates and reads. The ready queue uses a separate lock because queue operations are independent from statistics updates, and using a single lock for everything would increase contention and could cause unnecessary waiting. My solution provides mutual exclusion because only one thread can access a protected critical section at a time. Progress is maintained because threads eventually release their locks, but bounded waiting is not strictly guaranteed since the default ReentrantLock is non-fair and a thread may occasionally wait longer than others.]

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| [e.g., `ReadyQueue.poll()`] | [lock name] | [reason] |
| [ReadyQueue.add()]       | [queueLock] | [Modifies the shared queue and map] |
| [ReadyQueue.poll()]      | [queueLock] | [Prevents multiple CPUs from removing the same process] |
| [ReadyQueue.processOf()] | [queueLock] | [Accesses the shared map safely] |
| [ReadyQueue.snapshot()]  | [queueLock] | [Prevents concurrent modification during iteration] |
| [contextSwitchCount(incrementContextSwitch())]       | [statsLock] | [Prevents lost updates] |
| [completedProcessCount(incrementCompletedProcess())] | [statsLock] | [Prevents lost updates and incorrect completion count] |
| [totalServiceTime(addServiceTime())] | [statsLock] | [Prevents lost updates in the accumulator] |
| [Statistics getters ] | [statsLock] | [Prevents reading inconsistent values during updates] |


## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

[In the starter version, CPUs used busy waiting by repeatedly checking the ready queue and sleeping for a short time when no process was available. This wastes CPU time because the threads continue polling instead of blocking until work becomes available. In my final solution, the semaphore value represents the number of processes currently waiting in the ready queue, and I initialized it to 0 because the queue is empty when it is created. After the initial 20 calls to add(), the semaphore value becomes 20 because each call executes release(). The last CPU calls release(SharedStats.totalCPUs) to wake up any CPUs blocked in acquire(); otherwise, some CPU threads would remain blocked forever and the program would not terminate correctly.]

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*
This scheduling system is similar to the Producer-Consumer (Bounded Buffer) problem. The CPUs act as consumers when they take processes from the ready queue, and they can also act as producers when they re-enqueue unfinished processes after a quantum expires. If the queue had a limited capacity K, I would use three semaphores: empty initialized to K, full initialized to 0, and mutex initialized to 1. A deadlock could occur if a thread acquired the mutex lock before waiting on a semaphore because other threads would be unable to access the queue and release the required resource. To prevent this, I would break the hold-and-wait condition by ensuring that a thread never waits on a semaphore while holding the mutex lock.

**Classical problem and roles**:
[problem: Producer-Consumer (Bounded Buffer)
Producer: CPUs when they re-enqueue unfinished processes into the ready queue.
Consumer: CPUs when they remove processes from the ready queue and execute them]

**Semaphores for a bounded queue (name and initial value)**:
[ 1- empty is initialized to K because all queue slots are initially empty.
  2- full is initialized to 0 because there are no processes in the queue at the beginning.
  3- mutex is initialized to 1 to provide mutual exclusion when accessing the queue.]

**Deadlock scenario and prevention**:
[Suppose the queue is full and a producer thread acquires mutex first, then waits on empty. Because it is holding mutex, consumer threads cannot enter the queue to remove items and increase empty. The producer waits for empty, while the consumers wait for mutex, creating a deadlock. This can be prevented by breaking the hold-and-wait condition and always waiting on the semaphore before acquiring the mutex, following the classical producer-consumer solution.]

## Summary

**Key concepts I understood through these questions:**
1.Race conditions and lost updates on shared variables.
2.Coordination between threads using counting semaphores instead of busy waiting.
3.Mutual exclusion using ReentrantLock and critical sections.


**Concepts I need to study more:**
1.Deadlock prevention and avoidance techniques.
2.Fairness and starvation in synchronization mechanisms.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [x] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [x] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [x] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [x] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [x] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [x] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [x] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [x] **The four verification lines are ✔ in 5 consecutive runs**
- [x] Every lock is released in a `finally` block
- [x] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [x] Each feature has clear comments

**Commits**
- [x] **At least 4 meaningful commits, ideally 7 or more**
- [x] **One commit per feature**
- [x] Commits are spread over **different dates** (not all in the last hour)
- [x] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [x] Full name and student ID filled in at the top
- [x] Development log has **5+ entries** on different dates
- [x] Reflection: 4 questions, 5-7 sentences each
- [x] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [x] No `[...]` placeholders left
- [x] No section headers deleted

**Video**
- [x] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [x] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [x] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [x] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
