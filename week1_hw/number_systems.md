# Beginner’s Guide to Computer Number Systems

##  The Building Blocks: Bits and Bytes

Computers run on electricity. Inside a computer processor or memory chip, information is stored using millions of tiny electrical switches:

*   **Bit (Binary Digit):** A single switch. It has only two possible states:
    *   `0` = Off
    *   `1` = On
    *   It is the smallest unit of data in computing.
*   **Byte:** A group of 8 bits together (e.g., `01000001`). A single byte can represent 256 different values (from 0 to 255), which is enough to store a single character like the letter "A" or the number "5".

---

## Number Systems Comparison

We use different number systems depending on who is reading the data:

| System | Base | Available Symbols | Main Purpose |
| :--- | :---: | :--- | :--- |
| **Decimal** | Base-10 | 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 | Human counting (based on 10 fingers) |
| **Binary** | Base-2 | 0, 1 | Native computer language (electric pulses) |
| **Hexadecimal** | Base-16 | 0–9 and A, B, C, D, E, F | Human-readable shorthand for long binary numbers |

### The Hexadecimal Letter Values
Because Base-16 needs 16 distinct symbols, single letters are used for values 10 through 15:
*   A = 10
*   B = 11
*   C = 12
*   D = 13
*   E = 14
*   F = 15

---

## How Positional Values Work

In any positional system, digits on the right have the smallest value, and each position to the left grows by multiplying by the base.

### Decimal (Base-10): Powers of 10
The place values are 100s, 10s, 1s ($10^2, 10^1, 10^0$):

$$\text{Number } 342 = (3 \times 100) + (4 \times 10) + (2 \times 1) = 300 + 40 + 2 = 342$$

### Binary (Base-2): Powers of 2
The place values double with every step to the left: 8s, 4s, 2s, 1s ($2^3, 2^2, 2^1, 2^0$).

When reading a 4-bit binary number, line up the place values:

| Place Value | 8 | 4 | 2 | 1 |
| :--- | :---: | :---: | :---: | :---: |
| **Binary Digit** | 1 | 1 | 0 | 1 |

*   A **1** means the switch is **ON** (add that place value).
*   A **0** means the switch is **OFF** (skip that place value).

$$\text{Calculation: } (1 \times 8) + (1 \times 4) + (0 \times 2) + (1 \times 1) = 8 + 4 + 0 + 1 = \mathbf{13}$$

---

##  Converting Binary to Hexadecimal

Because $16 = 2^4$, exactly 4 bits of binary map to 1 Hex digit. To convert a long binary byte into Hex:
1. **Split** the byte into two 4-bit halves (called nibbles).
2. **Calculate** the decimal value of each 4-bit half using 8-4-2-1.
3. **Convert** any value above 9 to its Hex letter (A–F).

### Example: Convert `11010011` to Hex

*   **Step 1: Split into two 4-bit chunks**
    $$\text{Chunk 1: } \mathbf{1101} \quad \mid \quad \text{Chunk 2: } \mathbf{0011}$$

*   **Step 2: Calculate Chunk 1 (1101)**
    $$\text{Values: } (1 \times 8) + (1 \times 4) + (0 \times 2) + (1 \times 1) = 8 + 4 + 0 + 1 = 13$$
    $$13 \text{ in Hex} = \mathbf{D}$$

*   **Step 3: Calculate Chunk 2 (0011)**
    $$\text{Values: } (0 \times 8) + (0 \times 4) + (1 \times 2) + (1 \times 1) = 0 + 0 + 2 + 1 = 3$$
    $$3 \text{ in Hex} = \mathbf{3}$$

*   **Final Result:** `11010011` in binary = **`D3`** in Hexadecimal.

---

## Converting Hexadecimal to Binary

Converting from Hex back to Binary is the reverse process of Section 4: replace every individual Hex symbol with its equivalent 4-bit binary code.

### Steps:
1. Take each Hex digit separately.
2. Convert each digit into a 4-bit binary number using 8-4-2-1.
3. Join the 4-bit groups together.

### Example: Convert `2F` to Binary

*   **Step 1: Convert 2**
    How do we make 2 using 8, 4, 2, 1? $\rightarrow 0\times8 + 0\times4 + 1\times2 + 0\times1$
    *   Binary: `0010`

*   **Step 2: Convert F**
    F in decimal is 15. How do we make 15 using 8, 4, 2, 1? $\rightarrow 1\times8 + 1\times4 + 1\times2 + 1\times1$
    *   Binary: `1111`

*   **Step 3: Combine**
    Put `0010` and `1111` side-by-side: `00101111`

*   **Final Result:** `2F` in Hexadecimal = **`00101111`** in Binary.

---

## Converting Hexadecimal to Decimal (Base-10)

There are two easy ways to convert Hex directly into standard decimal numbers.

### Method A: Using Powers of 16 (Direct Method)
Place values in Hexadecimal increase by powers of 16 from right to left:
*   1s place ($16^0 = 1$)
*   16s place ($16^1 = 16$)
*   256s place ($16^2 = 256$)

#### Example: Convert `2F` to Decimal
1. **Identify place values:**
    *   16s place: Digit is `2`
    *   1s place: Digit is `F` (which equals 15)
2. **Multiply and add:**
    $$\text{Calculation: } (2 \times 16) + (15 \times 1) = 32 + 15 = \mathbf{47}$$

### Method B: Bridge via Binary (Easier for Beginners)
If multiplying by 16 feels tricky, convert the Hex number to Binary first, then add up the binary place values (128, 64, 32, 16, 8, 4, 2, 1):

1. **Convert `2F` to Binary:** `0010 1111` (from Section 5)
2. **Line up under 8-bit place values:**

| Place Value | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Bit** | 0 | 0 | 1 | 0 | 1 | 1 | 1 | 1 |

3. **Add the ON values:**
    $$32 + 8 + 4 + 2 + 1 = \mathbf{47}$$

*   **Final Result:** `2F` in Hexadecimal = **`47`** in Decimal.
