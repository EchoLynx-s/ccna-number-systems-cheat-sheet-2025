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
