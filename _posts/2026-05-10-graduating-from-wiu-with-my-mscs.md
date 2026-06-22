---
title: "Graduating from WIU with My M.S. Computer Science"
date: May 10, 2026 9:00 AM
categories:
  - personal
tags:
  - graduate-school
  - mscs
  - western-illinois-university
  - teaching
  - capstone
  - ai
description: I graduated from Western Illinois University in May 2026 with a Master of Science in Computer Science and a 4.0 GPA. Here is what the experience actually meant — through tutoring, designing curriculum, building EduKai, and learning what it looks like to finish something hard.
toc: true
comments: true
math: false
image: false
---

## It Is Done

In May 2026, I completed my Master of Science in Computer Science at Western Illinois University, finishing with a 4.0 GPA.

I have been thinking about how to write this post for a while, and I kept putting it off. Graduation is one of those events that is supposed to feel significant and then slips by faster than you expect, leaving you with a diploma and a quiet question: *what did that actually mean?* This is my attempt to answer that question honestly.

## Two Semesters of Teaching

The most unexpected part of my time at WIU was not any course I took. It was the teaching I got to do.

### Fall 2025: Teaching Support Assistant

In Fall 2025, I worked as a Teaching Support Assistant for the School of Computer Sciences. In practice, that meant being the person students came to when they were stuck — across the full undergraduate curriculum. The majority of students who found me were from the introductory programming course, encountering loops and functions and debugging for the first time. That work is satisfying in a particular way: the moment someone understands why their program was not doing what they expected is a visible thing, and you get to watch it happen.

But the more interesting tutoring sessions were with graduate students working through technically demanding material. Helping a graduate student with Computer Graphics means you are not clarifying syntax — you are talking about the OpenGL rendering pipeline, about how transformation matrices move coordinates through model space, world space, and clip space, about the math underlying lighting and shadow calculations. How does diffuse light scatter? What does the surface normal contribute to a shading model? These are not questions you can answer by reminding someone how a for-loop works. They required me to reconstruct my own understanding and explain it from an angle I had not tried before. That kind of teaching is clarifying in a way that being a student is not.

I also helped with Computer Architecture questions: K-map reduction, the translation from boolean expressions to physical circuit designs, the gap between the logic on paper and the behavior in silicon. Sitting across from someone who is stuck on a Karnaugh map at 4pm on a Thursday is a reliable test of whether you actually understand something or just remember having understood it once.

### Spring 2026: Teaching CS101

Spring 2026 was different. I was given responsibility for teaching CS101 to a cohort of interdisciplinary students — people from music, from legal studies and justice administration, from emergency management. Students who were not necessarily there by choice and were not sure the material had anything to do with them.

I designed the curriculum, wrote the exercises, and created the assessments from a provided outline. The structural decisions were mine: what would these particular students actually need in order to feel capable of using technology in their own fields?

The lab sessions are what I remember most clearly from that semester. We deployed a simple site to GitHub Pages. We navigated the Microsoft Office suite — Word, Excel, PowerPoint — through actual tasks rather than abstract demonstrations. We wrote small programs on CodinGame. None of these are technically impressive activities. But watching someone who arrived believing that computers were fundamentally beyond them successfully deploy something to a live URL for the first time — that is not a small thing. The look on their face when it worked was the same regardless of whether they were a music major or anyone else.

The biggest thing I hoped they would take away was this: you can figure it out. Technology is not a closed system with gatekeepers. It responds to patience and curiosity. You will make mistakes, and the mistakes will be informative rather than catastrophic. If you are willing to try, you will make progress.

What I did not expect was what they would give back. They came to class consistently. They completed the work I assigned. They participated in the lab sessions without needing to be pulled into it. Any teacher will tell you that this is not a given, and it made a real difference. I want to thank my students for taking the class seriously and for trusting the process, even when the material felt distant from their own interests. That kind of engagement deserves to be named.

## EduKai: The Capstone

Every MSCS student at WIU completes a capstone project. Mine was **EduKai** — an AI-powered tutoring platform designed to give students the kind of adaptive, personalized feedback that human tutors provide, at a scale that human tutors cannot.

The architecture I built for it centers on a **LangGraph multi-agent system**: multiple AI agents that coordinate with each other to understand what a learner needs and determine how to respond. This is paired with a **RAG (retrieval-augmented generation) pipeline** that grounds the system's responses in specific course material, so that answers are contextual rather than generic. Underlying the review scheduling is **FSRS** — the Free Spaced Repetition Scheduler — a modern algorithm that determines the optimal moment to resurface material based on each learner's memory curve, rather than on a fixed interval.

The problem EduKai is trying to solve is not new: how do you give students the quality of feedback that a good tutor provides, without requiring a tutor to be present for every student? The combination of multi-agent coordination, contextual retrieval, and spaced repetition was my answer to that question.

Dr. Gregory Baramidze, Assistant Professor in the School of Computer Sciences, was my project advisor. He helped me define what the system should actually do — a question that sounds simple and isn't — reviewed the project documentation as it took shape, and helped me present EduKai to the grading committee. His involvement meant I had a genuine thinking partner for the decisions that mattered, not just feedback on whether something ran correctly.

## The People Who Made It Possible

I want to say something that this kind of post sometimes skips over: getting to this point required other people.

**Dr. James McQuillan**, Interim Director of the School of Computer Sciences at Western Illinois University, was my academic advisor throughout the program. The behind-the-scenes work of navigating a graduate degree — course sequencing, requirements, the moments when something is not going according to plan — benefits enormously from having someone in your corner who understands the institution and is willing to spend time helping you stay on track. Dr. McQuillan was that person for me, and I am grateful.

**Dr. Gregory Baramidze** I have already mentioned in the context of EduKai, but I want to acknowledge something beyond the capstone: he has continued to support my job search after graduation. That kind of sustained investment in a student's future, past the point when the grades are submitted and the paperwork is signed, is not something anyone has to do. It says something about what kind of educator he is, and it has meant more to me than I have probably communicated.

To my students in CS101: thank you. You showed up, and that is not as common as it should be.

## What Comes Next

I am currently applying for post-completion OPT, which will allow me to work in the United States during my job search. My focus is on backend, data, and AI roles — the combination that maps most directly to both what I have built before and what I want to build next.

If the search in the US does not come together, I will return to Vietnam and pursue opportunities there. I have thought about this carefully and I have made peace with either outcome. The skills do not change depending on which country I happen to be in, and the work I want to do exists in both places.

I am also watching PhD programs, particularly at the University of Illinois Urbana-Champaign. That is a longer-horizon goal, but it is a real one, and it lives alongside the job search rather than as a fallback.

## A Final Note

I started this post by asking what the degree actually meant. Here is my answer.

It meant showing up to everything — courses, tutoring shifts, teaching, the capstone — and not stopping when it was inconvenient. A 4.0 GPA across a graduate program is a number, but the number reflects something more basic: sustained effort over time, applied consistently across two years of material that was sometimes difficult and sometimes unclear and occasionally both at once.

I did not always know what I was building toward. I do not fully know now. But I finished, and finishing, it turns out, is its own kind of answer. The rest comes from what you do with it.
