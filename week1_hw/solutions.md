#  Cryptography - Week 1 - Homework

##  Substitution Cipher Decryption
By analyzing the letter frequencies against the provided table, we substitute each ciphertext letter to reveal the original text:

### Decrypted Message:
> "the main component of a rotor machine is a wheel called the rotor. this is a disk with two faces that implements a simple substitution. around the perimeter of each face, there are twenty six evenly spaced electrical contacts. each contact on one face is connected by an electrical wire to exactly one contact on the other face. each contact are marked with alphabet letters a to z clockwise."

---

#  Conversions

##  Convert Decimal to Binary

### $13_{10}$
*   Find largest power of 2 fitting in 13: $8 \rightarrow (13 - 8 = 5) \rightarrow \mathbf{1}$ in 8s place
*   Largest power fitting in 5: $4 \rightarrow (5 - 4 = 1) \rightarrow \mathbf{1}$ in 4s place
*   Largest power fitting in 1: 2 does not fit $\rightarrow (1 - 0 = 1) \rightarrow \mathbf{0}$ in 2s place
*   Fits 1: $1 \rightarrow (1 - 1 = 0) \rightarrow \mathbf{1}$ in 1s place
*   **Result:** $1101_2$

### $27_{10}$
*   $27 - 16 = 11 \rightarrow \mathbf{1}$ (16s)
*   $11 - 8 = 3 \rightarrow \mathbf{1}$ (8s)
*   $3 - 4$ (doesn't fit) $\rightarrow \mathbf{0}$ (4s)
*   $3 - 2 = 1 \rightarrow \mathbf{1}$ (2s)
*   $1 - 1 = 0 \rightarrow \mathbf{1}$ (1s)
*   **Result:** $11011_2$

### $45_{10}$
*   $45 - 32 = 13 \rightarrow \mathbf{1}$ (32s)
*   $13 - 16$ (doesn't fit) $\rightarrow \mathbf{0}$ (16s)
*   $13 - 8 = 5 \rightarrow \mathbf{1}$ (8s)
*   $5 - 4 = 1 \rightarrow \mathbf{1}$ (4s)
*   $1 - 2$ (doesn't fit) $\rightarrow \mathbf{0}$ (2s)
*   $1 - 1 = 0 \rightarrow \mathbf{1}$ (1s)
*   **Result:** $101101_2$

### $100_{10}$
*   $100 - 64 = 36 \rightarrow \mathbf{1}$ (64s)
*   $36 - 32 = 4 \rightarrow \mathbf{1}$ (32s)
*   $4 - 16$ (doesn't fit) $\rightarrow \mathbf{0}$ (16s)
*   $4 - 8$ (doesn't fit) $\rightarrow \mathbf{0}$ (8s)
*   $4 - 4 = 0 \rightarrow \mathbf{1}$ (4s)
*   Remaining places (2s, 1s) are $\mathbf{0}$
*   **Result:** $1100100_2$

---

##  Convert Decimal to Hexadecimal

### $29_{10}$
*   Divide by 16: $29 \div 16 = 1$ with remainder $13$
*   Remainder 13 in Hex is **D**
*   Read bottom to top: $\mathbf{1D_{16}}$

### $156_{10}$
*   Divide by 16: $156 \div 16 = 9$ with remainder $12$
*   Remainder 12 in Hex is **C**
*   Read bottom to top: $\mathbf{9C_{16}}$

### $255_{10}$
*   Divide by 16: $255 \div 16 = 15$ with remainder $15$
*   Remainder 15 in Hex is **F**
*   Quotient 15 in Hex is **F**
*   **Result:** $\mathbf{FF_{16}}$

---

##  Convert $11010110_2$ to Decimal and Hexadecimal

### Decimal Step:
*   **Place values:** $\mathbf{128} \quad \mathbf{64} \quad \mathbf{32} \quad \mathbf{16} \quad \mathbf{8} \quad \mathbf{4} \quad \mathbf{2} \quad \mathbf{1}$
*   **Bits:** $\quad\quad\quad 1 \quad\ \ \  1 \quad\ \ \ 0 \quad\ \ \ 1 \quad\ 0 \quad\ 1 \quad\ 1 \quad\ 0$
*   **Sum:** $128 + 64 + 0 + 16 + 0 + 4 + 2 + 0 = \mathbf{214_{10}}$

### Hexadecimal Step:
*   Group into 4-bit pairs: `1101` and `0110`
    *   $1101 = 8 + 4 + 0 + 1 = 13 \rightarrow \mathbf{D}$
    *   $0110 = 0 + 4 + 2 + 0 = 6 \rightarrow \mathbf{6}$
*   **Result:** $\mathbf{D6_{16}}$

---

##  Convert $3\text{A}_{16}$ to Binary and Decimal

### Binary Step:
*   $3 = 0\times8 + 0\times4 + 1\times2 + 1\times1 \rightarrow \mathbf{0011}$
*   $\text{A (10)} = 1\times8 + 0\times4 + 1\times2 + 0\times1 \rightarrow \mathbf{1010}$
*   **Result:** $00111010_2$

### Decimal Step:
*   Multiply by powers of 16: $(3 \times 16^1) + (10 \times 16^0) = 48 + 10 = \mathbf{58_{10}}$

---

##  Complete All Representations ($172_{10}$)

### Decimal to Binary:
*   $172 - 128 = 44 \rightarrow \mathbf{1}$ (128s)
*   $44 - 64$ (doesn't fit) $\rightarrow \mathbf{0}$ (64s)
*   $44 - 32 = 12 \rightarrow \mathbf{1}$ (32s)
*   $12 - 16$ (doesn't fit) $\rightarrow \mathbf{0}$ (16s)
*   $12 - 8 = 4 \rightarrow \mathbf{1}$ (8s)
*   $4 - 4 = 0 \rightarrow \mathbf{1}$ (4s)
*   Remaining places (2s, 1s) are $\mathbf{0}$
*   **Binary Result:** $10101100_2$

### Binary to Hexadecimal:
*   Split `10101100` into `1010` and `1100`
    *   $1010 = 8 + 2 = 10 \rightarrow \mathbf{A}$
    *   $1100 = 8 + 4 = 12 \rightarrow \mathbf{C}$
*   **Hex Result:** $\mathbf{AC_{16}}$

---

#  ASCII Encoding & Decoding

## 1. Encode "CAT" in ASCII (Hexadecimal)
*   Look up ASCII decimal values: $\text{C} = 67, \text{A} = 65, \text{T} = 84$
*   Convert each decimal to Hex ($x \div 16$):
    *   **C:** $67 \div 16 = 4$ remainder $3 \rightarrow \mathbf{43}$
    *   **A:** $65 \div 16 = 4$ remainder $1 \rightarrow \mathbf{41}$
    *   **T:** $84 \div 16 = 5$ remainder $4 \rightarrow \mathbf{54}$
*   **Result:** $\mathbf{43\ 41\ 54_{16}}$

## 2. Encode "KEY" in ASCII (8-bit Binary)
*   Look up ASCII decimal values: $\text{K} = 75, \text{E} = 69, \text{Y} = 89$
*   Convert each decimal to 8-bit binary ($128\text{-}64\text{-}32\text{-}16\text{-}8\text{-}4\text{-}2\text{-}1$):
    *   **K (75):** $75 - 64 = 11 \rightarrow 11 - 8 = 3 \rightarrow 3 - 2 = 1 \rightarrow 1 - 1 = 0 \rightarrow \mathbf{01001011_2}$
    *   **E (69):** $69 - 64 = 5 \rightarrow 5 - 4 = 1 \rightarrow 1 - 1 = 0 \rightarrow \mathbf{01000101_2}$
    *   **Y (89):** $89 - 64 = 25 \rightarrow 25 - 16 = 9 \rightarrow 9 - 8 = 1 \rightarrow 1 - 1 = 0 \rightarrow \mathbf{01011001_2}$
*   **Result:** $01001011_2,\ 01000101_2,\ 01011001_2$

## 3. Encode "CODE" in Hexadecimal and Binary
*   Look up ASCII values: $\text{C} = 67, \text{O} = 79, \text{D} = 68, \text{E} = 69$
*   Convert to Hexadecimal:
    *   **C (67):** $67 \div 16 = 4 \text{ rem } 3 \rightarrow \mathbf{43}$
    *   **O (79):** $79 \div 16 = 4 \text{ rem } 15 \rightarrow \mathbf{4F}$
    *   **D (68):** $68 \div 16 = 4 \text{ rem } 4 \rightarrow \mathbf{44}$
    *   **E (69):** $69 \div 16 = 4 \text{ rem } 5 \rightarrow \mathbf{45}$
    *   **Hex Result:** $\mathbf{43\ 4F\ 44\ 45_{16}}$
*   Convert Hex to 8-bit Binary (expand each Hex digit to 4 bits):
    *   **43** $\rightarrow 4\ (0100), 3\ (0011) \rightarrow \mathbf{01000011_2}$
    *   **4F** $\rightarrow 4\ (0100), \text{F}\ (1111) \rightarrow \mathbf{01001111_2}$
    *   **44** $\rightarrow 4\ (0100), 4\ (0100) \rightarrow \mathbf{01000100_2}$
    *   **45** $\rightarrow 4\ (0100), 5\ (0101) \rightarrow \mathbf{01000101_2}$
    *   **Binary Result:** $01000011\ 01001111\ 01000100\ 01000101_2$

## 4. Decode Hexadecimal ASCII Codes: `43 52 59 50 54 4F`
*   Convert Hex to Binary:
    *   **43** $\rightarrow \mathbf{01000011_2}$
    *   **52** $\rightarrow \mathbf{01010010_2}$
    *   **59** $\rightarrow \mathbf{01011001_2}$
    *   **50** $\rightarrow \mathbf{01010000_2}$
    *   **54** $\rightarrow \mathbf{01010100_2}$
    *   **4F** $\rightarrow \mathbf{01001111_2}$
*   Convert Hex to Decimal and find ASCII character:
    *   **43** $\rightarrow (4 \times 16) + 3 = 67 \rightarrow \mathbf{C}$
    *   **52** $\rightarrow (5 \times 16) + 2 = 82 \rightarrow \mathbf{R}$
    *   **59** $\rightarrow (5 \times 16) + 9 = 89 \rightarrow \mathbf{Y}$
    *   **50** $\rightarrow (5 \times 16) + 0 = 80 \rightarrow \mathbf{P}$
    *   **54** $\rightarrow (5 \times 16) + 4 = 84 \rightarrow \mathbf{T}$
    *   **4F** $\rightarrow (4 \times 16) + 15 = 79 \rightarrow \mathbf{O}$
*   **Decoded Message:** CRYPTO
