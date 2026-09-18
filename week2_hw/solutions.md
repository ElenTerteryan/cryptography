#  Cryptography - Week 2 - Homework

# 1. MD4 and MD5

### Comparison of MD4 and MD5
* **Digest Length:** Both output a 128-bit (16-byte) hash.
* **Message-Block Size:** Both process messages in chunks of 512 bits (64 bytes).
* **Word Size:** Both work with 32-bit words.
* **Rounds and Steps:**
  * MD4: Has 3 rounds with 16 steps each (48 steps total).
  * MD5: Has 4 rounds with 16 steps each (64 steps total).
* **Boolean Functions:** Both use basic bit logic (like AND, OR, and XOR) in each round. However, MD5 added a slightly different mixing function in round 2 to fix some symmetry weaknesses found in MD4.

### Principal Changes in MD5:
* Added a fourth round to make the mixing deeper.
* Changed the second round's logic function to reduce patterns.
* Added unique mathematical constants to every step (derived from sine waves) to break predictable patterns.
* Changed how message words are picked in rounds 2 and 3.
* Added extra mixing steps at the end of rounds.

### Current Security Status:
Both are completely broken. Computers can find two different files that produce the exact same MD5 hash in just a few seconds. They are totally unsafe for security today.

### Why MD5 was Designed & Why Neither is Collision-Resistant
MD5 was created as an upgrade to MD4 after researchers found clear flaws in MD4's design.

Neither algorithm is safe against collisions today because their underlying architecture (the Merkle-Damgård method) and their internal mixing math are too weak. Modern cryptanalysis allows researchers to systematically track differences through the rounds and build two different messages that output the exact same hash.

---

# 2. SHA-1, SHA-2 and SHA-3

### SHA-1
* **Output Size:** 160 bits.
* **Block Size:** 512 bits.
* **Rounds:** 80 rounds.
* **Construction:** Merkle-Damgård (using the Davies-Meyer structure).
* **Security Status:** Broken. Researchers have successfully demonstrated real-world collisions (such as the SHAttered attack on PDF files).

### SHA-2 (e.g., SHA-256)
* **Output Size:** 256 bits (or up to 512 bits for SHA-512).
* **Block Size:** 512 bits (1024 bits for SHA-512).
* **Rounds:** 64 rounds (80 for SHA-512).
* **Construction:** Merkle-Damgård (using the Davies-Meyer structure).
* **Security Status:** Secure and widely trusted. No practical attacks exist against it.

### SHA-3 (e.g., SHA3-256)
* **Output Size:** 256 bits (configurable).
* **State Size:** 1600 bits total, split into a 1088-bit rate and a 512-bit capacity.
* **Rounds:** 24 rounds of the Keccak permutation.
* **Construction:** Sponge construction.
* **Security Status:** Secure and modern; offers a completely different design that avoids old vulnerabilities.

### Why SHA-256 and SHA3-256 are Different
Even though both give you a 256-bit output string, they are built completely differently under the hood. SHA-256 uses traditional block-processing with modular addition and bit rotations, which makes it vulnerable to a theoretical issue called length-extension. SHA3-256 uses a "sponge" structure based on the Keccak algorithm, where data is absorbed into a wide state and stirred around using complex bit permutations. Because of this sponge design, SHA3-256 is naturally immune to length-extension attacks.

---

# 3. Padding

### Padding in MD5, SHA-1, SHA-256, and SHA-512
These four algorithms use the exact same padding strategy:
1. Append a single 1 bit right after the end of your original message.
2. Append a string of 0 bits so that the total length of the data becomes a specific size short of a full block.
   * For MD5, SHA-1, and SHA-256, you pad until the length is $448$ bits mod $512$ (leaving the last $64$ bits empty).
   * For SHA-512, you pad until the length is $896$ bits mod $1024$ (leaving the last $128$ bits empty).
3. Append the length: Write the original message length (in bits) as a big-endian number into that remaining space at the very end ($64$ bits long for the 512-bit block algorithms, or $128$ bits for SHA-512).

### Comparison with SHA-3 Padding
SHA-3 uses a different method called multi-rate padding (pad10*1). It adds a 1 bit, followed by as many 0 bits as needed, and finishes with a final 1 bit so that the entire padded message fits cleanly into the "rate" portion of the sponge state.

### Why it fits a sponge construction:
Traditional hash functions like SHA-256 use a fixed-block structure and glue the exact message length at the very end (Merkle-Damgård strengthening). The sponge construction doesn't do this; it absorbs data chunks continuously into an internal state. SHA-3 padding simply aligns the message data smoothly with the sponge's rate size rather than keeping a dedicated length counter at the finish line.
