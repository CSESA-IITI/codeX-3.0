## 1. Graphics & Simulation: Cellular Automata Fluid Simulator

**Objective:** Build a 2D pixel-based physics simulator using cellular automata principles where particles interact based on their material properties (e.g., sand falls, water flows, solid boundaries block).

**Concepts Covered:** 2D grid arrays, cellular automata state rules, double buffering, basic rendering loops, and boundary checks.

**Core Requirements:**

* Initialize a 2D grid (e.g., 128x128 or 256x256) representing the simulation world.
* Implement an update loop that processes the grid from bottom-to-top to avoid redundantly updating particles that have already fallen in the current frame.
* Support at least three distinct materials:
* **Sand:** Falls straight down if empty; if blocked, attempts to fall diagonally down-left or down-right.
* **Water:** Falls down or diagonally; if blocked underneath, disperses horizontally to the left or right.
* **Wall/Wood:** Static structural elements that are impassable and do not update.
* Ensure proper particle swapping so dense materials (sand) can sink through lighter fluids (water).
* Take inspiration from already existing engines (like noita, made with the game engine falling everything)

---

## 2. Networks: Concurrent TCP Chat Server

**Objective:** Build a multi-client chat room over raw TCP sockets where multiple users can connect simultaneously, send messages, and see broadcasts from others in real-time.

**Concepts Covered:** TCP/IP socket lifecycle (`bind`, `listen`, `accept`), I/O multiplexing (`select`, `poll`, `epoll`) or threading, blocking vs. non-blocking connections, and state management.

**Core Requirements:**

* Create a socket, bind it to a local port (e.g., 8080), and listen for incoming TCP connections.
* Maintain a dynamic list of active client file descriptors/sockets.
* Handle multiple connections concurrently without freezing the server while waiting for one specific user to type (avoiding blocking I/O pitfalls).
* When a text message is received from one client, broadcast it to all other connected clients.
* Handle client disconnections gracefully (e.g., when a user closes their terminal) by removing them from the active list without crashing the server.
* Bonus: Implement channels, history, UI, replicate how discord looks and works.

---

## 3. Systems: Interactive Unix Command Shell

**Objective:** Develop a lightweight command-line interpreter (CLI) that can launch external system programs and manage local built-in commands like `cd` and `exit`.

**Concepts Covered:** Linux/Unix system calls (`fork`, `execvp`, `waitpid`, `chdir`), process lifecycles, memory management, and array manipulation.

**Core Requirements:**

* Implement an infinite Read-Evaluate-Print Loop (REPL) that displays a prompt (e.g., `myshell> `) and waits for user input.
* Parse the input string into a command and an array of arguments (handling spaces appropriately).
* Use `fork()` to spawn a child process and the `exec()` family of functions to replace the child's image with the requested binary (e.g., executing `ls -l` or `cat file.txt`).
* Use `wait()` or `waitpid()` in the parent process to suspend execution until the child process finishes before re-drawing the prompt.
* Implement built-in commands: `cd` (which must use the `chdir()` system call in the parent process rather than forking) and `exit`.
* Bonus: Implement piping `|`, file descriptor redirection using `>` and other shell built-ins.
