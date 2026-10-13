# THIH Linux Learner Guide

**THIHsystems Field School 2026–2027 | Linux fundamentals, guided labs, and practical troubleshooting**

Learn to explain a command, predict its behavior, run it in the right environment, and verify what the result establishes. Careful practice is part of faithful stewardship of systems.

## Start here

| Goal | Resource |
|---|---|
| Understand the learning approach | [Field School](field-school/README.md) |
| Resume from a demonstrated checkpoint | [Progress record](field-school/PROGRESS.md) |
| Practice the next lesson | [Lesson 12: Pipes](field-school/lessons/12-pipes.md) |
| Design a lesson | [Lesson template](field-school/templates/lesson.md) |
| Document learning publicly | [Learning journal](field-school/templates/learning-journal.md) |

## Topic library

The inherited folders remain a quick reference library. Reading a section does not establish proficiency.

| Topic | Reference | Practical question |
|---|---|---|
| Fundamentals | [Getting started](01-getting-started/01-fundamentals.md) | Which environment am I using? |
| Filesystem | [Folder structure](02-folder-structure/README.md) | Where should I look and work? |
| Users | [User management](03-user-management/README.md) | Whose identity and privileges apply? |
| Files | [File management](04-file-management/README.md) | How can I inspect and handle files deliberately? |
| Editing | [VI shortcuts](05-vi-shortcuts/README.md) | How do I edit, save, and exit? |
| Permissions | [File permissions](06-file-permissions/README.md) | Who can read, write, or execute this? |
| Processes | [Process management](07-process-management/README.md) | What is running, and what would stopping it affect? |
| Monitoring | [System monitoring](08-monitoring/README.md) | What current evidence supports my diagnosis? |
| Networking | [Networking](09-networking/README.md) | Is this addressing, routing, DNS, or a service? |
| Storage | [Disk management](10-disk-management/README.md) | Which destination is affected? |

## Learning rhythm

**Recall → explain → predict → execute → verify → apply → teach back.**

Progress follows demonstrated understanding. A 45-lesson curriculum may take 90 days or longer. Weekends and missed mornings create no catch-up obligation. Resume when there is time and attention to learn.

Use Ubuntu WSL for foundational exercises. Treat the separate practice server as a separate host: verify identity and fresh evidence before applying lessons there. Examples and old reports do not establish current server health.

## Attribution and first-edition scope

This fork began with **Ultimate Linux Guide**, revision notes for **Abhishek Veeramalla** (`iam-veeramalla`) and his YouTube course. [Original introduction](field-school/UPSTREAM-INTRODUCTION.md) preserves that credit. The original topic folders remain available; this homepage and `field-school/` add the THIH learning approach.

This first edition contains one fully worked guided lesson, not a completed rewrite of every section. Later editions can deepen each topic using the same lesson format.

Read inherited commands in context before execution, especially deletion, privileges, storage, networking, and container setup. A container does not reproduce every aspect of a full server. Mounting a host Docker socket grants substantial control over the host and is unnecessary for introductory shell practice.
