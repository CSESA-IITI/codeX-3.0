# Introduction to Cybersecurity and CTFs

## What is cybersecurity?

Cybersecurity is the practice of protecting computers, networks, applications, and data from unauthorized access, misuse, disruption, or damage. It combines technology, careful system design, and everyday habits such as using strong passwords, installing updates, and recognizing suspicious messages.

Three basic goals guide security decisions:

- **Confidentiality:** Only authorized people can access information.
- **Integrity:** Information remains accurate and cannot be changed without authorization.
- **Availability:** Systems and information are accessible when needed.

For example, a college portal should keep student records private, prevent unauthorized changes to grades, and remain available during registration.

A **vulnerability** is a weakness, such as a missing access check. A **threat** is something that could exploit that weakness. **Risk** considers how likely an incident is and how serious its consequences could be.

Cybersecurity includes securing websites and networks, investigating digital evidence, protecting accounts, and monitoring systems for suspicious activity. Beginners can start with basic Linux commands, networking concepts, and a programming language such as Python. You can learn these gradually while working on practical exercises.

## What are CTFs?

**CTF** stands for **Capture the Flag**. In cybersecurity, a CTF is a collection of challenges where you investigate a file, program, or intentionally vulnerable system to discover a hidden answer called a **flag**. A flag often looks like `flag{example_answer}`, although its format depends on the platform.

In a common format called a **Jeopardy-style CTF**, you choose challenges from different categories and submit flags to earn points. You can participate individually or with a team.

Common categories include:

- **General skills:** Working with terminals, files, encodings, and simple scripts.
- **Web security:** Understanding how websites work and identifying weaknesses in practice applications.
- **Cryptography:** Exploring encryption, mathematical puzzles, and mistakes in cryptographic implementations.
- **Digital forensics:** Examining files, metadata, or network captures to recover clues.
- **Reverse engineering:** Studying a program to understand its behavior.
- **Binary exploitation:** Investigating low-level program weaknesses, including memory errors.

CTFs help develop problem-solving, research, and debugging skills. You do not need to know every category before starting. Begin with easy challenges, keep notes on what you discover, and use hints when you are stuck. Practice within the systems and rules provided by the challenge platform.

## Start practicing with picoCTF

[picoCTF](https://picoctf.org/) provides cybersecurity challenges for learners. Its [picoGym practice area](https://play.picoctf.org/practice) lets you work through challenges at your own pace outside a live competition. The official [getting-started guide](https://picoctf.org/get_started.html) explains how to begin.

1. Create an account and open picoGym.
2. Start with easy **General Skills** challenges.
3. Read the description carefully and inspect the provided files or clues.
4. Research unfamiliar commands and concepts, then try them in the challenge environment.
5. Submit the flag and record the approach that worked.

When you are ready to build something, try the [Suspicious Login Activity Analyzer](02_problem_statement.md). Find supporting material in [Learning Resources](03_resources.md).
