# Mission 4 — How programs run

## 1. Task
The objective of this mission is to understand how computer software executes:
- Write and run a Python script (`hello.py`) from the command line using Python 3.
- Compare how compilers and interpreters translate human readable source code into machine executable actions.
- Understand the trade offs in execution speed and debugging between compiled and interpreted execution models.

---

## 2. Work completed
- **Task 4.1:** Created `hello.py` containing a script that prints `"Hello from Python"`, ran it through the Terminal using `python3 hello.py`, and verified the console output.
- **Task 4.2:** Completed the Compiler vs Interpreter comparison table and wrote an explanation analyzing the differences.

---

## 3. Commands / tools used

| Command / Tool | Purpose |
| :--- | :--- |
| `python3` | The Python 3 runtime interpreter used to execute `hello.py`. |
| `python3 hello.py` | Command executed in the terminal to run the Python script. |
| `cat hello.py` | Used to inspect and display the source code of `hello.py` in the terminal. |
| `git` | Stages, commits, and pushes mission files to GitHub. |

---

## 4. Understanding

### Task 4.1 — Create and run a Python program
- **File created:** `mission-04-programs/hello.py`
- **Code:**
  ```python
  print("Hello from Python")
  ```
- **Terminal execution:**
  ```bash
  python3 hello.py
  ```
- **Observed output:**
  ```text
  Hello from Python
  ```
- **Execution observation:** When `python3` was used, the Python interpreter loaded the script, checked the syntax, and immediately executed the `print()` function, sending the string to standard output without requiring a manual compilation build step.

---

### Task 4.2 — Compare compiler and interpreter

| Point | Compiler | Interpreter |
| :--- | :--- | :--- |
| **When translation / execution happens** | Translates the entire source code into machine code ahead of time before execution begins. | Translates and executes source code line by line dynamically at runtime. |
| **Typical output** | Produces a executable machine-code binary file that runs independently. | Does not produce a separate machine code binary executes instructions directly in memory. |
| **One example** | C, C++, Rust, Go | Python, JavaScript, Ruby |
| **One advantage** | **High performance & speed:** Code runs significantly faster because it is already optimized native machine code for the target CPU. | **Rapid development & easy debugging:** Code can be tested immediately without waiting for build cycles and errors are pinpointed line by line. |

#### Explanation of Differences
A compiler processes the complete program source code all at once before the program can ever run, translating it into binary machine code that the CPU executes directly at maximum speed. In contrast, an interpreter reads, converts, and carries out source code instructions on the fly during program runtime. This means compiled programs deliver faster execution performance and early compile time error checking, whereas interpreted languages provide greater portability across operating systems and an interactive, rapid debugging environment. Many modern languages utilize a hybrid model, compiling source code into intermediate bytecode `.pyc` before running it.

---

## 5. Difficulties faced
- Ensuring the command `python3` was used explicitly rather than the legacy `python` command, which may not be aliased or may point to an older system environment.

---

## 6. How I resolved them
- Confirmed the active Python runtime version using `python3 --version` (`Python 3.9.6`).


---

## 7. Evidence
- N/A

---

## 8. Commit details
- **Commit Message:** `Compare compilers and interpreters`
- git commit -m "Compare compilers and interpreters"