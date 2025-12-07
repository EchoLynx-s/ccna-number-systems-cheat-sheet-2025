# CCNA – Number Systems (Module 5)

Quick-reference notes for NetAcad CCNA – **Module 5: Number Systems**.  
Focus is on how binary and hexadecimal work, and how they relate to IPv4 and IPv6
addressing.

I use this repo to revise conversions (decimal ↔ binary ↔ hex), IP addressing
relationships, and key terms for labs, Packet Tracer, and exams.

---

## Table of Contents

- [Module 5 Overview](#module-5-overview)
- [Module Map](#module-map)

- [5.0 Introduction](#50-introduction)  
  - [5.0.1 Why should I take this module?](#501-why-should-i-take-this-module)  
  - [5.0.2 What will I learn to do in this module?](#502-what-will-i-learn-to-do-in-this-module)

- [5.1 Binary Number System](#51-binary-number-system)  
  - [5.1.1 Binary and IPv4 Addresses](#511-binary-and-ipv4-addresses)  
  - [5.1.2 Video – Converting Between Binary and Decimal Numbering Systems](#512-video--converting-between-binary-and-decimal-numbering-systems)  
  - [5.1.3 Binary Positional Notation](#513-binary-positional-notation)  
  - [5.1.4 Check Your Understanding – Binary Number System](#514-check-your-understanding--binary-number-system)  
  - [5.1.5 Convert Binary to Decimal](#515-convert-binary-to-decimal)  
  - [5.1.6 Activity – Binary to Decimal Conversions](#516-activity--binary-to-decimal-conversions)  
  - [5.1.7 Decimal to Binary Conversion](#517-decimal-to-binary-conversion)  
  - [5.1.8 Decimal to Binary Conversion Example](#518-decimal-to-binary-conversion-example)  
  - [5.1.9 Activity – Decimal to Binary Conversions](#519-activity--decimal-to-binary-conversions)  
  - [5.1.10 Activity – Binary Game](#5110-activity--binary-game)  
  - [5.1.11 IPv4 Addresses](#5111-ipv4-addresses)

- [5.2 Hexadecimal Number System](#52-hexadecimal-number-system)  
  - [5.2.1 Hexadecimal and IPv6 Addresses](#521-hexadecimal-and-ipv6-addresses)  
  - [5.2.2 Video – Converting Between Hexadecimal and Decimal Numbering Systems](#522-video--converting-between-hexadecimal-and-decimal-numbering-systems)  
  - [5.2.3 Decimal to Hexadecimal Conversions](#523-decimal-to-hexadecimal-conversions)  
  - [5.2.4 Hexadecimal to Decimal Conversion](#524-hexadecimal-to-decimal-conversion)  
  - [5.2.5 Check Your Understanding – Hexadecimal Number System](#525-check-your-understanding--hexadecimal-number-system)

- [5.3 Module Practice and Quiz](#53-module-practice-and-quiz)  
  - [5.3.1 What did I learn in this module?](#531-what-did-i-learn-in-this-module)  
  - [5.3.2 Module Quiz – Number Systems](#532-module-quiz--number-systems)

---

## Module 5 Overview

### Goal of the module

Understand how computers represent numbers and addresses:

- How the **binary** system works and why networks love powers of two.
- How binary maps to **IPv4 addresses** (octets, ranges, subnets).
- How the **hexadecimal** system compresses long binary strings.
- How hex is used with **IPv6 addresses** and MAC addresses.
- How to quickly convert **decimal ↔ binary ↔ hex** for exam questions and subnetting.

This cheat sheet is my personal brain-dump for Module 5 so I can quickly find:

- Step-by-step conversion methods (with patterns I can memorise).
- Examples that tie binary/hex to real **IP addressing**.
- Small practice tables or mini-exercises I can re-do before quizzes.

---

## Module Map

- **5.0 – Introduction**  
  Why number systems matter for networking and addressing.

- **5.1 – Binary Number System**  
  Core binary concepts, positional notation, and how binary underpins IPv4.

- **5.2 – Hexadecimal Number System**  
  Hex digits, conversions, and how hex simplifies IPv6 notation.

- **5.3 – Module Practice and Quiz**  
  Wrap-up, “What did I learn?” summary, and graded quiz.

---

## 5.0 Introduction

### 5.0.1 Why should I take this module?

Networking lives in **binary**.  
That nice human-friendly IPv4 address `192.168.10.10` is really a 32-bit string of 1s
and 0s. IPv6 addresses are even longer: 128 bits. Binary is how hosts, routers and
switches actually see addresses; dotted decimal or hex is just for us.

As a network administrator you must be able to:

- Read a binary IPv4 address and convert it to dotted decimal.
- Take a dotted decimal address and convert it to binary.
- Move comfortably between **decimal, binary and hexadecimal** representations.

This module gives you those skills and reinforces them with practice activities and the
Binary Game, so conversions become something you can do almost automatically.

---

### 5.0.2 What will I learn to do in this module?

**Module title:** Number Systems  

**Module objective:** Calculate numbers between decimal, binary and hexadecimal systems.

By the end of this module I should be able to:

- Work with the **Binary Number System**  
  Convert numbers between decimal and binary, and understand how binary is used
  in IPv4 addressing.

- Work with the **Hexadecimal Number System**  
  Convert numbers between decimal and hexadecimal, and understand how hex is used
  in IPv6 addresses (and other networking contexts like MAC addresses).

---

## 5.1 Binary Number System

### 5.1.1 Binary and IPv4 Addresses

Every IPv4 address starts as **binary**: a 32-bit pattern of 1s and 0s.  
Those 32 bits are split into four 8-bit groups called **octets**. Each octet is one byte,
and in dotted-decimal notation it appears as a number from 0 to 255.

Example:

- Binary address (one octet shown): `11000000`
- Same octet in decimal: `192`

An IPv4 address like `192.168.10.10` is really four of these 8-bit binary values
stacked together. Devices on the network (PCs, routers, servers) use the binary
form internally to make forwarding decisions, apply subnet masks, and compare
network vs host bits.

Humans find long binary strings hard to read and remember, so we use dotted decimal
as a shorthand. But for subnetting, address planning and exam questions, I must be
comfortable converting between:

- Binary ↔ decimal for each octet.
- Full 32-bit binary addresses ↔ dotted-decimal IPv4 addresses.

This section starts building those skills.

---

### 5.1.2 Video – Converting Between Binary and Decimal Numbering Systems

The video reviews **positional notation** in decimal and then applies the same idea
to binary.

Key points I want to remember:

- Decimal is **base 10**, binary is **base 2**.
- Each position in a number has a **place value**:
  - Decimal: powers of 10 (1, 10, 100, 1000, …).
  - Binary: powers of 2 (1, 2, 4, 8, 16, 32, 64, 128, …).
- To convert from decimal to binary:
  1. List the powers of two (for IPv4, usually 128 down to 1).
  2. Starting from the largest value, decide if you “use” that value (1) or not (0).
  3. Subtract any value you use from the remaining decimal number.
  4. Continue until you reach 0; the 1/0 choices give you the binary bits.
- To convert from binary to decimal:
  1. Line up the bits with their place values (128, 64, 32, 16, 8, 4, 2, 1).
  2. Add the values for every position that has a 1.
  3. The total is the decimal result.

The video finishes with full IP-address examples, converting each 8-bit octet in turn
to get the final dotted-decimal IPv4 address, like:

`11000000.10101000.00000001.01100101` → `192.168.1.101`

---

### 5.1.3 Binary Positional Notation

**Positional notation** means that the value of a digit depends on *where* it sits in
the number. You already know this from decimal, even if you never called it that.

#### Decimal positional notation (review)

- Decimal is base 10, so the **radix** is 10.
- Place values grow as powers of 10:  
  `10⁰ = 1`, `10¹ = 10`, `10² = 100`, `10³ = 1000`, and so on.
- Example: the number **1234**.

  - 1 is in the thousands place → `1 × 1000 = 1000`
  - 2 is in the hundreds place → `2 × 100 = 200`
  - 3 is in the tens place → `3 × 10 = 30`
  - 4 is in the ones place → `4 × 1 = 4`  

  Add them up: `1000 + 200 + 30 + 4 = 1234`.

Each column is a power of ten, and the digit tells how many of that value we have.

#### Binary positional notation

Binary works exactly the same way but with **base 2**:

- The radix is 2.
- Place values are powers of 2 from right to left:  
  `2⁰ = 1`, `2¹ = 2`, `2² = 4`, `2³ = 8`, `2⁴ = 16`, `2⁵ = 32`, `2⁶ = 64`, `2⁷ = 128`.
- With 8 bits (one octet), the place values are:  
  `128  64  32  16  8  4  2  1`.

Each bit can only be **0** or **1**:

- 0 means “no copies” of that place value.
- 1 means “one copy” of that place value.

Example: binary `11000000` → decimal

- Bits: `1 1 0 0 0 0 0 0`
- Place values: `128 64 32 16 8 4 2 1`
- Calculation: `1×128 + 1×64 + 0×32 + … + 0×1 = 192`.

So `11000000₂ = 192₁₀`.

This is exactly how each IPv4 octet is interpreted by a router. Understanding
positional notation makes all the later conversion steps (and subnetting) much easier.

---

### 5.1.4 Check Your Understanding – Binary Number System

These quick questions make sure I really understand how to line up decimal IPv4
addresses with their binary form.

**Example 1 – 192.168.11.10**

To get the binary form, I convert each octet separately:

- 192 → `11000000`  (128 + 64)
- 168 → `10101000`  (128 + 32 + 8)
- 11  → `00001011`  (8 + 2 + 1)
- 10  → `00001010`  (8 + 2)

Put together:  
`192.168.11.10` → **`11000000.10101000.00001011.00001010`**

**Example 2 – 172.16.31.30**

Again, octet by octet:

- 172 → `10101100`  (128 + 32 + 8 + 4)
- 16  → `00010000`  (16)
- 31  → `00011111`  (16 + 8 + 4 + 2 + 1)
- 30  → `00011110`  (16 + 8 + 4 + 2)

So:  
`172.16.31.30` → **`10101100.00010000.00011111.00011110`**

The key idea: never try to convert a whole 32-bit address at once. Always break it
into four 8-bit octets and use the 128–1 place-value table.

---

### 5.1.5 Convert Binary to Decimal

This section shows the **reverse direction**: binary IPv4 → dotted-decimal.

Process:

1. Split the 32-bit binary address into four 8-bit octets.
2. For each octet, line up its bits with the place values:  
   `128 64 32 16 8 4 2 1`
3. Multiply each place value by the bit (0 or 1).
4. Add the results to get the decimal value of that octet.

Example using one octet:

- Bits: `11000000`
- Calculation:  
  `1×128 + 1×64 + 0×32 + 0×16 + 0×8 + 0×4 + 0×2 + 0×1 = 192`

Repeat for all four octets; that’s how the course gets from  
`11000000.10101000.00001011.00001010` to `192.168.11.10`.

---

### 5.1.6 Activity – Binary to Decimal Conversions

This interactive tool is just **drill practice** for step 5.1.5:

- It gives me a random 8-bit binary number.
- Underneath is the familiar table: powers of 2 (128–1) and the bit values.
- My job is to type the correct **decimal value** in the answer box.

I keep repeating this until I can instantly recognise common patterns, for example:

- `11111111` → 255  
- `10000000` → 128  
- `01111111` → 127  
- `11000000` → 192  
- `00001111` → 15  

Once these are in my head, subnetting and IP math become much faster.

---

### 5.1.7 Decimal to Binary Conversion

Now we go the other way: **decimal octet → binary**.  
NetAcad uses a flowchart based on the same 128–1 place-value table.

Algorithm for one octet:

1. Start with the decimal value *n* and the left-most place value **128**.
2. Ask: “Is *n* ≥ 128?”
   - If **yes**: write `1` in that bit position and set `n = n − 128`.
   - If **no**: write `0` and keep *n* as it is.
3. Move to the next place value (64, then 32, 16, 8, 4, 2, 1).
4. Repeat the same question each time (“Is *n* ≥ this place value?”), writing 1 or 0
   and subtracting when needed.
5. When you reach the 1’s place, you will have eight bits: the binary octet.

Example: convert **168** to binary

- Start: `n = 168`
- 128? 168 ≥ 128 → bit = 1, new *n* = 168 − 128 = 40
- 64? 40 ≥ 64? no → bit = 0, *n* = 40
- 32? 40 ≥ 32 → bit = 1, *n* = 40 − 32 = 8
- 16? 8 ≥ 16? no → bit = 0, *n* = 8
- 8? 8 ≥ 8 → bit = 1, *n* = 8 − 8 = 0
- 4? 0 ≥ 4? no → bit = 0
- 2? 0 ≥ 2? no → bit = 0
- 1? 0 ≥ 1? no → bit = 0

Bits from left to right: **`10101000`**  
So 168₁₀ = 10101000₂.

This is exactly the same method the video demo uses for building binary octets in an
IPv4 address.
---

### 5.1.8 Decimal to Binary Conversion Example

This example applies the decimal→binary method to a full IPv4 address:
**192.168.10.11**.  
Each octet is handled separately using the 128–1 place-value table.

#### First octet – 192

Start with `n = 192` and test each place value from left to right:

- 128? 192 ≥ 128 → bit = 1, new *n* = 192 − 128 = 64
- 64? 64 ≥ 64 → bit = 1, *n* = 64 − 64 = 0
- 32? 0 ≥ 32? no → bit = 0
- 16? 0 ≥ 16? no → bit = 0
- 8? 0 ≥ 8? no → bit = 0
- 4? 0 ≥ 4? no → bit = 0
- 2? 0 ≥ 2? no → bit = 0
- 1? 0 ≥ 1? no → bit = 0

Result: **192₁₀ = 11000000₂**

#### Second octet – 168

`n = 168`

- 128? 168 ≥ 128 → bit = 1, *n* = 168 − 128 = 40
- 64? 40 ≥ 64? no → bit = 0
- 32? 40 ≥ 32 → bit = 1, *n* = 40 − 32 = 8
- 16? 8 ≥ 16? no → bit = 0
- 8? 8 ≥ 8 → bit = 1, *n* = 8 − 8 = 0
- 4? 0 ≥ 4? no → bit = 0
- 2? 0 ≥ 2? no → bit = 0
- 1? 0 ≥ 1? no → bit = 0

Result: **168₁₀ = 10101000₂**

#### Third octet – 10

Here we can see the pattern quickly:

- 10 = 8 + 2 → we need the 8’s and 2’s positions set to 1.

Binary: `00001010` (1 in the 8 and 2 positions, 0 everywhere else).

#### Fourth octet – 11

- 11 = 8 + 2 + 1 → set the 8’s, 2’s and 1’s positions to 1.

Binary: `00001011`.

#### Final result

Putting the four octets together:

- Decimal: **192.168.10.11**
- Binary: **`11000000.10101000.00001010.00001011`**

This example shows how the same step-by-step method works for every octet, and
how sometimes it’s faster to recognise “easy” numbers (like 10 = 8+2 or 11 = 8+2+1)
instead of doing all the subtractions.

---
### 5.1.9 Activity – Decimal to Binary Conversions

This tool is the mirror of 5.1.6, but now I convert **decimal → 8-bit binary**.

- The activity shows a random decimal value (e.g. **232**) at the top.
- Below that is the powers-of-two table: 128, 64, 32, 16, 8, 4, 2, 1.
- My job is to decide for each position if I need that value (bit = 1) or not (bit = 0),
  until I’ve built the full 8-bit binary number.

Example mental process for 232:

- 232 ≥ 128 → 1, remainder 104  
- 104 ≥ 64 → 1, remainder 40  
- 40 ≥ 32 → 1, remainder 8  
- 8 ≥ 16? no → 0  
- 8 ≥ 8 → 1, remainder 0  
- Remaining positions (4, 2, 1) → 0  

So 232₁₀ = **11101000₂**.

I repeat this until I can do common values without the table, which will be crucial
for quick subnetting later.

---

### 5.1.10 Activity – Binary Game

Cisco’s **Binary Game** is a gamified way to drill binary skills:

- Numbers drop or appear and I must quickly enter the correct binary (or decimal)
  before time runs out.
- It trains me to recognise patterns like `128+64+8` instantly, instead of
  always adding from scratch.
- There are also mobile “binary game” apps that do the same thing.

This isn’t new theory; it’s pure speed practice so binary/decimal conversions become
muscle memory.

---

### 5.1.11 IPv4 Addresses

Computers and routers think in **binary**, but humans prefer **decimal**.  
This section ties everything together using the example IPv4 address:

**192.168.10.10**

There are three views of the same address:

1. **Dotted decimal view**

   - Shown as: `192.168.10.10`
   - This is how we usually type and read IP addresses.
   - Each number is one **octet** (0–255).

2. **Octet view**

   Each decimal octet has a matching 8-bit binary value:

   - 192 → `11000000`
   - 168 → `10101000`
   - 10  → `00001010`
   - 10  → `00001010` (again)

   So we can map it as:

   - `192`  → `11000000`  
   - `168`  → `10101000`  
   - `10`   → `00001010`  
   - `10`   → `00001010`

3. **32-bit binary view**

   When the computer stores or processes the address, it treats it as one continuous
   32-bit stream:

   ```text
   11000000 10101000 00001010 00001010


---

## 5.2 Hexadecimal Number System

### 5.2.1 Hexadecimal and IPv6 Addresses

Hexadecimal (hex) is a **base-16** number system.  
It uses 16 symbols:

- Decimal 0–9 → Hex 0–9  
- Decimal 10–15 → Hex A, B, C, D, E, F

Each hex digit represents a 4-bit binary value (a **nibble**).  
Because of this, hex and binary map very neatly:

| Decimal | Binary | Hex |
|--------:|:------:|:---:|
| 0 | 0000 | 0 |
| 1 | 0001 | 1 |
| 2 | 0010 | 2 |
| 3 | 0011 | 3 |
| 4 | 0100 | 4 |
| 5 | 0101 | 5 |
| 6 | 0110 | 6 |
| 7 | 0111 | 7 |
| 8 | 1000 | 8 |
| 9 | 1001 | 9 |
| 10 | 1010 | A |
| 11 | 1011 | B |
| 12 | 1100 | C |
| 13 | 1101 | D |
| 14 | 1110 | E |
| 15 | 1111 | F |

**IPv6 and MAC addresses** are usually written in hexadecimal:

- IPv6 addresses are **128 bits** long.  
- Every 4 bits are shown as one hex digit → **32 hex digits** total.  
- IPv6 is normally grouped in 8 blocks of 4 hex digits: `xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx`.  
- Each block of 4 hex digits is sometimes called a **hextet** (16 bits).

### 5.2.2 Video – Converting Between Hexadecimal and Decimal Numbering Systems

Hex is based on **powers of 16**, just like decimal is based on powers of 10.

Place values for hex (right to left):

- 16⁰ = 1  
- 16¹ = 16  
- 16² = 256  
- 16³ = 4096  
- …

To convert a hex number directly to decimal, you can:

1. Write the place values (…, 4096, 256, 16, 1).  
2. Multiply each place value by its hex digit (converted to decimal).  
3. Add the partial results.

Example (from the video):  
Hex `2A` = (2 × 16) + (10 × 1) = 32 + 10 = **42** in decimal.

In practice, it is often easier to convert **via binary** instead of doing big ×16 calculations in your head.

### 5.2.3 Decimal to Hexadecimal Conversions

A common method (used in the module) for decimal → hex:

1. **Convert decimal to 8-bit binary.**  
2. **Split the 8 bits into two groups of 4 bits.**  
3. **Convert each 4-bit group to its hex digit** using the 0–15 table.

Example (from the text): convert **168₁₀ → hex**

1. 168₁₀ in binary is `10101000`.  
2. Group into nibbles: `1010 1000`.  
3. `1010` = 10 → **A**, `1000` = 8 → **8**.

So **168₁₀ = A8₁₆**.

### 5.2.4 Hexadecimal to Decimal Conversion

For hex → decimal, you can reverse the process:

1. **Convert each hex digit to its 4-bit binary value.**  
2. **Group bits into 8-bit chunks** if needed.  
3. **Convert each 8-bit binary group to decimal** using the binary place values (128, 64, 32, 16, 8, 4, 2, 1).  
4. Combine the results if the number has more than one byte.

Example (from the text): **D2₁₆ → decimal**

1. D = 13 → `1101`; 2 = 2 → `0010`.  
2. D2₁₆ = `1101 0010` in binary.  
3. 8-bit binary `11010010` = 128 + 64 + 16 + 2 = **210**.

So **D2₁₆ = 210₁₀**.

### 5.2.5 Check Your Understanding – Hexadecimal Number System

> These are the quiz questions from 5.2.5 with the correct answers and short working steps.

**Q1 – Which is the hexadecimal equivalent of 202?**

- 202₁₀ ÷ 16 = 12 remainder 10  
- 12 → C, 10 → A → **CA**

 **Answer: `CA`**

---

**Q2 – Which is the hexadecimal equivalent of 254?**

- 254₁₀ ÷ 16 = 15 remainder 14  
- 15 → F, 14 → E → **FE**

 **Answer: `FE`**

---

**Q3 – Which is the decimal equivalent of A9?**

- A9₁₆ = (10 × 16) + 9 = 160 + 9 = **169**

 **Answer: `169`**

---

## 5.3 Module Practice and Quiz

### 5.3.1 What did I learn in this module?

**Binary Number System**

- Binary is a base-2 system using only **0** and **1** (bits).  
- Decimal is base-10 with digits **0–9**.  
- Network devices (PCs, routers, switches) actually work in **binary**, even though humans usually see addresses in decimal or hex.  
- For IPv4, each address is 32 bits and usually shown in **dotted decimal** (for example `192.168.10.10`).  
- You must be comfortable converting between **binary** and **decimal** for IPv4 addressing:  
  - decimal → binary  
  - binary → decimal  

**Hexadecimal Number System**

- Hex is a base-16 system using digits **0–9** and letters **A–F**.  
- It is used heavily for **IPv6 addresses** and **Ethernet MAC addresses** because it is a compact way to show long binary values.  
- IPv6 addresses are **128 bits** long → 32 hex digits total.  
- To convert **hex → decimal**, you normally go via binary: hex → 4-bit groups → binary → decimal.  
- To convert **decimal → hex**, you can go decimal → 8-bit binary → split into 4-bit groups → hex.

Overall, this module built the skills to move between **decimal, binary, and hexadecimal** and explained how those systems appear in IPv4 and IPv6 addressing.

### 5.3.2 Module Quiz – Number Systems (Answer Notes)

I’ll phrase these as “given → answer” for your write-up.

1. **173₁₀ in binary**  
   → `10101101`.

2. **Binary IP `11101100 00010001 00001100 00001010` in dotted decimal**  
   - Octets: 11101100₂ = 236, 00010001₂ = 17, 00001100₂ = 12, 00001010₂ = 10.  
   → **236.17.12.10**

3. **Number of bits in an IPv6 address**  
   → **128 bits**.

4. **232₁₀ in binary**  
   - 232 = 128 + 64 + 32 + 8.  
   → `11101000`.

5. **Correct statements about IPv4 & IPv6 (choose two)**  
   - IPv6 addresses are represented in **hexadecimal**.  
   - IPv4 addresses are **32 bits** long.  
   → Statements: **“IPv6 addresses are represented by hexadecimal numbers”** and **“IPv4 addresses are 32 bits in length.”**

6. **Human-friendly IPv4 format like `201.192.1.14`**  
   → **Dotted decimal** notation.

7. **Binary IP `11001011.00000000.01110001.11010011` in dotted decimal**  
   - 11001011₂ = 203  
   - 00000000₂ = 0  
   - 01110001₂ = 113  
   - 11010011₂ = 211  
   → **203.0.113.211**

8. **Binary `10010101` in decimal**  
   - 128 + 16 + 4 + 1 = 149.  
   → **149**.

9. **Hex `0x3F` in decimal**  
   - `3×16 + 15 = 48 + 15 = 63`.  
   → **63**.

10. **Binary IP `00001010.01100100.00010101.00000001` in dotted decimal**  
    - 00001010₂ = 10  
    - 01100100₂ = 100  
    - 00010101₂ = 21  
    - 00000001₂ = 1  
    → **10.100.21.1**

11. **Hex `0xC9` in decimal**  
    - `12×16 + 9 = 192 + 9 = 201`.  
    → **201**.

12. **Valid hex digit among {F, G, H, J}**  
    → **F** (digits A–F only).

13. **Binary representation of hex `0xCA`**  
    - C → 1100, A → 1010.  
    → `11001010`.

14. **Number of bits in an IPv4 address**  
    → **32 bits**.

---
