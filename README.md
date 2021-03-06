# KAIST CS492: Design and Analysis of Concurrent Programs

## Logistics

- Instructor: [Jeehoon Kang](https://cp.kaist.ac.kr/jeehoon.kang)
- TA: [Jaehwang Jung](https://cp.kaist.ac.kr/jaehwang.jung)
- Time & Place: Tue & Thu 10:30am-11:45am, Rm 1101, Bldg E3-1 (for 2020 Fall)
- Website: https://github.com/kaist-cp/cs492-concur
- Announcements: in [issue
  tracker](https://github.com/kaist-cp/cs492-concur/issues?q=is%3Aissue+is%3Aopen+label%3Aannouncement)



## Course description

### Context

I expect computers in the next 700 years will be **massively parallel**. We the humankind want to
improve the performance of computers in the era of big data. But it is becoming more and more
challenging after the breakdown of [Dennard scaling](https://en.wikipedia.org/wiki/Dennard_scaling)
around 2005, which means the performance of sequential computers will not be improved. Thus not only
servers but also personal computers have been multi-core systems since then. The problem is only
worsened by the ending of the [Moore's law](https://en.wikipedia.org/wiki/Moore%27s_law), which
means we are no longer able to benefit from denser electrical circuit. It seems the only remaining
way to optimize performance is specialization, which aims to better exploit parallelism of
workloads. Because of these technology trends, I expect computers in the future will be massively
parallel.

But we are not ready yet for the era of massive parallelism. The main difficulty lies on handling
**shared mutable states**, which is the main topic of concurrency. To coordinate multiple cores and
other resources, their inputs and outputs should be somehow properly synchronized with each other
via shared mutable states like memory. But handling shared mutable states is inherently challenging,
both theoretically and practically. For example, in the presence of thousands and millions of cores,
how to efficiently synchronize concurrent accesses to shared memory? In the presence of
nondeterministic interleaving of thread executions, how to make sure the safety of a concurrent
program? In the presence of compiler and hardware optimizations, what is the right specification of
a concurrent data structure?

Fortunately, the theory of shared mutable states has advanced quite impressively in the past five
years, and now it is greatly helpful in designing and analyzing practical systems with shared
mutable states. So in this course, we will discuss the recent theory of shared mutable states and
its application to real-world practical systems.


### Goal

This course is geared towards senior undergraduate/graduate students in computer science (or related
disciplines) who are interested in the modern theory and practice of parallel computer systems.
This course aims to help such students to:

- Understand the motivations and challenges in concurrent programming
- Learn design patterns and reasoning principles of concurrent programs
- Design, implement, and evaluate concurrent programs
- Apply the understanding to real-world parallel systems


### Textbook

- [Slides](https://docs.google.com/presentation/d/1NMg08N1LUNDPuMxNZ-UMbdH13p8LXgMM3esbWRMowhU/edit?usp=sharing)
- Classical papers and libraries
    + [Promising semantics](https://sf.snu.ac.kr/promise-concurrency/): programming language &
      architecture semantics for shared-memory concurrency
    + [Crossbeam](https://github.com/crossbeam-rs/crossbeam): concurrent data structure library in
      [Rust](https://www.rust-lang.org/)


### Tools

- We will use [Rust](https://www.rust-lang.org/) as the language of implementation, because its
  ownership type system greatly simplifies the reasoning of shared mutable states without incurring
  significant runtime overheads.

- You should host all your implementation in [GitHub](https://github.com).


## Prerequisites

- It is **strongly recommended** that students already took courses on:

    + Mathematics (freshman calculus, MAS101 & MAS102): proposition statement and proof
    + Data structures (CS206): linked list, stack, queue
    + Systems programming (CS230): memory layout, cache, lock

  Without a proper understanding of these topics, you will likely struggle in this course.

- Other recommendations which would help you in this course:

    + Basic understanding of computer architecture (CS311)
    + Programming experience in [Rust](https://www.rust-lang.org/)



## Grading & honor code

### Homework & project (60%)

- Reading assignment (both paper and code)
- Programming assignment (including design, implementation, evaluation)

### Midterm and final exams (40%)

The exams will evaluate your theoretical understanding of shared mutable states.

### Attendance (?%)

You should submit a token to the [Course Management](https://gg.kaist.ac.kr) website for each
session.  You should submit a token within **12 hours from the beginning of a sessions**.

### Honor code

Please sign [KAIST School of Computing Honor Code](https://forms.gle/1WrK3YyWhJZYuKwZ9).



## Communication

- Course-related announcements and information will be posted on the
  [website](https://github.com/kaist-cp/cs492-concur) as well as on the [GitHub issue
  tracker](https://github.com/kaist-cp/cs492-concur/issues).  You are expected to read all
  announcements within 24 hours of their being posted.  It is highly recommended to watch the
  repository so that new announcements will automatically be delivered to you email address.

- Ask your questions via email **only if** they are either confidential or personal.  Otherwise, ask
  questions in [this repository's issue tracker](https://github.com/kaist-cp/cs492-concur/issues).
  Any questions failing to do so (e.g. email questions on course materials) will not be answered.

- Emails to the instructor or TAs should begin with "CS492:" in the subject line, followed by a
  brief description of the purpose of your email.  The content should at least contain your name and
  student number.  Any emails failing to do so (e.g. emails without student number) will not be
  answered.
