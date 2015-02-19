---
title: Why computers love 0s and 1s
files: []
layout: 2-panels-tree

---
You will probably have heard that computers think in terms of 0 and 1. Let's exaplin why.

## Transistors
All logic chips, memory chips and CPUs are built using millions or billions of tiny transistors. Take a look at the image below and you can see transistors, old and new.

| Image | Description |
|-|-|
|![](.guides/img/vacuum-tube.jpg) | This is a so-called vacuum tube transistor, which is about 1 inch in height. These were used in computers in the 1940s and 50s and you'd find 10 or 20 thousand of them. That's why they were so huge.  |
| ![](.guides/img/i7.jpg) | This is a modern Intel i7 CPU. It contains about 700 million nanoscopic transistors and is around 1 inch square. |

## How they work
Transistors are set up in computer chips in a way that each transistor can exist in 2 states. On or off.

| State | Binary Value | Description |
|-|-|-|
| ON | 1 | Once a minimum voltage is applied across the transistor, the state flips to being ON |
| OFF | 0 | Anything below the minimum voltage, and the transistor flips to being OFF. When you switch the power off, all transistors on a chips flip to OFF or 0 |


---
title: Decimal Numbers
files: []

---
So, how does a computer represent a decimal number internally in binary format? 

Let's actually start of by seeing how we think about decimal numbers. You do this automatically without thinking about it but you probably have forgotten the reasoning.

Decimal is also known as *Base 10* because 10 to power of 0 is 1, 10 to power of 1 is 10, 10 to the power of 2 is 100 etc.

The number **2473** can be thought of like this

| 10 000 | 1000 | 100 | 10 | 1
|-|-|-|-|-|
| 0 | 2 | 4 | 7 | 3 |

In other words

- There are 2 1000's
- There are 4 100's
- There are 7 10's
- and 1 1's

We'll now take the same approach for binary on the next page.

---
title: Binary Numbers
files: []

---
So, a transistor can either be 

- ON or 1
- OFF or 0

Another way of expressing this is to say that a transistor is in a binary state. We'll now start to see why binary numbers are so important.


## Binary
Binary is known as Base 2.

| Base 2 | Power | Result | Base 10 | Power | Result |
|-|-|-|-|-|-|
|2|0|1|10|0|1|
|2|1|2|10|1|10|
|2|2|4|10|2|100|
|2|3|5|10|3|1000|
|2|4|16|10|4|10000|
|2|5|32|10|5|100000|

## The number 24 in binary

| 32 | 16 | 8 | 4 | 2 | 1  |
| -  | -  | - | - | - | -  |
|  0 |  1 | 1 | 0 | 1 | 0  |

If you look at the second row, you can clearly see that the omly possible values are 0 and 1. Now you hopefully start to see the connection between binary, transistors and computers.

So decimal 24 is binary `11010` which is the same as `011010` in the same way that `2473` is the same as `02473`. We don't need to show leading 0s.


---
title: Storing data in memory
files: []

---
Data is typically stored in memory (RAM). Memory is a huge list of locations, each of which can contain a number. Let's assume each memory location (address) can contain a value between 0 and 1023 (in today's chips, the values are actually between 0 and billions).

So the first three addresses in our memory might look like this

| Memory Address | Decimal Value | Binary Value |
|-|-|-|
| 1 | 67   | 0001000011 |
| 2 | 65   | 0001000001 |
| 3 | 84   | 0001010100 |
| 4 | 1023 | 1111111111 |

## Binary Cat
You may remember from an earlier module that letters can be represented as numbers in computers as numbers. One simple standard is the **ASCII** (pronounced 'askey') character set. Each number has a unique value. [Click here](http://www.asciitable.com/) to see the ASCII character set on the internet.

Now look at the table above. You can see that 67 represents 'C' 65 represents 'A' and 84 represents 'T'. So, we are storing the word 'CAT' in memory.

Furthermore, you can see how this is prepresented in memory in binary format.

Now, hopefully, you can see how this binary is represented by the physical transistor states in a memory chip.


---
title: "Bits, nibbles, bytes etc."
files: []

---
Here is our memory table again.

| Memory Address | Decimal Value | Binary Value |
|-|-|-|
| 1 | 67   | 0001000011 |
| 2 | 65   | 0001000001 |
| 3 | 84   | 0001010100 |
| 4 | 1023 | 1111111111 |

If you look in the binary column above, you can see in memory address 4 that the maximum value it is possible to store is `1111111111` or decimal `1023`.

Do you notice how there are 10 possible positions in the binary number? Each position is actually called a 'bit'. Here is a table to show what various data size terms all mean.



| Name | # Bits | Binary Range | Decimal Range |
|-|-|-|-|
| Bit | 1 | 0 to 1 | 0 to 1 |
| Nibble | 4 | 0000 to 1111 | 0 to 15 | 
| Byte | 8 | 00000000 to 11111111 | 0 to 255 | 
| Word | 16 | 0000000000000000 to 1111111111111111 | 0 to 65535 | 

There are actually more but this will do for now.
---
title: Hexadecimal
files: []

---
Hexadecimal sounds horrendous but it is actually very useful when you get into programming. It's quite scary at first but once you get the hang of it, it's not too bad.

In a web page, colors are often represented as RGB (red, green, blue) numbers. 

Play with the widget below by clicking anywhere within the color area. You can also enter values for the Red, Green and Blue values. 

Each number can be between 0 and 255 (that's a 'byte', remember) and represents the saturation level of each color. When these colors get mixed together you actually end up with 255 * 255 * 255 colors. That makes 16,581,375 colors. 

## So what?
Well, in the 'CSS' language, which all web pages use, we can sepcify a color as a color value.

The value 10,442,612 is not very friendly and tells us nothing about the RGB values.

But 159, 87, 116 tells us more. However, 15987116 is not the same as  10,442,612. We need a single number.

In CSS we use hexadecimal numbers because each number between 0 and 255 can be represented with 2 digits.

`color: #9F5774`

The # sign tells the browser that the number that follows is a 'Hex' number.

Here's a table to see how we get there

| System | Red | Green | Blue | 
|-|-|-|-|
|Decimal | 159|87|116|
| Binary | 10011111 | 1010111 | 1110100 |
| Hex | 9F | 57 | 74 |

## The real reason for Hex
If you look at the above table, you can see that one byte (8 binary digits or bits) is always 2 hex characters. This is really useful in  certain cases as it is compact, always exactly 2 characters wide and  represents one byte, which is an important data size in computing.

In the nex section we'll learn how to comvert binary and decimal values into Hex. It's exactly the same approach as decimal and binary.













---
title: Conversion game
files: []

---
Some **awesome** content 4

---
title: "Logic gates & truth tables"
files: []

---

---
title: Real world boolean logic
files: []

---

---
title: Boolean logic in programs
files: []

---
