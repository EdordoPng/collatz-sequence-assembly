# collatz-sequence-assembly
A MIPS assembly program that generates the Collatz sequence for a given starting number and performs binary analysis on the sequence elements.

# Collatz Sequence Calculator in MIPS Assembly

![MIPS Logo](https://img.shields.io/badge/MIPS-Assembly-blue)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

A MIPS assembly program that generates the Collatz sequence for a given starting number and performs binary analysis on the sequence elements.

## 📋 Table of Contents
- [Description](#description)
- [The Collatz Conjecture](#the-collatz-conjecture)
- [Program Features](#program-features)
- [Algorithm Implementation](#algorithm-implementation)
- [Binary Analysis](#binary-analysis)
- [Usage Instructions](#usage-instructions)
- [Example Output](#example-output)
- [Register Usage](#register-usage)

## 📝 Description

This MIPS assembly program calculates the Collatz sequence starting from a user-provided number. The program displays the entire sequence and provides additional statistical information about the sequence elements, including a binary analysis of the numbers in the sequence.

## 🧮 The Collatz Conjecture

The Collatz Conjecture is a famous unsolved problem in mathematics. It states that for any positive integer, the following sequence will always eventually reach 1:
- If the number is even, divide it by 2
- If the number is odd, multiply it by 3 and add 1

For example, starting with 6:
- 6 → 3 → 10 → 5 → 16 → 8 → 4 → 2 → 1

The conjecture is that regardless of the starting number, the sequence will always reach 1, entering the cycle 4 → 2 → 1 → 4 → ...

## ✨ Program Features

This program:

1. **Generates the Collatz sequence** starting from a user-provided number
2. **Counts the sequence length** (number of elements until reaching 1)
3. **Performs binary analysis** by finding the number in the sequence with the maximum number of 1s in its binary representation
4. **Handles negative numbers** by converting them to positive before calculation
5. **Handles edge cases** like starting with 0 or 1

## 🔄 Algorithm Implementation

The program implements the Collatz sequence generation with the following steps:

1. **Input Phase**: 
   - User enters a starting number
   - The program converts negative numbers to positive if necessary

2. **Sequence Generation**:
   - For each number in the sequence:
     - Check if the number is 0 or 1 (termination condition)
     - If even, divide by 2
     - If odd, multiply by 3 and add 1
   - Print each number in the sequence

3. **Binary Analysis**:
   - For each number in the sequence, count the number of 1s in its binary representation
   - Track the number with the maximum count of 1s

4. **Output Phase**:
   - Display the complete sequence
   - Display the total count of elements in the sequence
   - Display the number with the maximum count of 1s and its count

## 🔍 Binary Analysis

The program performs a binary analysis to determine which number in the sequence has the most 1s in its binary representation:

1. For each number in the sequence, it:
   - Examines each bit position (32 bits total)
   - Counts the number of 1 bits
   - Updates the maximum if the current number has more 1s than previously found

2. The result provides insight into the binary complexity of the numbers in the sequence.

## 🚀 Usage Instructions

1. Load the program into a MIPS simulator (MARS, SPIM, or QtSPIM)
2. Run the program
3. When prompted, enter a starting number for the Collatz sequence
4. The program will display:
   - The complete Collatz sequence
   - The total number of elements in the sequence
   - The number with the most 1s in its binary representation
   - The count of 1s in that number

## 📊 Example Output

```
Enter a number: 6
6 3 10 5 16 8 4 2 1 

Number of elements in the sequence: 9

Number with the maximum amount of ones in its binary representation among those in the sequence: 5

It has a number of ones equal to: 2
```

## 📋 Register Usage

| Register | Purpose |
|----------|---------|
| `$t0` | Count of elements in the sequence |
| `$t1` | Used for comparisons and bit operations |
| `$t2` | Used for shift in sign change |
| `$t3` | Counter for 1 bits in binary representation |
| `$t4` | Fixed value (32) for 32-bit analysis |
| `$t5` | Bit position counter during binary analysis |
| `$s0` | Current number in the sequence |
| `$s1` | Copy of current number for bit analysis |
| `$s2` | Number with maximum 1 bits in binary |
| `$s3` | Count of maximum 1 bits found |
| `$s4` | Count of even numbers processed |
| `$s5` | Count of odd numbers processed |
