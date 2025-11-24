---
title: Digital Fundamentals
draft: false
tags:
---
> * [[Notes/Sem3/index|index]]
---
### Module 2: Digital System & Number System

#### Fundamentals of Digital Systems and Logic Families

- **Logic Gates and Operations:**
    - **AND Gate:** Has two or more inputs but only one output. The output is logic 1 only when all inputs are logic 1. The output is logic 0 if any one input is logic 0. Notation: C = A · B.
    - **OR Gate:** Has two or more inputs but only one output. The output is logic 0 only when all inputs are logic 0. The output is logic 1 if any one input is logic 1. Notation: C = A + B.
    - **NOT Gate (Inverter):** Has only one input and one output. Its output is always the complement of its input. The output is logic 1 when its input is logic 0, and logic 0 when its input is logic 1. Notation: C = Ā.
    - **NAND Gate (Universal Gate):** Means NOT AND, i.e., the AND output is NOTed. The output is logic 0 only when all inputs are logic 1.
    - **NOR Gate (Universal Gate):** Means NOT OR, i.e., the OR output is NOTed. The output is logic 1 only when all inputs are logic 0.
    - **EX-OR Gate:** Has two or more inputs but only one output. The output is logic 1 only when the inputs are not equal. It is also called an anti-coincidence gate or inequality detector. Notation: C = A ⊕ B.
    - **EX-NOR Gate:** An X-NOR gate has two or more inputs but only one output. The output is logic 0 when only one of its inputs is logic 0, or when both inputs are logic 0. It is a coincidence gate or equality detector. Notation: C = A ⊙ B.
- **Basic Gates as Universal Gates (NAND/NOR Implementation):**
    - **NOT using NAND gate:** A NAND gate can act as an inverter by tying all its input terminals together and applying the signal to be inverted to a common terminal.
    - **AND using NAND gate:** NAND means NOT AND. So, a NAND gate is a combination of an AND gate and a NOT gate.
    - **OR using NAND gate:** By inverting inputs in a NAND gate, an OR gate is constructed via De Morgan's theorem (Ā · B̄)′ = A + B.
    - **NOT using NOR gate:** A NOR gate can act as an inverter by tying all its input terminals together and applying the signal to be inverted to a common terminal.
    - **OR using NOR gate:** NOR means NOT OR. So, a NOR gate is a combination of an OR gate and a NOT gate.
    - **AND using NOR gate:** By inverting inputs in a NOR gate, an AND gate is constructed via De Morgan's theorem (Ā + B̄)′ = A · B.
- **Boolean Algebra:**
    - **AND laws:** A · 0 = 0 (Null Law), A · 1 = A (Identity Law), A · A = A, A · Ā = 0.
    - **OR laws:** A + 0 = A (Null Law), A + 1 = 1 (Identity Law), A + A = A, A + Ā = 1.
    - **Commutative laws:** A + B = B + A, A · B = B · A.
    - **Associative laws:** (A + B) + C = A + (B + C), (A · B) · C = A · (B · C).
    - **Distributive laws:** A · (B + C) = A · B + A · C, A + B · C = (A + B) · (A + C).
    - **Redundant Literal Rule:** A + ĀB = A + B, A(A + B) = A + B.
    - **Idempotence laws:** A + A = A, A · A = A.
    - **Absorption laws:** A + A B = A, A(A + B) = A.
    - **De Morgan's Theorem:**
        - Law 1: (A + B + C)′ = ĀB̄C̄. States that the complement of a sum of variables is equal to the product of their individual complements.
        - Law 2: (A · B · C)′ = Ā + B̄ + C̄. States that the complement of a product of variables is equal to the sum of their individual complements.
    - **Reduction of Boolean Expression:** Examples are provided to illustrate simplification using Boolean algebra laws.

#### Number Systems

- **Common Number Systems:**
    - **Decimal Number System:** Contains ten unique symbols (0-9). Base or radix is 10.
    - **Binary Number System:** Contains two unique symbols (0, 1). Base or radix is 2.
    - **Octal Number System:** Contains eight unique symbols (0-7). Base or radix is 8.
    - **Hexadecimal Number System:** Contains sixteen unique symbols (0-9, A-F). Base or radix is 16.
- **Number System Conversions:**
    - **Decimal to Binary Conversion:** The decimal integer is converted to binary by successive division by 2, and the decimal fraction by successive multiplication by 2. Remainders are read from bottom to top for the integer part, and integers from top to bottom for the fractional part.
    - **Binary to Decimal Conversion:** Binary numbers are converted by multiplying each binary digit by its positional weight (2^n) and summing the products.
    - **Decimal to Octal Conversion:** Similar to binary, but involves successive division/multiplication by 8. Octal digits are multiplied by 8^n for decimal conversion.
    - **Decimal to Hexadecimal Conversion:** Similar to octal, but involves successive division/multiplication by 16. Hexadecimal digits are multiplied by 16^n for decimal conversion.
    - **Octal to Binary Conversion:** Replace each octal digit with its 3-bit binary equivalent.
    - **Binary to Octal Conversion:** Group binary digits into groups of 3 (from the decimal point outwards) and replace each group with its octal equivalent.
    - **Hexadecimal to Binary Conversion:** Replace each hexadecimal digit with its 4-bit binary equivalent.
    - **Binary to Hexadecimal Conversion:** Group binary digits into groups of 4 (from the decimal point outwards) and replace each group with its hexadecimal equivalent.
    - **Octal to Hexadecimal Conversion:** Convert octal to binary (3-bit groups), then binary to hexadecimal (4-bit groups).
    - **Hexadecimal to Octal Conversion:** Convert hexadecimal to binary (4-bit groups), then binary to octal (3-bit groups).
    - **Accuracy in Binary Number Conversion:** Absolute value of allowable error is typically 1% of the number. Maximum error due to truncation is 2^(-n).
- **Binary Arithmetic:**
    - **Binary Addition:** Rules: 0+0=0; 0+1=1; 1+0=1; 1+1=10 (0 with a carry of 1); 1+1+1=11 (1 with a carry of 1).
    - **Binary Subtraction:** Rules: 0-0=0; 1-1=0; 1-0=1; 0-1=1 with a borrow of 1.
    - **Binary Multiplication:** Illustrated with an example (1011.101 x 101.01).
    - **Binary Division:** Illustrated with an example (101101 / 110).
- **Complements Arithmetic:**
    - **9's Complement (Decimal):** Obtained by subtracting each digit of the decimal number from 9.
    - **10's Complement (Decimal):** Obtained by adding 1 to the 9's complement. Shortcut: subtract LSB from 10 and rest of the digits from 9.
    - **1's Complement (Binary):** Obtained by changing 1's to 0's and 0's to 1's in the binary number.
    - **2's Complement (Binary):** Obtained by adding 1 to the 1's complement. Shortcut: Start at the least significant bit (LSB), copy all zeros, working from LSB toward MSB, copy the first 1, and flip all remaining bits.
    - **Signed Number Representation:** The 2's complement system is used. For positive numbers, magnitude is represented in true binary form and sign bit is 0. For negative numbers, magnitude is represented in 2's complement form and sign bit is 1.
    - **Subtraction using Complement Forms:** Procedures are provided for decimal subtraction using 9's/10's complement and binary subtraction using 1's/2's complement. If there is a carry, the result is positive; if no carry, the result is negative and its complement must be taken.
- **Codes:**
    - **BCD Code (Binary Coded Decimal):** In this code, each decimal digit (0-9) is coded by a 4-bit binary number. It is a weighted code. Six illegal combinations (1010-1111) exist.
        - **BCD Addition:** If there is a carry or illegal sum (not 0-9), add 6 (0110) to the sum term, and add the resulting carry to the next group.
        - **BCD Subtraction:** If there is a borrow from the next higher group, then no correction is required. If there is a borrow from the next group and 6 is subtracted from the difference, this is the correct difference.
    - **Excess-3 Code (XS-3):** A non-weighted BCD code derived by adding 3 (0011) to each BCD digit. It is sequential and self-complementing. It has six invalid states.
        - **XS-3 Addition/Subtraction:** If there is no carry out from the addition of any of the 4-bit groups, subtract 0011 from the sum. If there is a carry out, add 0011 to the sum. Subtraction rules are similar.
    - **Gray Code:** A non-weighted code. It is a cyclic code where successive code words differ in only one bit position. It is a reflective code. The N least significant bits for 2^(n-1)-1 are mirror images for those from 0 to 2^(n-1)-1.
        - **Binary to Gray Conversion:** The MSB of the gray code is the same as the MSB of the binary number. Perform X-ORing between the MSB of the binary and the next bit to get the next bit of the gray code.
        - **Gray to Binary Conversion:** The MSB of the binary number is the same as the MSB of the gray code. Perform X-ORing between the MSB of the binary and the next significant bit of the gray code to get the next bit of the binary.
- **Error Detecting and Correcting Codes:**
    - **Parity:** The simplest technique for detecting errors. An extra bit, the parity bit, is added to each word.
        - **Even parity:** Parity bit is set to 0 or 1 such that the total number of 1s in the word (including parity bit) is an even number.
        - **Odd parity:** Parity bit is set to 0 or 1 such that the total number of 1s in the word (including parity bit) is an odd number.
        - A parity checking circuit generates an error signal if the total number of 1s in an odd-parity system is odd, or in an even-parity system. It can detect a single-bit error but not two or more errors within the same word.
    - **Check Sums:** Simple parity can detect two errors within the same word. Adding a two-dimensional parity check sum can help detect errors transmitted across data.
    - **Block Parity:** Used when several binary words are transmitted in succession. Parity bits are assigned to both rows and columns (row-wise and column-wise parity). This technique can correct a single error.
    - **Error Correcting Code:** A code that can always be deduced from an erroneous word. The minimum distance of a code is the smallest number of bits by which any two code words must differ. Distance of 3 can correct single-bit errors, but not detect two-bit errors.
    - **7-bit Hamming Code:** A code used to encode 4 data bits (D1-D4) into a 7-bit code word by adding three parity bits (P1-P3) at positions 2^0, 2^1, and 2^2. Each parity bit is set to achieve even parity for specific data bits.

#### Characteristics of Digital ICs

- **Threshold Voltage:** The voltage at the input of a gate that causes a change in the state of the output from one logic level to the other.
- **Propagation Delay:** The time a gate takes to propagate a certain amount of time to output. Average transition delay time (tpd) is expressed as (tPLH + tPHL)/2, where tPLH is signal delay time when output goes from logic 0 to 1, and tPHL is delay time when output goes from logic 1 to 0.
- **Power Dissipation:** The power required by a logic gate to operate with 50% duty cycle at a specified frequency.
- **Fan-in:** The number of inputs that the gate is designed to handle.
- **Fan-out:** The maximum number of standard loads that the output of the gate can drive without impairing its normal operation.
- **Voltage Parameters:**
    - **VIL(min):** Minimum voltage level required at the input of a gate for that input to be treated as a logic 1.
    - **VIH(min):** Minimum voltage level required at the input of a gate for that input to be treated as a logic 1.
    - **VOL(max):** Maximum voltage level that can be treated as logic 0 at the output of the gate.
    - **VOH(max):** Maximum voltage level that can be treated as logic 0 at the output of the gate.
    - **IIL:** Current that flows into an input when a specified LOW level voltage is applied.
    - **IIH:** Current that flows into an input when a specified HIGH level voltage is applied.
    - **IOL:** Current that flows from an output in a logic 0 state under specified load conditions.
    - **IOH:** Current that flows from an output in a logic 1 state under specified load conditions.
- **Noise Margin:** When digital circuits operate in a noisy environment, gates may malfunction if noise is beyond certain limits. Noise immunity refers to a circuit's ability to tolerate noise voltages at its inputs.
- **Operating Temperature:** IC gates and other circuits are temperature sensitive. The range of temperature for commercial applications is 0 to 70°C, for industrial 0 to 85°C, and for military applications -55°C to 125°C.
- **Speed Power Product:** A common measure for comparing and obtaining the overall performance of an IC family. It is the speed power product, obtained by multiplying the gate propagation delay by the gate power dissipation.

#### Digital Logic Families

- **TTL vs CMOS vs ECL:** A table compares characteristics like Power input, Frequency limit, Circuit density, and Circuit types per family.
- **Transistor-Transistor Logic (TTL):** Named for its dependence on transistors alone to perform basic logic operations. It is the most popular logic family and widely used bipolar digital IC family. TTL uses transistors operating in saturated mode. Basic TTL logic circuit is the NAND gate. TTL variants include Standard TTL, High Speed TTL, Low power TTL, Schottky TTL, Advanced Schottky TTL, Advanced low power Schottky TTL, and Rfast TTL.
- **Schottky TTL:** A standard TTL version, but high speed TTL series operates using saturated switching. It has more than three times the switching speed of standard TTL, at the expense of approximately doubling the power consumption. Schottky TTL 74S series reduces storage time delay by not allowing the transistor to go into full saturation.
- **Tri-State TTL:** The third TTL configuration, it utilizes a totem-pole configuration and wire ANDing of the open-collector configuration. It has three possible output states: HIGH, LOW, and HIGH impedance (Hi-Z). In the Hi-Z state, both transistors in the totem-pole arrangement are turned off, so the output terminal is a HIGH impedance to ground or Vcc. The output is an open or floating terminal, not LOW or HIGH.

### Module 3: Combinational Logic Design

#### Combinational Digital Circuits

- **Standard Representation for Logic Functions:**
    - **Sum-of-products (SOP) Form:** Also called Disjunctive Normal Form (DNF). Example: f(A, B, C) = ĀB + B̄C̄.
    - **Product-of-sums (POS) Form:** Also called Conjunctive Normal Form (CNF). The function above equation may also be written in the form shown in equation below. By multiplying it out and using the consensus theorem, we can see that it is the same as f(A,B,C) = (A+B)(B+C).
    - **Standard Sum-of-Products Form (Disjunctive Canonical Form, DCF):** All variables of the function either in complemented or uncomplemented form. This form is obtained by finding the sum of all the terms that correspond to those combinations (rows) for which f assumes the value 1.
    - **Standard Product-of-Sums Form (Conjunctive Canonical Form, CCF):** All variables of the function either in complemented or uncomplemented form. This form is obtained by finding the product of all terms that correspond to those combinations (rows) for which f assumes the value 0.
    - **Minterm:** A product term containing all variables of the function either in complemented or uncomplemented form. A minterm assumes the value 1 only for one combination of the variables.
    - **Maxterm:** A sum term containing all variables of the function. It assumes value 0 for only one combination of variables.

#### K-map Representation and Simplification

- **Karnaugh Map (K-Map):** A systematic method of simplifying Boolean expressions. It is a chart or a graph composed of an arrangement of adjacent cells, each representing a particular combination of variables in sum of product form.
- **Two-variable K-Map:** Has 2^2 = 4 possible combinations.
- **Three-variable K-Map:** Has 2^3 = 8 possible combinations.
- **Four-variable K-Map:** Has 2^4 = 16 possible combinations.
- **Reduction using K-Map:** Squares that are physically adjacent or adjacent to each other by wrapping the map can be combined to form bigger squares. The bigger squares (2, 4, 8, etc.) must form either a geometric square or rectangle. The minterms or maxterms to be combinable need their binary designations to differ by a power of 2.
- **K-Map with Don't Care Conditions:** Don't care conditions are denoted by 'X' in a K-Map, meaning the output can be either 0 or 1. They can be used to form larger groups for simplification.

#### Minimization of Logical Functions using Tabulation Method and Variable Entered Mapping Method

- **Quine McCluskey Method (Tabulation Method):** A procedure for minimization using a tabulation table.
    1. List all minterms.
    2. Arrange all minterms in groups based on the number of 1s in their binary representation.
    3. Compare each term of the lowest index group with every term in the succeeding group. Combined terms are marked with a check. New combined terms form the next column.
    4. Compare terms in the same fashion until no further combinations are possible.
    5. List all prime implicants and draw the prime implicant chart.
    6. Obtain the essential prime implicants and minimal expression.
- **Variable-Entered Map (VEM):** An n-variable problem can be plotted on an n-1 variable map. It is useful for implementing designs involving multiplexers. The values of variables in the map itself depend on the logic function and the plotting variable K-Map.

#### Multiplexer, De-Multiplexer/Decoders

- **Multiplexer (MUX):** A device that allows digital information from several sources to be routed onto a single line for transmission. It is a many-to-one device.
    - The relationship between inputs (m) and control inputs (n) is m = 2^n.
    - **Applications:** Logic function generation, data selection, data routing, operation sequencing, parallel-to-serial conversion, waveform generation.
- **Demultiplexer (DEMUX):** Takes several inputs and transmits one of them to the output. It performs the reverse operation of a multiplexer. It is a one-to-many device (1-to-N). The relationship between outputs (m) and control inputs (n) is m = 2^n.
- **Decoder:** A logic circuit that converts an N-bit binary input code into M output lines such that only one output line is activated for each one of the possible combinations of inputs. It identifies or recognizes a particular code.
    - **3 to 8 Decoder:** Shows the circuitry for a decoder with three inputs and eight outputs. It uses all AND gates, and outputs are active-HIGH.

#### Adders, Subtractors

- **Half Adder:** A combinational circuit with two binary inputs (augend and addend bits) and two binary outputs (sum and carry).
    - Sum (S) is the X-OR of A and B (S = A ⊕ B).
    - Carry (C) is the AND of A and B (C = AB).
- **Full Adder:** A combinational circuit that adds two bits and a carry and outputs a sum bit and a carry bit. It can add two binary numbers, each having two or more bits.
    - The sum (S) output is equal to 1 when only one input is 1 or when all three inputs are 1.
    - The carry (Cout) output is 1 if two or three inputs are 1.
    - Can be realized using two X-OR gates and two AND gates, and one OR gate.
- **Half Subtractor:** A combinational circuit that subtracts one bit from another and produces the difference. It has an output for a borrow bit.
    - Difference (d) is A ⊕ B.
    - Borrow (b) is ĀB.
- **Full Subtractor:** A combinational circuit that performs subtraction for two bits and a borrow input. It is used for LSB subtraction.
    - Difference (d) is A ⊕ B ⊕ Cin.
    - Borrow (b) is ĀB + Cin(Ā ⊕ B).
- **Binary Parallel Adder:** A digital circuit that adds two binary numbers in parallel. Consists of full adders connected in a chain, with the output carry from each full-adder connected to the input carry of the next full-adder.
- **Binary Parallel Subtractor:** Subtracts binary numbers by means of complement. Subtraction A-B can be done by taking the 2's complement of B and adding it to A.
- **Binary Adder-Subtractor:** Figure shows a 4-bit adder-subtractor circuit. The mode input M controls the operation: M=0 for addition, M=1 for subtraction. The circuit performs A + B if M=0, and A + B' + 1 (i.e. A-B) if M=1.
- **Look Ahead Carry Adder:** Speeds up the addition process by ripple reduction. It examines all input bits simultaneously and generates the carry-in bits for all stages simultaneously. The carry output for the nth stage is expressed as a two-level AND-OR or equivalent NAND-NAND form.

#### BCD Arithmetic

- BCD Addition and Subtraction details are covered under "Codes" in Module 2.

#### Carry Look Ahead Adder

- Details are covered under "Adders, Subtractors".

#### Serial Adder

- A serial adder is used to add binary numbers in serial form. Two binary numbers are stored in shift registers A and B. Bits are added one pair at a time using a single full adder (FA) circuit. The carry output of the full adder is transferred to a D flip-flop, which serves as the carry input for the next pair of bits.

#### ALU (Arithmetic Logic Unit), Elementary ALU Design

- **Arithmetic Logic Unit (ALU):** A very popular and widely used combinational circuit capable of performing arithmetic as well as logical operations. To perform a micro-operation, specific registers are placed in the inputs of the ALU. The ALU performs an operation, and the result is transferred to a destination register.
- **Elementary ALU Design:** A table shows selection inputs (S2, S1, S0) and carry input (Cin) for various functions like transfer, increment, add, subtract with borrow, decrement, OR, XOR, AND, and complement.

#### Popular MSI Chips

The sources describe the functionality of various MSI (Medium Scale Integration) circuits like multiplexers, demultiplexers, adders, subtractors, and comparators. However, they do not list specific "popular MSI chips" by their common IC number designations (e.g., 74LSxx).

#### Digital Comparator

- **1-bit Magnitude Comparator:** Compares two 1-bit numbers, A and B.
    - A > B: G = A B̄.
    - A < B: L = Ā B.
    - A = B: E = A ⊙ B.
- **2-bit Magnitude Comparator:** Compares two 2-bit numbers, A=A1A0 and B=B1B0. Logic for A>B, A<B, and A=B are provided in Boolean expressions.

#### Parity Checker/Generator

- **Parity Generator:** Generates a parity bit for a given set of data bits. Uses exclusive-OR functions. The logic for a 3-bit parity generator (f = A ⊕ B ⊕ C) is shown.
- **Parity Checker:** Used in error detection. Checks if the received data has correct parity.

#### Code Converters

- **Binary to Gray Converter:** Converts a 4-bit binary input (B3B2B1B0) to a 4-bit gray code output (G3G2G1G0). Logic expressions and K-maps for each gray code bit are provided (e.g., G3=B3, G2=B3⊕B2).
- **BCD to XS-3 Code Converter:** Converts 4-bit BCD input (B4B3B2B1) to XS-3 code output (X4X3X2X1). A truth table and K-maps are used for conversion.

#### Priority Encoders

- **Priority Encoder:** A logic circuit that responds to just one input in accordance with some priority system, ensuring that only the highest priority input is recognized when multiple inputs are HIGH. The output is a binary representation of the input with the highest priority.
    - A truth table and K-maps illustrate a 4-input priority encoder example.

#### Decoders/Drivers for Display Devices

- Decoders are covered above. Specific "drivers for display devices" are not detailed in the sources.

