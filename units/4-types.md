# 4: Types

<details>

<summary>Bits and Bytes</summary>

* Bit&#x20;
  * Either 1 or 0
  * k bits hold 2\*\*k values
* Byte
  * 8 bits
* Since all data are represented as 1 and 0s --> programmers must specify the type of variable
  * Allows machine code to know how to interpret the bits sequence

</details>

<details>

<summary>Integers</summary>

* 8 bits represent 256 values
* If unsigned --> range is 0 - 255
* If signed --> range is -128 - 127

</details>

<details>

<summary>Characters</summary>

* ASCII
  * Uses 8 bits per character
  * Maps 127 binary sequences to common characters
* Unicode
  * Uses 32 bits per character
  * Allows for non-English characters to be represented as well

</details>

<details>

<summary>Real Numbers (IMPT)</summary>

* Uncountably many real numbers --> cannot represent all numbers in computer
* Cannot represent floating point numbers exactly on computer
  * Eg: 1.1 + 2.2 becomes 3.3000000000000003
* `int` is usually 32 bits long
  * Minimum is 16 bits
  * CPU architecture dependent
* `short` is 16 bits

</details>

<details>

<summary>Compound Types</summary>

* Consists of primitive types (integers, real numbers, characters)
* Eg: Sentence is represented by a sequence of characters
* Eg: Point is represented by a pair of real numbers

</details>

<details>

<summary>Type Declaration</summary>

* Static Typed Languages:
  * Once variable is declared with a type --> type cannot be changed
  * Eg: C
* Dynamically Typed Languages:
  * Type of variable may change depending on the value the variable is assigned to
  * Eg: Python

</details>
