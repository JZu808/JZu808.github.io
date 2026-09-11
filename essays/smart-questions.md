---
layout: essay
type: essay
title: ""
# All dates must be YYYY-MM-DD format!
date: 2026-09-10
published: true
labels:
  - Questions
  - Answers
  - StackOverflow
---

<img width="300px" class="rounded float-start pe-4" src="../img/smart-questions/rtfm.png">

---
title: "Asking Questions the Smart Way"
summary: "Why clear questions matter in software engineering, using a smart and a not-so-smart StackOverflow question as examples."
date: 2026-09-10
labels:
  - Communication
  - Software Engineering
  - StackOverflow
---

---
title: "Asking Questions the Smart Way"
summary: "Why doing your homework first makes a better question, shown through a smart and a not-so-smart StackOverflow post."
date: 2026-09-10
labels:
  - Communication
  - Software Engineering
  - StackOverflow
---

## Before You Ask

The smartest part of a good question happens before you post it. In [*How To Ask Questions The Smart Way*](http://www.catb.org/esr/faqs/smart-questions.html), Eric Raymond says the people answering are mostly volunteers, and they can tell how much effort you put in. So do your homework first: search the web, read the manual, and try to solve the problem yourself. Then show that you did.

This matters because a vague question makes the reader guess. When you leave out details, they fill in the blanks with their own assumptions and end up solving the wrong problem. Doing your homework first, and showing it, keeps the answer aimed at your real question. The two posts below show both sides of this.

## The Smart Question

A good example is a StackOverflow question titled [*Why is processing a sorted array faster than processing an unsorted array?*](https://stackoverflow.com/questions/11227809/why-is-processing-a-sorted-array-faster-than-processing-an-unsorted-array). The developer noticed that a simple C++ loop ran about six times faster when the array was sorted first, even though sorting shouldn't change the result. He posted the full, runnable code, gave his exact timing numbers, and asked one clear question: why?

This question does everything Raymond asks for. The title names the exact problem. The code is small enough to read but complete enough to run, so anyone can see the behavior instead of guessing. The timing numbers are real facts, not "it's slow." //And it stays calm and focused, with no panic or urgency.

Because the question gave everything needed, the community went straight to answering. The top answer explains **branch prediction**: the CPU guesses which way an `if` will go so it can work ahead. On sorted data that guess is almost always right, so the loop is fast. On random data it's often wrong, which slows things down. The answer became one of the most upvoted on the whole site and still helps people today.

That is help that is both fast and useful. There was no back-and-forth, because nothing was missing. The good question made the good answer possible.

## The Not-So-Smart Question

Bad questions usually get deleted fast, so they are hard to link to. So, as the assignment allows, here is a made-up example based on the mistakes StackOverflow warns about in its [How do I ask a good question?](https://stackoverflow.com/help/how-to-ask) guide:

> **Title:** PLEASE HELP my code doesnt work!!! URGENT
>
> **Body:** "i am making a website and my javascript is not working. it was fine yesterday and now it doesnt. can someone tell me whats wrong?? i need this ASAP its due tomorrow. thanks"

This breaks almost every rule. Nothing shows any homework. The title describes panic, not the problem. There is no code, so nothing can be tested. "Doesn't work" gives no error message and no details. And "URGENT" tries to push the asker's deadline onto volunteers, which Raymond says gets a question ignored, not answered faster.

A question like this gets slow, useless help. People ask for the missing basics, leave replies like "works on my machine," or just downvote and close it. Instead of an answer, the asker gets a list of follow-up questions. The "urgent" tag ends up causing the slowest result of all.

## What I Learned

The biggest difference between these two is the homework. One person did it and showed it; the other did none. That one thing decides whether answering is easy or a chore. "Doesn't work" is the mistake to avoid, while clear details let someone help right away. I also learned that writing a good question can solve the problem on its own, since explaining it clearly often reveals the answer. In the end, asking clearly is really about respecting other people's time, and it's one of the easiest ways to become a better engineer.

## References

- Eric S. Raymond, [*How To Ask Questions The Smart Way*](http://www.catb.org/esr/faqs/smart-questions.html)
- StackOverflow #11227809, [*Why is processing a sorted array faster than processing an unsorted array?*](https://stackoverflow.com/questions/11227809/why-is-processing-a-sorted-array-faster-than-processing-an-unsorted-array)
- StackOverflow, [*How do I ask a good question?*](https://stackoverflow.com/help/how-to-ask)
- StackOverflow, [*How to create a Minimal, Reproducible Example*](https://stackoverflow.com/help/minimal-reproducible-example)
