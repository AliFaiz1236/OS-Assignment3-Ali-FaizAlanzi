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
| **Full Name** | [Write your full name here ; Ali Faiz Alanzi] |
| **Student ID** | [Write your student ID here; 446050238] |
| **University Email** | 446050238@std.psau.edu.sa |
| **GitHub Username** | [AliFaiz1236] |
| **Repository Link** | [Paste your repository link here] |
 
---

## 🎥 Video Link 

**Video Link**: []https://youtu.be/RYO41B2Lwcg 

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
| 7 | Video link | `Docs: ` | https://youtu.be/RYO41B2Lwcg 

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

### Entry 1 - [11\22 6pm]
Entry 1 - November 22, 2026, 6:15 PM
What I did: Read README.md and SchedulerSimulationSync.java, set my student ID 446050238, and ran the original starter program
Details:
Read README.md and traced how ReadyQueue, SharedStats, CpuWorker, and RaceWindow interact
Set my student ID to 446050238 on line 304 of SchedulerSimulationSync.java
Ran the original starter code and saved its output showing race conditions, busy waiting, and synchronization issues
Committed and pushed: Set my student ID: 446050238
Challenges: Identifying all shared variables and critical sections accessed concurrently across threads
Solution: Read SchedulerSimulationSync.java from top to bottom and mapped each shared structure and method before editing
Time spent: 50 minutes

---

### Entry 2 - [11\22 7 pm]
**What I did**: Entry 2 - November 22, 2026, 7 PM
Implemented Feature 1 by protecting ReadyQueue operations with a ReentrantLock
Details:
Used queueLock (ReentrantLock) in ReadyQueue around critical sections accessing list and map in add and poll
Wrapped lock acquisition and release inside try ... finally blocks so locks are always released even if an exception occurs
Tested queue behavior and committed Feature 1 changes
Challenges: Making sure lock release happens reliably on every return or exception path in queue operations
Solution: Placed queueLock.unlock() strictly inside finally blocks immediately after queueLock.lock(); try { ... }
Time spent: 45 minute
---

### Entry 3 - [11\22 8pm]
Entry 3 - November 22, 2026, 9:50 PM
What I did: Implemented Feature 2 by protecting SharedStats counters with locks for read and write operations
Details:
Protected updates and reads of completedProcessCount, contextSwitchCount, and totalServiceTime in SharedStats using ReentrantLock and try ... finally
Fixed a duplicate call inside getCompletedProcessCount() before returning completedProcessCount
Guarded getter methods as well so threads do not read inconsistent or partially updated counter values
Committed and pushed Feature 2
Challenges: Deciding between a single shared lock for all statistics versus separate locks for independent counters, and ensuring getters were protected
Solution: Used dedicated locks per statistic counter with try ... finally blocks to avoid unnecessary contention while preserving mutual exclusion
Time spent: 55 minutes
---

### Entry 4 - [11\22 9pm]
Entry 4 - November 22, 2026, 1:30 PM
What I did: Started Feature 3 by importing and initializing the counting semaphore availableItems and signaling process availability in ReadyQueue.add
Details:
Imported java.util.concurrent.Semaphore at the top of SchedulerSimulationSync.java
Initialized final Semaphore availableItems = new Semaphore(0); in ReadyQueue so CpuWorker can access it cleanly
Added availableItems.release(); inside ReadyQueue.add(Process process) whenever a process is added to the queue
Challenges: Resolving cross-class access to availableItems from CpuWorker when private blocked direct access
Solution: Removed the private modifier on availableItems in ReadyQueue while keeping it final
Time spent: 40 minutes

---

### Entry 5 - [11\22 10pm]
Entry 5 - November 22, 2026, 5:20 PM
What I did: Completed Feature 3 in CpuWorker.run() by replacing busy waiting with availableItems.acquire() and adding end-of-execution semaphore wake-up
Details:
Replaced the polling and Thread.sleep(20) busy-waiting loop in CpuWorker.run() with a blocking readyQueue.availableItems.acquire() call inside try ... catch (InterruptedException e) before readyQueue.poll()
Removed a duplicate Thread thread = readyQueue.poll(); declaration and cleaned up stray characters in the loop
Added if (SharedStats.getCompletedProcessCount() >= SharedStats.totalProcesses) { readyQueue.availableItems.release(SharedStats.totalProcesses); } so blocked worker threads wake up and terminate cleanly once all processes finish
Committed and pushed Feature 3
Challenges: Avoiding duplicate variable declarations in the while loop and preventing CpuWorker threads from remaining blocked on acquire() after completion
Solution: Removed the duplicate declaration, handled InterruptedException cleanly, and released permits once completed processes reach totalProcesses
Time spent: 60 minutes

---

### Entry 6 - [Optional - 11\22]
Entry 6 - November 22, 2026, 8:45 PM
What I did: Ran multiple verification tests on the final code and drafted documentation in MY_WORK.md
Details:
Executed multiple consecutive runs in the IDE to verify clean termination without WATCHDOG and all verification checks passing
Wrote development log entries, reflection answers, and technical answers in MY_WORK.md
Committed and pushed documentation updates to the GitHub repository
Challenges: Ensuring every question in Part B and Part C respects the sentence limits and uses accurate examples from my implementation
Solution: Reviewed each answer against the code changes and test runs before saving and pushing to GitHub
Time spent: 50 minutes

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.
Total time spent on assignment: 5 hours (across November 12–13, 2026, plus the November 22, 2026 video demo)

Most challenging part: Coordinating CpuWorker blocking on availableItems.acquire() with proper wake-up (release) when all processes complete so no worker thread remains stuck waiting indefinitely.

Most interesting learning: Seeing firsthand how removing Thread.sleep polling and using ReentrantLock + Semaphore eliminates race conditions and wasted CPU polling while keeping shared state consistent.

What I would do differently next time: Trace all variable scopes and TODO markers across classes carefully before making edits so duplicate statements or stray characters never sneak into the code.


---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

Question 1: What did you learn about synchronization?
Your Answer: (5-7 sentences)

Working on this assignment taught me that concurrent threads executing read-modify-write operations on shared data can easily corrupt state when interleaved. A race condition occurs when multiple threads read or modify shared structures—such as ReadyQueue or SharedStats counters—without mutual exclusion. Using ReentrantLock with try ... finally blocks guarantees that only one thread enters a critical section at a time and that the lock is always released even if an exception happens. I also learned how a counting Semaphore (availableItems) coordinates threads based on available permits instead of repeatedly polling an empty queue. What surprised me most when running the starter code was how quickly timing delays like RaceWindow.pause() exposed conflicting thread behavior and incorrect statistics. Overall, proper synchronization turns unpredictable multi-threaded execution into deterministic, safe behavior.

Question 2: What was the most challenging part of this assignment?
Your Answer: (5-7 sentences)

The most challenging part of this assignment was coordinating CpuWorker thread termination with the counting semaphore once all processes finished executing. When worker threads block on readyQueue.availableItems.acquire(), any remaining thread waiting on a permit will stay blocked if no further release() happens after the final process completes. Deciding when and how many permits to release at the end of the loop in CpuWorker.run() required careful thought about the loop condition checking SharedStats.getCompletedProcessCount() < SharedStats.totalProcesses. While making that edit, I also had to fix a duplicate Thread thread = readyQueue.poll(); declaration and a stray pasted text snippet that broke compilation. Resolving both the concurrency logic and the syntax issues made me appreciate how sensitive multi-threaded loops are to edge cases. Testing the program repeatedly helped confirm that all threads exit cleanly without triggering the watchdog.

Question 3: How did you overcome the challenges you faced?
Your Answer: (5-7 sentences)

I overcame the challenges by reading README.md and SchedulerSimulationSync.java systematically before changing synchronization logic. Whenever a compiler error or unexpected behavior appeared, I inspected the exact line numbers and error messages in VS Code rather than guessing. For SharedStats and ReadyQueue, I checked every read and write path to make sure every lock() had a matching unlock() inside a finally block. For the semaphore in Feature 3, I verified cross-class access to availableItems, matched acquire() in CpuWorker.run() with release() in ReadyQueue.add(), and added end-of-work wake-up releases when completed processes reached totalProcesses. Running the program multiple times after each feature and committing changes incrementally helped me catch mistakes early and keep the repository organized.

Question 4: Where can synchronization concepts be applied in real-world applications?
Your Answer: (5-7 sentences)

Synchronization concepts apply directly to banking applications where concurrent transactions update account balances and transaction logs. If two transfers read the same balance before writing back, a lost update can credit or debit money inaccurately, just like an unprotected counter in SharedStats. Online ticket or seat booking systems also rely on mutual exclusion so two users cannot reserve the last available seat at the exact same moment. Print queues and background job workers mirror ReadyQueue and CpuWorker, using semaphores or condition queues so worker threads wait efficiently until jobs arrive. Database systems similarly depend on locks and concurrency control to preserve consistency under heavy parallel load.

Optional: What would you like to learn more about?

Condition variables (Condition with ReentrantLock), lock-free atomic classes (AtomicInteger, AtomicLong), and deadlock detection/prevention algorithms in operating systems.

Optional: How confident do you feel about synchronization concepts now?

Confident with basic ReentrantLock and Semaphore usage and race-condition debugging; I want more practice with complex multi-lock ordering and condition queues.

Optional: Feedback on the assignment
The assignment was very helpful because seeing the broken starter first and fixing each feature step by step made abstract synchronization concepts concrete.

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

[Write your answer here.]


In the unpatched starter run for ID 446050238, shared counters in SharedStats and queue operations in ReadyQueue were accessed concurrently without mutual exclusion, causing mismatches between expected and observed values as well as thread contention or errors. A single lost update happens when two threads read the same counter value, pause or get preempted before writing, and both write back an incremented value based on the stale read. On a real machine even without RaceWindow.pause(), OS thread scheduling, context switches, and CPU cache or instruction reordering can still interleave these steps unpredictably. It is hard to detect because timing varies across runs, so the bug may appear intermittently or only under heavier load.
Verification block of the original starter:
[Paste the exact verification block / console output from your original starter run for Student ID 446050238 here]

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

[Write your answer here.] 

I protected ReadyQueue (list and map inside add and poll) with queueLock and protected the SharedStats counters (completedProcessCount, contextSwitchCount, and totalServiceTime across their update and getter methods) using separate ReentrantLock instances per statistic counter. Using per-counter locks instead of a single global statistics lock avoids blocking unrelated statistics updates while trading off slightly more lock management overhead, and keeping queueLock separate from statistics locks avoids unnecessary coupling or lock-ordering conflicts across subsystems. Mutual exclusion is enforced because every critical section requires acquiring its ReentrantLock and releasing it in a finally block. Progress is preserved because active threads release locks in finally without holding them across external blocking waits, though a default non-fair ReentrantLock does not strictly guarantee FIFO bounded waiting under heavy contention
| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| [e.g., `ReadyQueue.poll()`] | [lock name] | [reason] |
| [...] | [...] | [...] |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

[Write your answer here.]
In the starter code, CpuWorker polled an empty queue in a loop and slept briefly (Thread.sleep(20)) while incrementing busyWaitPolls (observed value from starter run: [Paste exact Busy-waiting polls count from your starter output here]), wasting CPU cycles and polling repeatedly while waiting for work. The availableItems semaphore represents the number of ready process permits currently available to be dequeued from ReadyQueue, starting at 0 because the queue begins empty with no processes available to consume. Right after numProcesses initial add() calls—each calling availableItems.release()—the semaphore value is numProcesses (assuming no acquire() calls have consumed permits yet). Releasing permits once SharedStats.getCompletedProcessCount() >= SharedStats.totalProcesses wakes up CpuWorker threads blocked on availableItems.acquire() so they can exit the loop and terminate; without it, blocked worker threads would remain stuck waiting on the semaphore indefinitely.

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*
Classical problem and roles:
This matches the Producer-Consumer (Bounded-Buffer) problem from Chapter 5: process arrivals/enqueueing act as the producer adding processes to ReadyQueue, while CpuWorker threads act as consumers removing processes to run a quantum—and importantly, CpuWorker threads also act as producers when they re-enqueue a process that has not finished (!process.isFinished()).

Semaphores for a bounded queue (name and initial value):
For a bounded queue of capacity K, you would use three synchronization primitives/semaphores: empty initialized to K (available free slots), full initialized to 0 (available items to consume), and mutex initialized to 1 (binary semaphore / mutual exclusion lock protecting queue access).

Deadlock scenario and prevention:
If a producer or re-enqueueing CpuWorker acquired mutex first and then called empty.acquire() when the queue is full (0 permits), it would block while holding mutex, preventing any consumer from acquiring mutex to remove an item and signal empty.release()—causing a deadlock. To prevent this, you can break the hold and wait (or circular wait) condition by acquiring/waiting on capacity semaphores (empty / full) before acquiring mutex and keeping the critical section short.
## Summary

1. How race conditions and lost updates arise from unsynchronized read-modify-write sequences and why try ... finally is essential with locks.

2. How lock granularity (queueLock vs. SharedStats locks) affects concurrency, contention, and deadlock risk.

3. How a counting semaphore (availableItems) replaces busy-waiting polling and requires wake-up releases so threads do not hang after completion.

Concepts I need to study more:
1. Bounded-buffer semaphore ordering (empty, full, mutex) and avoiding deadlock under multiple locks.

2. Fairness trade-offs (fair vs. non-fair ReentrantLock) and condition variables in Java concurrency.
---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
