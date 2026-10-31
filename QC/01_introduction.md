# Introduction to Quantum Computing Software

Quantum computing uses a different model of computation to solve certain kinds of problems. These projects introduce that model through software running on an ordinary laptop. No previous quantum computing knowledge or access to quantum hardware is required.

You should be comfortable with functions, loops, lists, and basic debugging. The explanations start from the basics, while the projects involve building complete tools rather than isolated demonstration scripts.

## Bits, qubits, and measurement

A classical computer stores information in bits, each having a value of `0` or `1`. A quantum computer uses **qubits**. Before measurement, a qubit is described by two numbers called **amplitudes**, associated with the possible outcomes `0` and `1`.

An amplitude is not a probability. Its squared magnitude gives the probability of observing an outcome. Amplitudes can be negative or complex, allowing them to reinforce or cancel one another. This behavior is called **interference**.

**Superposition** means that several possible outcomes have nonzero amplitudes. Measuring produces one result, not every possible answer at once. Measurement also changes the state, affecting subsequent operations.

## Gates and circuits

A **quantum gate** changes a state according to a mathematical rule. A **circuit** is a sequence of gates and measurements.

- **X:** Exchanges the amplitudes associated with `0` and `1`.
- **H, or Hadamard:** Combines amplitudes to create superposition or interference.
- **Z:** Changes the sign of the amplitude associated with `1`.
- **CNOT:** Flips a target qubit when a separate control qubit is `1` in a basis state. On a superposition, it applies this rule to each component.

Two qubits have four possible measurement outcomes: `00`, `01`, `10`, and `11`. Their joint state requires four amplitudes. In general, a state-vector simulation of `n` qubits stores `2^n` amplitudes.

Qubits can become **entangled**, meaning their joint state cannot be described as independent states for each qubit. An ideal Bell state, for example, gives `00` or `11` with equal probability when both qubits are measured in the usual basis.

## Where software fits

A simulator stores amplitudes, applies gates, and samples measurement results. It calculates quantum behavior using a classical computer. This does not give the laptop the computational advantages of quantum hardware, and the required storage grows rapidly with the number of qubits.

Quantum software also includes applications that coordinate protocols, manage experiments, and explain measurements. Building a simulator and building an application using an existing quantum library are two different routes into the field.

## The projects

**[PS1: Quantum Circuit Debugger and Hidden-String Solver](02_PS1.md)** is the beginner project, with a substantial programming scope. Build a small multi-qubit simulator without quantum libraries, inspect circuits step by step, and run a quantum algorithm on your simulator.

**[PS2: Quantum Communication and Eavesdropping Lab](03_PS2.md)** sits between beginner and moderate. Use a quantum library to build an interactive communication experiment with interception, noise, and result analysis.

Each project ends with a working application in a GitHub repository and a detailed README. Learning material is collected in [Resources](04_resources.md).
