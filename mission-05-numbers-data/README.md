# Mission 5 — Numbers and data

## 1. Task
The objective of this mission is to understand data representation in computing:
- Perform manual conversions between decimal (base 10), binary (base 2), and hexadecimal (base 16) numeral systems.
- Verify manual math using Python's built-in conversion functions (`bin()`, `hex()`, and `int()`).
- Develop an interactive Python program (`number_converter.py`) to convert user-input decimal numbers to binary and hexadecimal.
- Analyze how text is represented and encoded using the ASCII and UTF-8 standards.

---

## 2. Work completed
- **Task 5.1:** Calculated step by step manual conversions for all 7 required arithmetic problems.
- **Task 5.2:** Tested each conversion using the Python interactive REPL and verified 100% agreement with manual working.
- **Task 5.3:** Built and tested `number_converter.py` with three distinct test values 42, 255 and 1024, made a output table.
- **Task 5.4:** Researched character encodings, documented ASCII decimal values for 'A' and 'a', explained why encoding standards are necessary, and identified non ASCII Unicode characters.

---

## 3. Commands / tools used

| Command / Tool / Function | Purpose |
| :--- | :--- |
| `python3` | Launched the Python interactive shell and executed `number_converter.py`. |
| `bin(n)` | Built-in Python function that converts an integer into a binary string prefixed with `0b`. |
| `hex(n)` | Built-in Python function that converts an integer into a hexadecimal string prefixed with `0x`. |
| `int(string, base)` | Built-in Python function that parses a string representation of a number in a given base to a decimal integer. |
| `ord(c)` | Python function returning the Unicode/ASCII integer code point of a character. |
| `input()` | Takes user console input as a string in `number_converter.py`. |
| `git` | Stages, commits, and pushes mission documentation and scripts to GitHub. |

---

## 4. Understanding

### Task 5.1 — Convert numbers by hand

#### 1. Convert decimal 13 to binary
- **Division by 2 method:**
  - $13 \div 2 = 6$, remainder **1**
  - $6 \div 2 = 3$, remainder **0**
  - $3 \div 2 = 1$, remainder **1**
  - $1 \div 2 = 0$, remainder **1**
- Read remainders bottom-to-top: **`(1101)₂`**
- *Check:* $(1 \times 8) + (1 \times 4) + (0 \times 2) + (1 \times 1) = 8 + 4 + 0 + 1 = 13$

#### 2. Convert decimal 25 to binary
- **Division by 2 method:**
  - $25 \div 2 = 12$, remainder **1**
  - $12 \div 2 = 6$, remainder **0**
  - $6 \div 2 = 3$, remainder **0**
  - $3 \div 2 = 1$, remainder **1**
  - $1 \div 2 = 0$, remainder **1**
- Read remainders bottom-to-top: **`(11001)₂`**
- *Check:* $(1 \times 16) + (1 \times 8) + (0 \times 4) + (0 \times 2) + (1 \times 1) = 16 + 8 + 1 = 25$

#### 3. Convert binary 1010 to decimal
- **Positional expansion:**
  - $(1 \times 2^3) + (0 \times 2^2) + (1 \times 2^1) + (0 \times 2^0)$
  - $= (1 \times 8) + (0 \times 4) + (1 \times 2) + (0 \times 1) = 8 + 0 + 2 + 0 =$ **`(10)₁₀`**

#### 4. Convert binary 1101 to decimal
- **Positional expansion:**
  - $(1 \times 2^3) + (1 \times 2^2) + (0 \times 2^1) + (1 \times 2^0)$
  - $= (1 \times 8) + (1 \times 4) + (0 \times 2) + (1 \times 1) = 8 + 4 + 0 + 1 =$ **`(13)₁₀`**

#### 5. Convert hexadecimal A to decimal
- In base 16, digits 0–9 represent values 0–9, and letters A–F represent values 10–15.
- Therefore, $A_{16} = (10 \times 16^0) =$ **`(10)₁₀`**

#### 6. Convert hexadecimal 1F to decimal
- **Positional expansion:**
  - $(1 \times 16^1) + (F \times 16^0)$
  - $= (1 \times 16) + (15 \times 1) = 16 + 15 =$ **`(31)₁₀`**

#### 7. Convert binary 1111 to hexadecimal
- Group into 4 bits (nibble): `(1111)₂`
- Decimal value: $(1 \times 8) + (1 \times 4) + (1 \times 2) + (1 \times 1) = 15_{10}$
- In hexadecimal, decimal 15 is represented by: **`(F)₁₆`** (or `0xF`)

---

### Task 5.2 — Verify using Python

| Expression tested in Python | Python Output | Matches manual calculation? |
| :--- | :--- | :---: |
| `bin(13)` | `'0b1101'` | Yes (`1101`) |
| `bin(25)` | `'0b11001'` | Yes (`11001`) |
| `int('1010', 2)` | `10` | Yes (`10`) |
| `int('1101', 2)` | `13` | Yes (`13`) |
| `int('A', 16)` | `10` | Yes (`10`) |
| `int('1F', 16)` | `31` | Yes (`31`) |
| `hex(0b1111)` | `'0xf'` | Yes (`F`) |

---

### Task 5.3 — Build a small number converter

#### Test Results Table

| Test number | Binary output | Hexadecimal output |
| :--- | :--- | :--- |
| **42** | `0b101010` | `0x2a` |
| **255** | `0b11111111` | `0xff` |
| **1024** | `0b10000000000` | `0x400` |

#### What the conversion functions do:
- **`bin(decimal)`:** Takes an integer value and generates its equivalent binary bitstream as a string prefixed with `0b` (indicating base 2).
- **`hex(decimal)`:** Takes an integer and converts it to its compact base 16 representation prefixed with `0x`, mapping groups of 4 bits to single hex digits (0–9, a–f).

---

### Task 5.4 — How is text stored?

1. **ASCII Decimal Codes:**
   - Uppercase **'A'**: `65` (Binary: `01000001`)
   - Lowercase **'a'**: `97` (Binary: `01100001`)
   - *(Note: The difference of 32 represents a single bit flip at position 5).*

2. **Why computers need an encoding standard to store text:**
   - Computer hardware can only store and process binary voltages (0s and 1s). An encoding standard establishes a universal, standardized lookup table that maps specific numerical values to specific visual characters, ensuring that a file written on one system appears identically on any other computer.

3. **Example of a character not part of basic ASCII:**
   - The Indian Rupee symbol (**`₹`**, Unicode `U+20B9`) or the rocket emoji (**`🚀`**, Unicode `U+1F680`). Standard 7-bit ASCII only supports codes 0 to 127 (English alphabet, numbers, and basic symbols), so extended symbols require variable-length multi byte encodings like **UTF-8**.

---

## 5. Difficulties faced
- Remembering to strip or account for Python's formatting prefixes (`0b` for binary and `0x` for hex) when displaying clean output to users.

---

## 6. How I resolved it
- Handled Python prefixes cleanly in `number_converter.py` using string slicing (`[2:]`) to present both raw and clean formats.

---

## 7. Evidence
- N/A

---

## 8. Commit details
- **Commit Message:** `Build number converter and practise data representation`
- git commit -m "Build number converter and practise data representation"