# Systems & Graphics Project Problem Statements

A set of three hands-on programming projects covering graphics/simulation, networking, and systems programming. Each project lists its objective, the concepts it exercises, and its core requirements. Bonus goals are optional stretch features.

## Projects at a Glance

| # | Project | Domain | Key Concepts | Suggested Languages |
|---|---------|--------|--------------|---------------------|
| 1 | [Cellular Automata Fluid Simulator](#1-cellular-automata-fluid-simulator) | Graphics & Simulation | Grid arrays, CA rules, double buffering | C/C++, Python (pygame), Rust, JS |
| 2 | [Concurrent TCP Chat Server](#2-concurrent-tcp-chat-server) | Networks | Sockets, I/O multiplexing, threading | C, Python, Go, Rust |
| 3 | [Interactive Unix Command Shell](#3-interactive-unix-command-shell) | Systems | `fork`, `execvp`, `waitpid`, `chdir` | C (recommended), Rust |

---

## 1. Cellular Automata Fluid Simulator

**Objective:** Build a 2D pixel-based physics simulator using cellular automata, where particles interact according to their material properties (sand falls, water flows, solid boundaries block).

**Concepts covered:** 2D grid arrays, cellular automata state rules, double buffering, basic rendering loops, boundary checks.

### Core Requirements

- [ ] Initialize a 2D grid (e.g., 128x128 or 256x256) representing the world.
- [ ] Implement an update loop that processes the grid **bottom-to-top**, so particles that already fell this frame are not updated again.
- [ ] Support at least three materials:
  - **Sand:** falls straight down if empty; if blocked, tries down-left or down-right.
  - **Water:** falls down or diagonally; if blocked below, disperses horizontally left or right.
  - **Wall/Wood:** static, impassable, never updates.
- [ ] Correct particle swapping so dense materials (sand) sink through lighter fluids (water).

### Inspiration

Look at existing engines such as *Noita*, built on the *Falling Everything* engine.

### Tips

- Randomize left/right choice to avoid visible directional bias.
- Use double buffering (or a "moved this frame" flag) to prevent double updates.
- Add mouse input to paint materials for easier testing.

### Suggested Run Command

```bash
# Example, adjust to your language/toolchain
python sandbox.py
```

---

## 2. Concurrent TCP Chat Server

**Objective:** Build a multi-client chat room over raw TCP sockets. Multiple users connect simultaneously, send messages, and see broadcasts from others in real time.

**Concepts covered:** TCP/IP socket lifecycle (`bind`, `listen`, `accept`), I/O multiplexing (`select`, `poll`, `epoll`) or threading, blocking vs. non-blocking connections, state management.

### Core Requirements

- [ ] Create a socket, bind it to a local port (e.g., `8080`), and listen for incoming connections.
- [ ] Maintain a dynamic list of active client sockets/file descriptors.
- [ ] Handle many connections concurrently without one idle client freezing the server.
- [ ] Broadcast each received message to all *other* connected clients.
- [ ] Handle disconnects gracefully (e.g., a user closes their terminal) by removing the client without crashing.

### Bonus

- [ ] Channels / rooms
- [ ] Message history
- [ ] A UI that replicates how Discord looks and works

### Testing

```bash
# Start the server
./chat_server 8080

# In separate terminals
nc localhost 8080
```

Open several `nc` (netcat) clients, send messages from each, and confirm others receive them. Kill a client mid-session to verify the server stays up.

---

## 3. Interactive Unix Command Shell

**Objective:** Develop a lightweight command-line interpreter that launches external programs and handles built-in commands like `cd` and `exit`.

**Concepts covered:** Unix system calls (`fork`, `execvp`, `waitpid`, `chdir`), process lifecycles, memory management, array manipulation.

### Core Requirements

- [ ] Infinite REPL showing a prompt (e.g., `myshell> `) and waiting for input.
- [ ] Parse input into a command and an argument array (handle whitespace).
- [ ] `fork()` a child and use the `exec()` family to run the requested binary (e.g., `ls -l`, `cat file.txt`).
- [ ] Parent uses `wait()` / `waitpid()` until the child finishes before redrawing the prompt.
- [ ] Built-ins:
  - `cd`: must call `chdir()` **in the parent**, not in a forked child.
  - `exit`: terminates the shell.

### Bonus

- [ ] Piping with `|`
- [ ] Redirection with `>` (and `<`, `>>`) via file descriptor manipulation (`dup2`)
- [ ] Other built-ins

### Build & Run

```bash
gcc -Wall -Wextra -o myshell myshell.c
./myshell
```

### Tips

- Free all allocated memory per loop iteration; check with `valgrind`.
- Handle `fork`/`exec` failures and print errors with `perror`.
- Handle empty input and EOF (Ctrl+D) cleanly.

---

## General Guidelines

- Pick one language per project and document build/run steps in your own project README.
- Commit early and often; implement core requirements before bonuses.
- Test edge cases: empty input, abrupt disconnects, grid boundaries.

## Suggested Repository Layout

```
.
├── README.md
├── 01-fluid-simulator/
├── 02-tcp-chat-server/
└── 03-unix-shell/
```
